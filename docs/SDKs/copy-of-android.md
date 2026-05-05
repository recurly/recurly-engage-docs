---
title: Copy of Android
excerpt: >-
  Configuration guide for the Recurly Engage Android SDK, enabling native prompt
  display and usage tracking in your mobile and TV apps.
deprecated: false
hidden: true
metadata:
  robots: index
---
This document covers the **v3 architecture** (`core` + `ui` modules). If you are still on v2.x, see the [legacy Android SDK docs](https://docs.recurly.com/recurly-engage/docs/android-sdk).

***

## Overview

The Recurly Engage Android SDK v3 provides native support for Android phones, tablets, Android TV, Fire Tablets, and Fire TV. The SDK ships **drop-in Compose components** that automatically handle display of modals, interstitials, bottom banners and inline prompts, while still exposing the underlying prompt data and tracking primitives for apps that need full control over the render tree.

### Key benefits

* **Compose-first API** — a single `@Composable` (`PromptOverlay`) wires trigger resolution, delay, and rendering with no manual UI code.
* **Clean two-module architecture** — `core` holds networking, domain models, and business logic; `ui` holds Compose components. Host apps can depend on `ui` for the full experience or on `core` only when providing their own UI.
* **Automatic prompt types** — popups (modals), interstitials, bottom banners, and inline banners are selected automatically from the prompt configuration in Pulse.
* **Configuration change safe** — countdown timers, impression state, and dismissal state survive rotation via `rememberSaveable`.
* **Broad device support** — one SDK for phones, tablets, Android TV, and Amazon Fire devices, with automatic TV vs phone detection and focus-aware inline components.
* **Typed event model** — a `PromptEvent` sealed class delivers `Impression`, `Clicked`, `Decline`, `Timeout`, and `Dismissed` events with a strongly-typed `PromptResult`.
* **Optional In-App Purchase and Push** — enabled via product flavors in the `ui` module (Google Billing Library 8.0, Amazon Appstore SDK 3.x, Firebase Cloud Messaging, or Amazon A3L).

### Key details

The Recurly Engage Android SDK v3 monitors consumption, fetches active paths for the current `appId`/`userId`, and renders configured prompts inside your Compose tree. Prompt lifecycle events (impression, dismissal, click, timeout, holdout) are reported back to Recurly Engage without additional wiring.

***

## Install the SDK

The v3 Engage Android SDK is published as two artifacts:

| Artifact           | Purpose                                                                      |
| ------------------ | ---------------------------------------------------------------------------- |
| `redfast-sdk-core` | Domain models, networking, prompt resolution. No Android UI.                 |
| `redfast-sdk-ui`   | Jetpack Compose components, IAP adapters, push messaging. Depends on `core`. |

Most integrations depend on **`redfast-sdk-ui`**, which transitively exposes `redfast-sdk-core`. Only depend on `core` directly if you are rendering prompts with your own UI layer.

### Gradle / Maven

**Gradle (Kotlin DSL)**

```kotlin
// settings.gradle.kts
dependencyResolutionManagement {
    repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
    repositories {
        google()
        mavenCentral()
        maven(url = "https://jitpack.io")
    }
}

// app/build.gradle.kts
dependencies {
    // Full SDK (recommended)
    implementation("com.github.redfast.redfast-sdk-android-build:redfast-sdk-ui:v3.0.0")

    // Or, data layer only (bring your own UI)
    implementation("com.github.redfast.redfast-sdk-android-build:redfast-sdk-core:v3.0.0")
}
```

**Gradle (Groovy)**

```groovy
dependencies {
    implementation "com.github.redfast.redfast-sdk-android-build:redfast-sdk-ui:v3.0.0"
}
```

**Maven**

```xml
<repositories>
    <repository>
        <id>jitpack.io</id>
        <url>https://jitpack.io</url>
    </repository>
</repositories>

<dependency>
    <groupId>com.github.redfast.redfast-sdk-android-build</groupId>
    <artifactId>redfast-sdk-ui</artifactId>
    <version>v3.0.0</version>
</dependency>
```

### Product flavors (optional)

The `ui` module defines two flavor dimensions to tailor the artifact to your store and push provider:

| Dimension | Flavors                     | Notes                                                                |
| --------- | --------------------------- | -------------------------------------------------------------------- |
| `store`   | `google`, `amazon`, `noiap` | Selects the In-App Purchase implementation. `noiap` provides a stub. |
| `push`    | `fcm`, `adm`, `nopush`      | Selects the push-messaging implementation.                           |

Invalid combinations (`google` + `adm`, `amazon` + `fcm`) are disabled automatically.

### Local `.aar` installation

1. Download the latest `.aar` files from the [releases page](https://github.com/redfast/redfast-sdk-android-build/releases).
2. Copy them into `app/libs/`.
3. Add them to the module dependencies:

```kotlin
dependencies {
    implementation(files("libs/redfast-sdk-core-release.aar"))
    implementation(files("libs/redfast-sdk-ui-google-fcm-release.aar"))

    // Required Compose dependencies
    implementation(platform("androidx.compose:compose-bom:2024.09.00"))
    implementation("androidx.compose.ui:ui")
    implementation("androidx.compose.material3:material3")
    implementation("io.coil-kt:coil-compose:2.6.0")

    // Only if using the google store flavor
    implementation("com.android.billingclient:billing:8.0.0")
    implementation("com.android.billingclient:billing-ktx:8.0.0")
}

android {
    buildFeatures {
        compose = true
    }
}
```

### Requirements

* **Min SDK**: 24
* **Compile/Target SDK**: 36
* **Kotlin**: 2.0.x
* **Jetpack Compose BOM**: 2024.09.00 or later
* **Java**: 11

***

## Initialize Engage

Call `PromptManager.initialize()` once from your `Application.onCreate()`. The `appId` is available in **Pulse → Settings → Application**, and `userId` should uniquely identify the current user (or a guest identifier for anonymous sessions).

```kotlin
class RedflixApplication : Application() {
    override fun onCreate() {
        super.onCreate()

        PromptManager.initialize(
            context = this,
            appId = APP_ID,
            userId = USER_ID,
            onComplete = { result ->
                Log.d("Engage", "SDK initialized: ${result.code}")
            }
        )
    }
}
```

`PromptManager` is a singleton: additional calls to `initialize()` are ignored (use `setUserId()` to switch users). Anywhere in the app you can retrieve it with:

```kotlin
val pm = PromptManager.get()
```

Under the hood `initialize()`:

1. Builds a `DeviceInfo` record (manufacturer, model, TV vs phone) used by the composition mapper to select the correct asset.
2. Starts a background ping loop to sync available prompts with Recurly Engage.
3. Wires the Push and IAP managers for the active `ui` flavor.

The `onComplete` callback is invoked **once** after the first successful sync with `PromptResultCode.OK`.

***

## Trigger a popup via Screen Name

Drop `PromptOverlay` inside any Composable screen to allow the SDK to display the appropriate modal/interstitial/bottom-banner when the screen becomes active.

```kotlin
@Composable
fun HomeScreen() {
    // ... your screen content ...

    PromptOverlay(
        triggerType = PromptOverlayTriggerType.Screen(name = "home"),
        onEvent = { event ->
            when (event) {
                is PromptEvent.Impression -> Log.d("Engage", "shown: ${event.result.promptMeta?.promptName}")
                is PromptEvent.Clicked    -> handleDeeplink(event.result.value)
                is PromptEvent.Decline    -> { /* user clicked button 3 */ }
                is PromptEvent.Timeout    -> { /* auto-dismissed */ }
                is PromptEvent.Dismissed  -> { /* close or back */ }
            }
        }
    )
}
```

### `PromptOverlayTriggerType`

```kotlin
sealed class PromptOverlayTriggerType {
    data class Screen(val name: String) : PromptOverlayTriggerType()
    data class Button(val clickId: String) : PromptOverlayTriggerType()
}
```

`PromptOverlay` handles all lifecycle concerns for you:

1. Resolves a candidate prompt using the current screen name / click id.
2. Applies the configured `delaySeconds` before presenting.
3. Short-circuits if the user is in a holdout group or if the prompt is currently suppressed (dismiss/accept/decline intervals).
4. Dispatches to the correct renderer based on `PathType` (`MODAL`, `INTERSTITIAL`, `BOTTOM_BANNER`).

***

## Trigger a popup via button click

For button-triggered prompts, emit a `PromptOverlayTriggerType.Button` event when the user taps the button. The composable is placed once at the screen level and keyed off the click id you manage via state.

```kotlin
@Composable
fun DetailScreen() {
    var triggeredClickId by remember { mutableStateOf<String?>(null) }

    Column {
        Button(onClick = { triggeredClickId = "subscribe" }) {
            Text("Subscribe")
        }
    }

    triggeredClickId?.let { clickId ->
        PromptOverlay(
            triggerType = PromptOverlayTriggerType.Button(clickId = clickId),
            onEvent = { event ->
                // optionally clear the click id on terminal events
                if (event is PromptEvent.Dismissed || event is PromptEvent.Clicked) {
                    triggeredClickId = null
                }
            }
        )
    }
}
```

If you need to resolve prompts manually (e.g. from a legacy `View`-based surface) you can still use the low-level API on `PromptManager`:

```kotlin
val prompts = PromptManager.get().getTriggerablePrompts(
    screenName = "home",
    clickId    = "subscribe",
    type       = PathType.MODAL
)

prompts.firstOrNull()?.let { prompt ->
    // Render prompt manually, or let the SDK render it:
    // ShowPrompt(prompt, onEvent = { ... })
}
```

`getTriggerablePrompts` accepts wildcards (`"*"`) for both `screenName` and `clickId` and filters out prompts that are currently suppressed or in holdout.

***

## Retrieve and render inline prompts

Inline prompts (banners, tiles, featured) are bound to a **zone id** configured in Pulse. Drop the `PromptInline` composable where the inline should appear — it handles impression tracking, focus states (for TV), countdown timers, and dismissal.

```kotlin
item {
    PromptInline(
        zoneId = InlineType.general.value, // "android-banner"
        closeButton = InlineCloseButtonStyle(
            color   = "#000000",
            bgColor = "#FFFFFF",
            size    = 20
        ),
        timer = InlineTimerStyle(
            fontSize  = 14,
            fontColor = "#FFFFFF"
        ),
        focusStyle = InlineFocusStyle(
            borderColor  = "#ff4400",
            borderWidth  = 1,
            borderRadius = 5
        ),
        modifier = Modifier.padding(horizontal = 16.dp),
        onEvent = { event -> Log.d("Engage", "inline event: $event") }
    )
}
```

### Built-in zones

```kotlin
enum class InlineType(val value: String) {
    all("all"),
    general("android-banner"),
    featured("featured"),
    horizontal("horizontal"),
    billboard("billboard"),
    redfit_shop_banner("redfit-shop-banner"),
    redflix("redflix-featured")
}
```

### Manual retrieval

For custom layouts or `View`-based surfaces you can fetch the underlying data directly:

```kotlin
val pm = PromptManager.get()

pm.getTriggerablePrompts(
    screenName = "home",
    clickId    = "*",
    type       = PathType.HORIZONTAL,
    zoneId     = InlineType.featured.value
).firstOrNull()?.let { prompt ->
    // Device-aware background image (selected from rf_settings_bg_image_* fields)
    val bgImage        = prompt.pathItem.actions.rfSettingsBgImage
    val deviceMeta     = prompt.deviceMeta
    val deeplink       = prompt.deeplink
    val accessibility  = prompt.accessibilityLabel
    val customMetadata = prompt.pathItem.actions.rfMetadata

    // Button colors (from Pulse configuration)
    val button1Color = prompt.button1?.textColor
    val button2Color = prompt.button2?.textColor
    val button3Color = prompt.button3?.textColor

    // Countdown configuration
    val countDownSeconds     = prompt.countDown
    val countDownPrompt      = prompt.countDownPrompt
    val countDownColor       = prompt.countDownPromptColor
    val countDownFontSize    = prompt.countDownPromptFontSize
    val countDownInvisible   = prompt.countDownPromptInvisible

    // Suspend-based tracking primitives (invoke on a coroutine scope)
    lifecycleScope.launch {
        val impression = prompt.impression()   // PromptEvent.Impression equivalent
        val dismiss    = prompt.dismiss()
        val timeout    = prompt.timeout()
        val decline    = prompt.decline()       // user clicked button 3
        val goal       = prompt.goal()          // user clicked button 1 (accept)
        val goal2      = prompt.goal2()         // user clicked button 2 (accept2)
        val holdout    = prompt.holdout()       // invoked automatically when holdout=true
    }
}
```

`Prompt.pathItem.actions` exposes every field configured in Pulse (see `Action` in the SDK source for the full list).

***

## Deep link to a media asset

Deeplink key-value pairs are configured per-prompt in Pulse. When the user triggers the primary CTA the SDK decodes them and returns them on the `PromptResult.value` field:

```kotlin
PromptOverlay(
    triggerType = PromptOverlayTriggerType.Screen(name = "home"),
    onEvent = { event ->
        if (event is PromptEvent.Clicked) {
            val deeplink = event.result.value            // Map<String, Any>?
            val target   = deeplink?.get("deeplink") as? String
            target?.let { navigateTo(it) }
        }
    }
)
```

The same deeplink is exposed on manual retrieval via `Prompt.deeplink` (`Map<String, Any>?`) or `PathItem.actions.rfSettingsDeeplink`.

***

## Access custom metadata

Add custom key-value metadata in Pulse to drive registration flows, feature flags, or any app-specific behaviour. The metadata is delivered on every `PromptEvent` through `PromptResult.meta`:

```kotlin
onEvent = { event ->
    val campaign: String? = event.result.meta?.get("campaign") as? String
    val tier: String?     = event.result.meta?.get("tier") as? String
}
```

To read metadata that is not attached to a visible prompt, use `PromptManager.get().getMeta()` which returns the merged metadata from every **invisible** path currently matched for this user:

```kotlin
val allMeta: Map<String, Any> = PromptManager.get().getMeta()
```

***

## Send a usage-tracking event

Send a custom tracker event to Engage. When configured as a tracker in Pulse, custom events can be used to target future prompts at specific user segments.

```kotlin
PromptManager.get().customTrack("video_played")
```

The call is fire-and-forget and runs on `Dispatchers.IO`.

***

## Set or change the User ID

You can change the `userId` after initialization — for example, once a user signs in. It may take a few seconds for prompts to refresh with the new identity.

```kotlin
PromptManager.get().setUserId("new-user-id")

// Read the currently active user id
val currentUserId = PromptManager.get().getUserId()
```

To temporarily pause all prompt rendering and tracking (for example, during a splash or onboarding flow):

```kotlin
PromptManager.get().enablePrompt(false)
// ...later
PromptManager.get().enablePrompt(true)
```

Use `resetGoal()` to clear local suppression state and all server-tracked goals for the active user. Useful for QA:

```kotlin
PromptManager.get().resetGoal()
```

***

## Event model

All Compose components emit events through a single `onEvent: (PromptEvent) -> Unit` callback.

```kotlin
sealed class PromptEvent {
    abstract val result: PromptResult

    data class Impression(override val result: PromptResult) : PromptEvent()
    data class Clicked(override val result: PromptResult)    : PromptEvent()
    data class Decline(override val result: PromptResult)    : PromptEvent()
    data class Timeout(override val result: PromptResult)    : PromptEvent()
    data class Dismissed(override val result: PromptResult)  : PromptEvent()
}

data class PromptResult(
    val code: PromptResultCode,
    val value: Map<String, Any>? = null,       // decoded deeplink payload
    val meta:  Map<String, Any?>? = null,      // custom metadata from Pulse
    val promptMeta: PromptMeta? = null          // prompt / experiment identity
)

enum class PromptResultCode(val value: Int) {
    OK(1),
    ERROR(-100),
    NOT_APPLICABLE(-101),
    DISABLED(-102),
    SUPPRESSED(-103),
    IMPRESSION(100),
    BUTTON1(101),   // accept
    BUTTON2(102),   // accept2
    BUTTON3(103),   // decline
    DISMISS(110),
    TIMEOUT(111),
    HOLDOUT(120)
}

data class PromptMeta(
    val promptName: String?,
    val promptID: String?,
    val promptVariationName: String?,
    val promptVariationID: String?,
    val promptExperimentName: String?,
    val promptExperimentID: String?,
    val promptType: Int?,          // PathType.value
    val buttonLabel: String?       // localized label of the pressed button
)
```

Mapping of `PromptResultCode` to user action:

| Code             | Fired when                                                                         |
| ---------------- | ---------------------------------------------------------------------------------- |
| `OK`             | SDK initialized successfully                                                       |
| `IMPRESSION`     | The prompt was rendered to the user                                                |
| `BUTTON1`        | User tapped the primary (accept) button                                            |
| `BUTTON2`        | User tapped the secondary (accept2) button                                         |
| `BUTTON3`        | User tapped the tertiary (decline) button                                          |
| `DISMISS`        | User closed the prompt (X, back, tap outside)                                      |
| `TIMEOUT`        | The configured timer expired and auto-dismissed the prompt                         |
| `HOLDOUT`        | The user is in a holdout group; no prompt is shown but the event is tracked        |
| `SUPPRESSED`     | The prompt is temporarily suppressed by a previous dismiss/accept/decline interval |
| `NOT_APPLICABLE` | No prompt matches the current screen/click id                                      |
| `DISABLED`       | `enablePrompt(false)` is active                                                    |
| `ERROR`          | An unexpected error occurred; `PromptResult.value` contains the stack trace key    |

***

## Rendering prompts manually

If you need to bypass `PromptOverlay`'s automatic resolution (e.g., to show a specific prompt at a specific moment), use `ShowPrompt` with a `Prompt` object you obtained from `getPrompt()` / `getTriggerablePrompts()`:

```kotlin
val prompt = PromptManager.get().getPrompt(promptId)
prompt?.let {
    ShowPrompt(
        prompt = it,
        onEvent = { event -> /* ... */ }
    )
}
```

`ShowPrompt` dispatches to `PromptPopup` (modal dialog), `PromptInterstitial` (full-screen), or `PromptBottomBanner` based on `prompt.type`.

***

## In-App Purchase

When the `google` or `amazon` store flavor is active, the `PromptManager` instance exposes helpers around the platform billing SDK. Product details returned by Engage (via `prompt.inAppSku` / `Action.rfSettingsAndroidInappProductId`) can be resolved and purchased end-to-end:

```kotlin
val pm = PromptManager.get()

// Query previous purchases for the signed-in Play/Amazon user
pm.iapGetPurchased { purchases, type ->
    // 'purchases' is List<com.android.billingclient.api.Purchase> on google
}

// Resolve SKU metadata (title, price, description)
pm.iapGetProductDetails(
    sku  = "com.myapp.premium",
    type = IapProductType.subscription
) { skus: List<IapProduct> ->
    val product = skus.firstOrNull() ?: return@iapGetProductDetails
    // Launch the platform billing flow
    pm.iapPurchaseProducts(
        activity = currentActivity,
        productDetailsList = listOf(product.platformProduct), // ProductDetails / IapItem
        subscriptionUpdateParams = null
    ) { purchases, error ->
        // Acknowledge / consume the purchase and notify Engage
        purchases.firstOrNull()?.let { purchase ->
            pm.iapNotifyAppStore(purchase, IapProductType.subscription) { code, msg ->
                Log.d("IAP", "notify app store: $code $msg")
            }
        }
    }
}
```

`IapProduct` is a platform-agnostic wrapper:

```kotlin
data class IapProduct(
    val sku: String?,
    val title: String?,
    val description: String?,
    val price: String?,
    val platformProduct: Any   // ProductDetails (Google) or com.amazon.device.iap.model.Product
)

enum class IapProductType(val value: String) {
    consumable("consumable"),
    nonConsumable("android-nonConsumable"),
    subscription("subscription")
}
```

Call `pm.iapOnActivityResumed()` from the hosting activity's `onResume()` to refresh pending purchases on the Amazon flavor (no-op on Google).

***

## Push notifications

When the `fcm` or `adm` flavor is active, `PushManager` is wired automatically. To deliver a push token to Engage, call it from your Firebase / A3L service:

```kotlin
class MyFcmService : FirebaseMessagingService() {
    override fun onNewToken(token: String) {
        PushManager.onTokenReceived(token, channel = "fcm")
    }
    override fun onMessageReceived(message: RemoteMessage) {
        PushManager.onMessageReceived(
            PushMessage(
                title = message.notification?.title,
                body  = message.notification?.body,
                smallIconUrl = message.data["imageSmallIconUrl"],
                iconUrl      = message.data["imageIconUrl"],
                imageUrl     = message.data["imageUrl"],
                campaignId   = message.data["promptId"],
                actionUrl    = message.data["actionUrl"],
                actionDeeplink = message.data["actionDeeplink"]
            )
        )
    }
}
```

`PushManager` reports `trackPushImpression` on delivery and `trackPushGoal` on tap (handled by the bundled `NotificationOpenReceiver`).

***

## Architecture reference

```
host app
   │
   ▼
com.redfast.ui        ← Jetpack Compose components, IAP + Push adapters
   │
   ▼
com.redfast           ← Domain models, networking, PromptCore
   (core module)
```

| Layer               | Key types                                                                                                                                                                |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Public Compose API  | `PromptOverlay`, `PromptInline`, `ShowPrompt`                                                                                                                            |
| Public data API     | `PromptManager`, `Prompt`, `PromptEvent`, `PromptResult`, `PromptResultCode`, `PathType`, `InlineType`, `InlineCloseButtonStyle`, `InlineTimerStyle`, `InlineFocusStyle` |
| IAP                 | `IapManager`, `IapProduct`, `IapProductType`                                                                                                                             |
| Push                | `PushManager`, `PushMessage`                                                                                                                                             |
| Internal (SDK only) | `PromptState`, `PromptPopup`, `PromptInterstitial`, `PromptBottomBanner`, `PromptCloseBar`, `ModalParamsMapper`, `InlineParamsMapper`                                    |

### Path types

```kotlin
enum class PathType(val value: Int) {
    ALL(-1), INVISIBLE(1), MODAL(2), HORIZONTAL(5), VIDEO(6),
    TEXT(7), VERTICAL(8), TILE(9), INTERSTITIAL(10),
    NOTIFICATION(11), EMAIL(12), BOTTOM_BANNER(13)
}
```

`MODAL`, `INTERSTITIAL`, and `BOTTOM_BANNER` are rendered automatically by `PromptOverlay`. Inline types (`HORIZONTAL`, `VERTICAL`, `TILE`, `VIDEO`) are surfaced through `PromptInline` / `getTriggerablePrompts`.

***

## External libraries

### Common (both modules)

| Dependency                                      | Version |
| ----------------------------------------------- | ------- |
| `com.squareup.retrofit2:retrofit`               | 3.0.0   |
| `com.squareup.retrofit2:converter-gson`         | 2.9.0   |
| `com.squareup.okhttp3:okhttp`                   | 4.12.0  |
| `com.squareup.okhttp3:logging-interceptor`      | 4.12.0  |
| `com.google.code.gson:gson`                     | 2.10.1  |
| `org.jetbrains.kotlinx:kotlinx-coroutines-core` | 1.9.0   |
| `androidx.core:core-ktx`                        | 1.17.0  |

### UI module (additional)

| Dependency                                          | Version    |
| --------------------------------------------------- | ---------- |
| `androidx.compose:compose-bom`                      | 2024.09.00 |
| `androidx.compose.ui:ui`, `ui-graphics`             | bundled    |
| `androidx.compose.material3:material3`              | bundled    |
| `androidx.compose.material:material-icons-extended` | bundled    |
| `io.coil-kt:coil-compose`                           | 2.6.0      |
| `androidx.compose.runtime:runtime-saveable`         | 1.10.4     |

### Flavor-conditional

| Flavor   | Dependency                                                           | Version              |
| -------- | -------------------------------------------------------------------- | -------------------- |
| `google` | `com.android.billingclient:billing`                                  | 8.0.0                |
| `google` | `com.android.billingclient:billing-ktx`                              | 8.0.0                |
| `amazon` | `com.amazon.device:amazon-appstore-sdk`                              | 3.0.4                |
| `fcm`    | `com.google.firebase:firebase-messaging` (via `firebase-bom:34.0.0`) | —                    |
| `adm`    | `A3LMessaging-1.1.0.aar`                                             | 1.1.0 (compile-only) |

***

## Migration from v2.x

| v2.x API                                                                                          | v3 equivalent                                                                    |
| ------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| `PromotionManager.initPromotion(appId, userId)`                                                   | `PromptManager.initialize(context, appId, userId, onComplete)`                   |
| `PromotionManager.setScreenName(view, name) { }`                                                  | `PromptOverlay(PromptOverlayTriggerType.Screen(name), onEvent = { })`            |
| `PromotionManager.showModal(promptId, ctx) { }`                                                   | `ShowPrompt(prompt, onEvent = { })`                                              |
| `PromotionManager.getTriggerablePrompts(screen, clickId, type) { }`                               | `PromptManager.get().getTriggerablePrompts(screen, clickId, type)` (synchronous) |
| `PromotionManager.customTrack(id)`                                                                | `PromptManager.get().customTrack(id)`                                            |
| `PromotionManager.setUserId(id)`                                                                  | `PromptManager.get().setUserId(id)`                                              |
| Inline `prompt.impression() / click() / click2() / decline() / timeout() / dismiss() / holdout()` | Same lambdas on `Prompt`, plus `PromptEvent` emission via `PromptInline`         |
| `PromotionManager.showDebugView(...)`                                                             | Removed — use `setUserId()` / `resetGoal()` directly, or gate with your own UI   |

All Compose components are stateless from the caller's perspective: dropping `PromptOverlay` / `PromptInline` inside any `@Composable` is sufficient. There is no longer a need to pass a `View` root nor to manually invoke tracking lambdas when using the built-in renderers.

***

## Troubleshooting

* **Nothing renders** — confirm `PromptManager.initialize()` was called and the `onComplete` callback fired with `PromptResultCode.OK`. Check that the screen name / zone id matches what is configured in Pulse.
* **Prompt shows once then never again** — this is expected. The SDK honours the **dismiss / accept / decline / timeout intervals** configured in Pulse. Call `PromptManager.get().resetGoal()` in a debug build to clear local suppression state.
* **Countdown restarts after rotation** — upgrade to v3.0.0+. In v3 the countdown is restored from `initialStartTime` via `rememberSaveable`.
* **Multiple prompts render on the same screen** — that is supported; each `PromptOverlay` / `PromptInline` manages its own state and `remember(prompt.id)` keys prevent recomposition cross-talk.
* **TV focus ring invisible** — provide a non-default `InlineFocusStyle` with a contrasting `borderColor` and `borderWidth >= 1`.

```
Google IAP: 
    com.android.billingclient:billing:6.0.1
    com.android.billingclient:billing-ktx:6.0.1
    
Amazon IAP:
    amazon/in-app-purchasing-2.0.76.jar
```

<br />
