---
title: Android (V3)
excerpt: >-
  How to install, initialize, and integrate the Recurly Engage Android SDK v3
  into native Android applications, including prompt display, event tracking,
  inline components, push notifications, and in-app purchases.
deprecated: false
hidden: false
metadata:
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">This page covers the Recurly Engage Android software development kit (SDK) v3 architecture (<code>core</code> and <code>ui</code> modules). If you're still on v2.x, see the <a href="https://docs.recurly.com/recurly-engage/docs/android-sdk" target="_blank">legacy Android SDK docs</a>.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>A Recurly Engage account with a valid App ID (found in <strong>Pulse → Settings → Application</strong>)</li>
  <li>Android min SDK 24, compile/target SDK 36</li>
  <li>Kotlin 2.0.x</li>
  <li>Jetpack Compose BOM 2024.09.00 or later</li>
  <li>Java 11</li>
  <li>Maven Central access (included by default in Android projects)</li>
</ul>

### Limitations

<ul class="rp-list">
  <li><code>PromptManager</code> is a singleton. Additional calls to <code>initialize()</code> are ignored, so use <code>setUserId()</code> to switch users</li>
  <li>In-app purchase support requires the <code>google</code> or <code>amazon</code> store flavor of the <code>ui</code> module</li>
  <li>Push notification support requires the <code>fcm</code> or <code>adm</code> push flavor of the <code>ui</code> module</li>
  <li>Invalid flavor combinations (<code>google</code> + <code>adm</code>, <code>amazon</code> + <code>fcm</code>) are disabled automatically</li>
  <li><code>iapOnActivityResumed()</code> must be called from the host activity's <code>onResume()</code> on the Amazon flavor</li>
</ul>

# Definition

<div class="rp-definition">The Recurly Engage Android SDK v3 is a native library for Android phones, tablets, Android TV, Fire Tablets, and Fire TV. It ships drop-in Compose components that automatically handle display of modals, interstitials, bottom banners, and inline prompts, while still exposing the underlying prompt data and tracking primitives for apps that need full control over the render tree.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-code" aria-hidden="true"></i></div>
    <strong>Compose-first API</strong>
    <span>A single <code>@Composable</code> (<code>PromptOverlay</code>) wires trigger resolution, delay, and rendering with no manual UI code.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-cubes" aria-hidden="true"></i></div>
    <strong>Clean two-module architecture</strong>
    <span><code>core</code> holds networking, domain models, and business logic. <code>ui</code> holds Compose components. Host apps can depend on <code>ui</code> for the full experience, or on <code>core</code> only when providing their own UI.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-wand-magic-sparkles" aria-hidden="true"></i></div>
    <strong>Automatic, rotation-safe prompts</strong>
    <span>Popups (modals), interstitials, bottom banners, and inline banners are selected automatically from the prompt configuration in Pulse. Countdown timers, impression state, and dismissal state survive rotation through <code>rememberSaveable</code>.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-tv" aria-hidden="true"></i></div>
    <strong>Broad device support</strong>
    <span>One SDK for phones, tablets, Android TV, and Amazon Fire devices, with automatic TV vs. phone detection and focus-aware inline components.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-bolt" aria-hidden="true"></i></div>
    <strong>Typed events, optional purchases and push</strong>
    <span>A <code>PromptEvent</code> sealed class delivers <code>Impression</code>, <code>Clicked</code>, <code>Decline</code>, <code>Timeout</code>, and <code>Dismissed</code> events with a strongly typed <code>PromptResult</code>. In-app purchase and push are optional, enabled through product flavors in the <code>ui</code> module (Google Billing Library 8.0, Amazon Appstore SDK 3.x, Firebase Cloud Messaging, or Amazon A3L).</span>
  </div>
</div>

# Key details

The SDK monitors consumption, fetches active paths for the current `appId`/`userId`, and renders configured prompts inside your Compose tree. Prompt lifecycle events (impression, dismissal, click, timeout, holdout) are reported back to Recurly Engage without additional wiring.

## Install the SDK

The v3 SDK is split into two modules published separately to **Maven Central**:

<ul class="rp-list">
  <li><strong><code>ui</code> module</strong>: Jetpack Compose components (<code>PromptOverlay</code>, <code>PromptInline</code>, and so on), in-app purchase (IAP) adapters, and push. Depends on <code>core</code>. <strong>Use this if you want the SDK to render prompts for you.</strong></li>
  <li><strong><code>core</code> module</strong>: Networking, domain models, and prompt resolution. No Compose UI. <strong>Use this if you want to fetch prompt data and render your own UI.</strong></li>
</ul>

Each `ui` artifact bundles `core` transitively, so you only need one dependency.

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Artifact</td><td>Module</td><td>Store</td><td>Push</td><td>IAP</td></tr>
  <tr><td><code>engage-sdk-android-google</code></td><td>UI</td><td>Google Play</td><td>FCM</td><td>Google Play Billing</td></tr>
  <tr><td><code>engage-sdk-android-amazon</code></td><td>UI</td><td>Amazon Fire</td><td>ADM</td><td>Amazon IAP</td></tr>
  <tr><td><code>engage-sdk-android-noiap</code></td><td>UI</td><td>Google Play</td><td>FCM</td><td>None</td></tr>
  <tr><td><code>engage-sdk-android-core</code></td><td>Core</td><td>Any</td><td>None</td><td>None</td></tr>
</table>

FCM is Firebase Cloud Messaging, and ADM is Amazon Device Messaging.

### Gradle/Maven

**Gradle (Kotlin DSL)**

```kotlin
// settings.gradle.kts
dependencyResolutionManagement {
    repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
    repositories {
        google()
        mavenCentral()
    }
}

// app/build.gradle.kts
dependencies {
    // Google Play with IAP + FCM push (recommended for most apps)
    implementation("com.recurly:engage-sdk-android-google:3.0.0")

    // Amazon Fire with IAP + ADM push
    implementation("com.recurly:engage-sdk-android-amazon:3.0.0")

    // Google Play without IAP
    implementation("com.recurly:engage-sdk-android-noiap:3.0.0")

    // Data layer only — bring your own UI
    implementation("com.recurly:engage-sdk-android-core:3.0.0")
}
```

**Gradle (Groovy)**

```groovy
dependencies {
    implementation "com.recurly:engage-sdk-android-google:3.0.0"
}
```

**Maven**

```xml
<!-- No extra repository needed — SDK is on Maven Central -->
<dependency>
    <groupId>com.recurly</groupId>
    <!-- Replace artifactId with your chosen variant:
         engage-sdk-android-google | engage-sdk-android-amazon |
         engage-sdk-android-noiap  | engage-sdk-android-core   -->
    <artifactId>engage-sdk-android-google</artifactId>
    <version>3.0.0</version>
</dependency>
```

### Local .aar installation

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Download the .aar files</h4><p>Download the latest <code>.aar</code> files from the <a href="https://github.com/redfast/redfast-sdk-android-build/releases" target="_blank">releases page</a>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Copy them into your project</h4><p>Copy them into <code>app/libs/</code>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Add them as dependencies</h4><p>Add them to the module dependencies, as shown below.</p></div>
  </div>
</div>

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

<ul class="rp-list">
  <li><strong>Min SDK</strong>: 24</li>
  <li><strong>Compile/Target SDK</strong>: 36</li>
  <li><strong>Kotlin</strong>: 2.0.x</li>
  <li><strong>Jetpack Compose BOM</strong>: 2024.09.00 or later</li>
  <li><strong>Java</strong>: 11</li>
</ul>

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

`PromptManager` is a singleton: additional calls to `initialize()` are ignored (use `setUserId()` to switch users). Anywhere in the app, you can retrieve it with:

```kotlin
val pm = PromptManager.get()
```

Under the hood, `initialize()`:

1. Builds a `DeviceInfo` record (manufacturer, model, TV vs. phone) used by the composition mapper to select the correct asset.
2. Starts a background ping loop to sync available prompts with Recurly Engage.
3. Wires the Push and IAP managers for the active `ui` flavor.

The `onComplete` callback is invoked once after the first successful sync with `PromptResultCode.OK`.

## Trigger a popup via screen name

Drop `PromptOverlay` inside any Composable screen to allow the SDK to display the appropriate modal, interstitial, or bottom banner when the screen becomes active.

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

### PromptOverlayTriggerType

```kotlin
sealed class PromptOverlayTriggerType {
    data class Screen(val name: String) : PromptOverlayTriggerType()
    data class Button(val clickId: String) : PromptOverlayTriggerType()
}
```

`PromptOverlay` handles all lifecycle concerns for you:

1. Resolves a candidate prompt using the current screen name or click ID.
2. Applies the configured `delaySeconds` before presenting.
3. Short-circuits if the user is in a holdout group or if the prompt is currently suppressed (dismiss, accept, or decline intervals).
4. Dispatches to the correct renderer based on `PathType` (`MODAL`, `INTERSTITIAL`, `BOTTOM_BANNER`).

## Trigger a popup via button click

For button-triggered prompts, emit a `PromptOverlayTriggerType.Button` event when the user taps the button. Place the composable once at the screen level, and key it off the click ID you manage through state.

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

If you need to resolve prompts manually (for example, from a legacy `View`-based surface), you can still use the low-level API on `PromptManager`:

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

`getTriggerablePrompts` accepts wildcards (`"*"`) for both `screenName` and `clickId`, and filters out prompts that are currently suppressed or in holdout.

## Retrieve and render inline prompts

Inline prompts (banners, tiles, featured) are bound to a **zone ID** configured in Pulse. Drop the `PromptInline` composable where the inline should appear. It handles impression tracking, focus states (for TV), countdown timers, and dismissal.

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

For custom layouts or `View`-based surfaces, you can fetch the underlying data directly:

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

## Deep link to a media asset

You configure deep link key-value pairs per prompt in Pulse. When the user triggers the primary call-to-action (CTA), the SDK decodes them and returns them in the `PromptResult.value` field:

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

The same deep link is exposed on manual retrieval through `Prompt.deeplink` (`Map<String, Any>?`) or `PathItem.actions.rfSettingsDeeplink`.

## Access custom metadata

Add custom key-value metadata in Pulse to drive registration flows, feature flags, or any app-specific behavior. The metadata is delivered on every `PromptEvent` through `PromptResult.meta`:

```kotlin
onEvent = { event ->
    val campaign: String? = event.result.meta?.get("campaign") as? String
    val tier: String?     = event.result.meta?.get("tier") as? String
}
```

To read metadata that isn't attached to a visible prompt, use `PromptManager.get().getMeta()`. It returns the merged metadata from every invisible path currently matched for this user:

```kotlin
val allMeta: Map<String, Any> = PromptManager.get().getMeta()
```

## Send a usage-tracking event

Send a custom tracker event to Engage. When you configure it as a tracker in Pulse, custom events can be used to target future prompts at specific user segments.

```kotlin
PromptManager.get().customTrack("video_played")
```

The call is fire-and-forget and runs on `Dispatchers.IO`.

## Set or change the user ID

You can change the `userId` after initialization, for example, once a user signs in. It may take a few seconds for prompts to refresh with the new identity.

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

Use `resetGoal()` to clear local suppression state and all server-tracked goals for the active user. This is useful for QA:

```kotlin
PromptManager.get().resetGoal()
```

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

This table maps each `PromptResultCode` to a user action:

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Code</td><td>Fired when</td></tr>
  <tr><td><code>OK</code></td><td>SDK initialized successfully</td></tr>
  <tr><td><code>IMPRESSION</code></td><td>The prompt was rendered to the user</td></tr>
  <tr><td><code>BUTTON1</code></td><td>User tapped the primary (accept) button</td></tr>
  <tr><td><code>BUTTON2</code></td><td>User tapped the secondary (accept2) button</td></tr>
  <tr><td><code>BUTTON3</code></td><td>User tapped the tertiary (decline) button</td></tr>
  <tr><td><code>DISMISS</code></td><td>User closed the prompt (X, back, tap outside)</td></tr>
  <tr><td><code>TIMEOUT</code></td><td>The configured timer expired and auto-dismissed the prompt</td></tr>
  <tr><td><code>HOLDOUT</code></td><td>The user is in a holdout group; no prompt is shown but the event is tracked</td></tr>
  <tr><td><code>SUPPRESSED</code></td><td>The prompt is temporarily suppressed by a previous dismiss/accept/decline interval</td></tr>
  <tr><td><code>NOT_APPLICABLE</code></td><td>No prompt matches the current screen/click id</td></tr>
  <tr><td><code>DISABLED</code></td><td><code>enablePrompt(false)</code> is active</td></tr>
  <tr><td><code>ERROR</code></td><td>An unexpected error occurred; <code>PromptResult.value</code> contains the stack trace key</td></tr>
</table>

## Rendering prompts manually

If you need to bypass `PromptOverlay`'s automatic resolution (for example, to show a specific prompt at a specific moment), use `ShowPrompt` with a `Prompt` object you obtained from `getPrompt()` or `getTriggerablePrompts()`:

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

## In-app purchase

When the `google` or `amazon` store flavor is active, the `PromptManager` instance exposes helpers around the platform billing SDK. You can resolve and purchase the product details returned by Engage (through `prompt.inAppSku` / `Action.rfSettingsAndroidInappProductId`) end-to-end:

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

## Push notifications

When the `fcm` or `adm` flavor is active, `PushManager` is wired automatically. To deliver a push token to Engage, call it from your Firebase/A3L service:

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

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Layer</td><td>Key types</td></tr>
  <tr><td>Public Compose API</td><td><code>PromptOverlay</code>, <code>PromptInline</code>, <code>ShowPrompt</code></td></tr>
  <tr><td>Public data API</td><td><code>PromptManager</code>, <code>Prompt</code>, <code>PromptEvent</code>, <code>PromptResult</code>, <code>PromptResultCode</code>, <code>PathType</code>, <code>InlineType</code>, <code>InlineCloseButtonStyle</code>, <code>InlineTimerStyle</code>, <code>InlineFocusStyle</code></td></tr>
  <tr><td>IAP</td><td><code>IapManager</code>, <code>IapProduct</code>, <code>IapProductType</code></td></tr>
  <tr><td>Push</td><td><code>PushManager</code>, <code>PushMessage</code></td></tr>
  <tr><td>Internal (SDK only)</td><td><code>PromptState</code>, <code>PromptPopup</code>, <code>PromptInterstitial</code>, <code>PromptBottomBanner</code>, <code>PromptCloseBar</code>, <code>ModalParamsMapper</code>, <code>InlineParamsMapper</code></td></tr>
</table>

### Path types

```kotlin
enum class PathType(val value: Int) {
    ALL(-1), INVISIBLE(1), MODAL(2), HORIZONTAL(5), VIDEO(6),
    TEXT(7), VERTICAL(8), TILE(9), INTERSTITIAL(10),
    NOTIFICATION(11), EMAIL(12), BOTTOM_BANNER(13)
}
```

`PromptOverlay` renders `MODAL`, `INTERSTITIAL`, and `BOTTOM_BANNER` automatically. Inline types (`HORIZONTAL`, `VERTICAL`, `TILE`, `VIDEO`) are surfaced through `PromptInline` / `getTriggerablePrompts`.

## External libraries

### Common (both modules)

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Dependency</td><td>Version</td></tr>
  <tr><td><code>com.squareup.retrofit2:retrofit</code></td><td>3.0.0</td></tr>
  <tr><td><code>com.squareup.retrofit2:converter-gson</code></td><td>2.9.0</td></tr>
  <tr><td><code>com.squareup.okhttp3:okhttp</code></td><td>4.12.0</td></tr>
  <tr><td><code>com.squareup.okhttp3:logging-interceptor</code></td><td>4.12.0</td></tr>
  <tr><td><code>com.google.code.gson:gson</code></td><td>2.10.1</td></tr>
  <tr><td><code>org.jetbrains.kotlinx:kotlinx-coroutines-core</code></td><td>1.9.0</td></tr>
  <tr><td><code>androidx.core:core-ktx</code></td><td>1.17.0</td></tr>
</table>

### UI module (additional)

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Dependency</td><td>Version</td></tr>
  <tr><td><code>androidx.compose:compose-bom</code></td><td>2024.09.00</td></tr>
  <tr><td><code>androidx.compose.ui:ui</code>, <code>ui-graphics</code></td><td>bundled</td></tr>
  <tr><td><code>androidx.compose.material3:material3</code></td><td>bundled</td></tr>
  <tr><td><code>androidx.compose.material:material-icons-extended</code></td><td>bundled</td></tr>
  <tr><td><code>io.coil-kt:coil-compose</code></td><td>2.6.0</td></tr>
  <tr><td><code>androidx.compose.runtime:runtime-saveable</code></td><td>1.10.4</td></tr>
</table>

### Flavor-conditional

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Flavor</td><td>Dependency</td><td>Version</td></tr>
  <tr><td><code>google</code></td><td><code>com.android.billingclient:billing</code></td><td>8.0.0</td></tr>
  <tr><td><code>google</code></td><td><code>com.android.billingclient:billing-ktx</code></td><td>8.0.0</td></tr>
  <tr><td><code>amazon</code></td><td><code>com.amazon.device:amazon-appstore-sdk</code></td><td>3.0.8</td></tr>
  <tr><td><code>fcm</code></td><td><code>com.google.firebase:firebase-messaging</code> (through <code>firebase-bom:34.0.0</code>)</td><td>—</td></tr>
  <tr><td><code>adm</code></td><td><code>A3LMessaging-1.1.0.aar</code></td><td>1.1.0 (compile-only)</td></tr>
</table>

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
| `PromotionManager.showDebugView(...)`                                                             | Removed. Use `setUserId()` / `resetGoal()` directly, or gate with your own UI    |

All Compose components are stateless from the caller's perspective. Dropping `PromptOverlay` or `PromptInline` inside any `@Composable` is sufficient. You no longer need to pass a `View` root or manually invoke tracking lambdas when you use the built-in renderers.

## Troubleshooting

* **Nothing renders**: Confirm `PromptManager.initialize()` was called and the `onComplete` callback fired with `PromptResultCode.OK`. Check that the screen name or zone ID matches what is configured in Pulse.
* **Prompt shows once then never again**: This is expected. The SDK honors the dismiss, accept, decline, and timeout intervals configured in Pulse. Call `PromptManager.get().resetGoal()` in a debug build to clear local suppression state.
* **Countdown restarts after rotation**: Upgrade to v3.0.0+. In v3, the countdown is restored from `initialStartTime` through `rememberSaveable`.
* **Multiple prompts render on the same screen**: That is supported. Each `PromptOverlay` / `PromptInline` manages its own state, and `remember(prompt.id)` keys prevent recomposition cross-talk.
* **TV focus ring invisible**: Provide a non-default `InlineFocusStyle` with a contrasting `borderColor` and `borderWidth >= 1`.

## Claude skill

A Claude skill for this SDK is available for download at <a href="https://github.com/redfast/redfast-sdk-android/blob/main/SKILL.md" target="_blank">SKILL.md</a>. This skill enables Claude to assist with SDK integration, prompt configuration, and event handling in your Android application.

<br />
