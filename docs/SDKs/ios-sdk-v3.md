---
title: iOS & tvOS SKD (V3)
excerpt: >-
  How to install, initialize, and integrate the Recurly Engage Apple SDK into
  native iOS and tvOS applications, including prompt display, event tracking,
  push notifications, and in-app purchases.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

### Prerequisites

* A Recurly Engage account with a valid App ID (found in **Settings → Application**)
* Xcode with an iOS 15+ or tvOS 15+ deployment target
* Swift Package Manager or access to the `RedFast.xcframework` file for legacy installation

### Limitations

* Push notification support is available on iOS only — not tvOS
* In-app purchase support is available on iOS only
* `PromptManager` is a `@MainActor`-isolated singleton — all public methods must be called from the main thread
* Requires iOS 15+ or tvOS 15+

# Definition

The Recurly Engage Apple SDK is a native library for iOS and tvOS apps that handles prompt rendering and user event tracking automatically. It provides built-in SwiftUI components for modals, banners, interstitials, and inline prompts, and gives you full control over deep linking, custom metadata, push notifications, and in-app purchases.

# Key benefits

* **SDK integration**: Embed prompts and track user events directly in native iOS and tvOS applications — no web views or workarounds needed.
* **Automatic UI handling**: Built-in SwiftUI components for modals, banners, interstitials, and inline prompts take care of rendering so you can focus on your app logic.
* **Deep links and custom metadata**: Leverage custom metadata and deep links for tailored in-app navigation configured directly from Recurly Engage.

# Key details

## Install the SDK

The Recurly Engage Apple SDK supports iOS 15+ and tvOS 15+. The latest SDK version and a sample app are available at [github.com/redfast/redfast-sdk-apple/releases](https://github.com/redfast/redfast-sdk-apple/releases).

### Swift Package Manager

Add the SDK from the public GitHub [repository](https://github.com/redfast/redfast-sdk-apple).

1. Add a new Package Dependency to your existing project.

<Image align="center" border={true} width="75%" src="https://files.readme.io/b69fc2ebde28f7ca810e40ffcc781d6eb0838fe6c859fe97c482ca0f1cd8cbac-Screenshot_2024-11-20_at_19.55.49.png" className="border" />

2. Paste the GitHub repo URL and select the appropriate Dependency Rule.

<Image align="center" border={true} width="75%" src="https://files.readme.io/fa893cbcac4f982e312da89be3b511bec8b321c4c8f4fc7f53f660f30157edd8-Screenshot_2024-11-20_at_19.58.25.png" className="border" />

3. Complete adding the package.

<Image align="center" border={true} width="75%" src="https://files.readme.io/76fdc54ab8b032fd78e26a3b5e14d80593d14279d6707f81b9e69747926936cf-Screenshot_2024-11-20_at_19.59.52.png" className="border" />

4. Confirm successful package installation.

<Image align="center" border={true} width="75%" src="https://files.readme.io/9dcc3755e04a1a6daa30fd8f890f99fe420cc12675e2f918e70c2dce8fd88b6e-Screenshot_2024-11-20_at_20.02.19.png" className="border" />

The SDK ships three products — add only what your target needs:

| Product           | Contents                                                           |
| ----------------- | ------------------------------------------------------------------ |
| `redfast-ui`      | Core + SwiftUI components (modals, banners, interstitials, inline) |
| `redfast-ui-iap`  | `redfast-ui` + StoreKit 2 in-app purchase support                  |
| `redfast-ui-push` | `redfast-ui` + push notification support (iOS only)                |

### Legacy installation via local SDK

1. In Xcode, select **Target → General → Frameworks, Libraries, and Embedded Content** and click **+**.

2. Select **Add Other → Add Files** and open the `RedFast.xcframework` file.

<Image align="center" border={true} width="75%" src="https://files.readme.io/0824267-Screenshot_2024-05-23_at_3.19.28_PM.png" className="border" />

3. Set the embed option to **Embed & Sign**.

<Image align="center" border={true} width="75%" src="https://files.readme.io/ff07460-Screenshot_2024-05-23_at_3.22.56_PM.png" className="border" />

4. Initialize the SDK per the instructions below.

***

## Initialize the SDK

Call `PromptManager.initPrompt` once at app startup, before any screen or button triggers. Your App ID appears on the **Settings → Application** screen in Recurly Engage.

**SwiftUI**

```swift
import redfast_ui

@main
struct MyApp: App {
    init() {
        PromptManager.initPrompt(appId: "YOUR_APP_ID", userId: "USER_ID") { result in
            guard result.code == .OK else { return }
            // SDK ready — safe to call PromptManager.shared from here
        }
    }

    var body: some Scene {
        WindowGroup { ContentView() }
    }
}
```

**UIKit (AppDelegate)**

```swift
import redfast_ui

func application(
    _ application: UIApplication,
    didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?
) -> Bool {
    PromptManager.initPrompt(appId: "YOUR_APP_ID", userId: "USER_ID") { result in
        guard result.code == .OK else { return }
        // SDK ready
    }
    return true
}
```

`PromptManager` is a `@MainActor`-isolated singleton. All public methods must be called from the main thread.

***

## Display prompts — SwiftUI (recommended)

The `.promptOverlay` view modifier is the simplest way to display prompts. It resolves the trigger, respects any configured delay, and renders the appropriate component (`PromptPopup`, `PromptBanner`, or `PromptInterstitial`) automatically.

```swift
import redfast_ui

struct HomeView: View {
    @State private var trigger: PromptOverlayTrigger? = nil

    var body: some View {
        ContentView()
            .promptOverlay(trigger: $trigger) { result in
                switch result.code {
                case .BUTTON1:  handleAccept(result)
                case .BUTTON2:  handleAccept2(result)
                case .BUTTON3:  handleDecline(result)
                case .DISMISS:  break
                case .TIMEOUT:  break
                default:        break
                }
            }
            .onAppear {
                trigger = .screen("HomeScreen")
            }
    }
}
```

### PromptOverlayTrigger

| Case               | When to use                                     |
| ------------------ | ----------------------------------------------- |
| `.screen(String)`  | User navigated to a screen                      |
| `.button(String)`  | User tapped a button with a configured click ID |
| `.prompt(Prompt?)` | Display a specific `Prompt` object directly     |

Setting `trigger` to `nil` hides any active prompt.

***

## Manual trigger — screen name

Call `onScreenChanged` when a new screen becomes active. Returns a `CandidatePathItem` with the matched path and any configured display delay.

```swift
let candidate = PromptManager.shared.onScreenChanged(screenName: "HomeScreen")

if let path = candidate.path {
    let delaySeconds = candidate.delaySeconds  // configured delay before showing
    let prompt = PromptManager.shared.getPrompt(id: path.id)
    // render prompt after delay
}

// If no prompt matched, inspect candidate.result?.code:
// .NOT_APPLICABLE — no matching trigger
// .SUPPRESSED     — matched but currently suppressed
// .HOLDOUT        — user is in holdout group
// .DISABLED       — prompts are disabled via enablePrompt(false)
```

***

## Manual trigger — button click

Call `onButtonClicked` in a button's action handler. May be used alongside `onScreenChanged` when a trigger requires both a screen name and a click ID.

```swift
@IBAction func cancelButtonTapped(_ sender: Any) {
    let candidate = PromptManager.shared.onButtonClicked(clickId: "unsubscribe")

    if let path = candidate.path {
        let prompt = PromptManager.shared.getPrompt(id: path.id)
        // render prompt
    }
}
```

***

## Inline prompts

### SwiftUI component

`PromptInline` is a drop-in SwiftUI view that fetches and renders a zone-based inline prompt automatically. Impression and dismiss tracking are handled internally.

```swift
import redfast_ui

struct HomeView: View {
    var body: some View {
        VStack {
            PromptInline(zone: "featured") { event in
                switch event {
                case .clicked(let result):   handleDeeplink(result)
                case .dismissed(let result): break
                default: break
                }
            }
            // rest of content
        }
    }
}
```

### Fetch inline prompts manually

Use `getTriggerablePrompts` when you need to render inline prompts in a custom UI. Pass the current screen name and/or click ID; use `type` to filter by prompt type and `zoneId` to filter by placement zone.

```swift
let prompts = PromptManager.shared.getTriggerablePrompts(
    screenName: "HomeScreen",   // use "*" to match any screen
    clickId: "*",               // use "*" to match any click
    type: .HORIZONTAL,
    zoneId: "featured"
)

for prompt in prompts {
    // Prompt properties
    let id          = prompt.id
    let type        = prompt.type          // PathType
    let deeplink    = prompt.deeplink      // [String: String?]?
    let deviceMeta  = prompt.deviceMeta    // [String: String?]?
    let inAppSku    = prompt.inAppSku      // App Store product ID if configured
    let button1     = prompt.button1       // ModalButton? (label, colors, dimensions)
    let button2     = prompt.button2
    let button3     = prompt.button3
    let countDown   = prompt.countDown     // auto-dismiss timer in seconds (0 = none)

    // Report user activity
    prompt.impression()   // call when prompt becomes visible
    prompt.goal()         // button 1 tapped
    prompt.goal2()        // button 2 tapped
    prompt.decline()      // button 3 / decline tapped
    prompt.dismiss()      // user dismissed
    prompt.timeout()      // countdown reached zero
    prompt.holdout()      // user is in holdout group
}
```

### Available PathType values

| Value            | Display name                 |
| ---------------- | ---------------------------- |
| `.MODAL`         | Popup prompt                 |
| `.INTERSTITIAL`  | Full-screen interstitial     |
| `.BOTTOM_BANNER` | Bottom banner                |
| `.HORIZONTAL`    | Horizontal banner            |
| `.VERTICAL`      | Vertical banner              |
| `.TILE`          | Tile                         |
| `.VIDEO`         | Video popup                  |
| `.INVISIBLE`     | No UI — metadata/config only |

***

## Manual tracking

Use these methods when you are rendering prompts in a custom UI instead of the built-in components. All methods return a `PromptResult`.

```swift
// Record an impression
let result = PromptManager.shared.onImpression(pathId: prompt.id, actionGroupId: prompt.actionGroupId)

// Record a goal (button 1 accepted)
let result = PromptManager.shared.onGoal(pathId: prompt.id, actionGroupId: prompt.actionGroupId)

// Record a second-button goal (button 2)
let result = PromptManager.shared.onGoal(pathId: prompt.id, actionGroupId: prompt.actionGroupId, acceptType: "accept2")

// Record a dismiss / timeout / decline
let result = PromptManager.shared.onDismiss(pathId: prompt.id, actionGroupId: prompt.actionGroupId, reason: "dismiss")
// reason values: "dismiss" → .DISMISS | "timeout" → .TIMEOUT | "decline" → .BUTTON3

// Suppress future display after an interaction
PromptManager.shared.suppressOverlay(pathId: prompt.id, reason: "accept")
// reason values: "accept" | "timeout" | "decline" | "dismiss"
```

### Inline-specific tracking

```swift
// Record that an inline prompt became visible
PromptManager.shared.onInlineViewed(pathId: prompt.id, actionGroupId: prompt.actionGroupId)

// Record that the user tapped an inline prompt
PromptManager.shared.onInlineClicked(pathId: prompt.id, actionGroupId: prompt.actionGroupId)
```

***

## PromptResult

Every tracking call returns a `PromptResult`:

```swift
public struct PromptResult {
    var code: PromptResultCode
    var value: [String: Any?]?       // deep link key-value pairs
    var promptMeta: [String: Any?]?  // prompt analytics metadata
    var meta: [String: Any?]?        // custom metadata from Recurly Engage
    var inAppProductId: String?      // App Store product ID if configured
}
```

`promptMeta` contains:

| Key                    | Description                         |
| ---------------------- | ----------------------------------- |
| `promptName`           | Prompt name                         |
| `promptID`             | Prompt ID                           |
| `promptVariationName`  | Variation name                      |
| `promptVariationID`    | Variation ID                        |
| `promptExperimentName` | Experiment name                     |
| `promptExperimentID`   | Experiment ID                       |
| `promptType`           | Numeric path type                   |
| `buttonLabel`          | Label of the button that was tapped |

### PromptResultCode values

| Code              | Meaning                                    |
| ----------------- | ------------------------------------------ |
| `.OK`             | SDK initialized successfully               |
| `.IMPRESSION`     | Impression recorded                        |
| `.BUTTON1`        | User accepted (button 1)                   |
| `.BUTTON2`        | User accepted (button 2)                   |
| `.BUTTON3`        | User declined (button 3)                   |
| `.DISMISS`        | User dismissed                             |
| `.TIMEOUT`        | Auto-dismiss timer expired                 |
| `.HOLDOUT`        | User is in holdout group                   |
| `.NOT_APPLICABLE` | No matching trigger                        |
| `.SUPPRESSED`     | Matched but suppressed                     |
| `.DISABLED`       | Prompts disabled via `enablePrompt(false)` |
| `.ERROR`          | SDK error                                  |

### PromptEvent enum

`PromptEvent` is what `promptOverlay` and `PromptInline` deliver to your `onEvent` closure:

```swift
switch event {
case .impression(let result): // prompt became visible
case .clicked(let result):    // button 1 or button 2 tapped
case .decline(let result):    // button 3 tapped
case .timeout(let result):    // timer expired
case .dismissed(let result):  // user dismissed
}
```

***

## Deep links and custom metadata

Deep link key-value pairs and custom metadata are configured in Recurly Engage.

```swift
// From a Prompt object (inline)
let deeplink   = prompt.deeplink    // [String: String?]?
let customMeta = prompt.deviceMeta  // [String: String?]?

// From a PromptResult (modal/banner, after a goal event)
let deeplink   = result.value       // [String: Any?]?
let customMeta = result.meta        // [String: Any?]?
```

***

## Invisible prompts — metadata only

Prompts of type `.INVISIBLE` carry no UI; they deliver metadata visible across all screens. Use `getMeta()` to read the merged metadata from all active invisible prompts.

```swift
let meta = PromptManager.shared.getMeta() // [String: Any]
```

***

## Send a custom tracking event

```swift
PromptManager.shared.customTrack(customFieldId: "YOUR_CUSTOM_TRACK_ID")
```

***

## Update user ID

Change the user ID after initialization, for example when a user authenticates mid-session. Prompts refresh automatically within a few seconds.

```swift
PromptManager.shared.setUserId("NEW_USER_ID")
```

***

## Enable/disable prompts

Pause and resume all prompt display without re-initializing the SDK.

```swift
PromptManager.shared.enablePrompt(enabled: false) // pause
PromptManager.shared.enablePrompt(enabled: true)  // resume
```

***

## Reset suppression

Clear all suppressed prompt state and report a goal reset to Recurly Engage. Useful for QA or when a user's subscription state changes.

```swift
PromptManager.shared.resetGoal()
```

***

## Push notifications (iOS only)

Add the `redfast-ui-push` product to your target. Integration order:

1. `FirebaseApp.configure()` — optional, only if using FCM
2. `PromptManager.initPrompt(...)` — must come before the push manager
3. `RedfastPushManager.shared.configure()` — requests permission, registers for remote notifications

```swift
import redfast_ui
import redfast_ui_push

class AppDelegate: NSObject, UIApplicationDelegate {
    func application(
        _ application: UIApplication,
        didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]? = nil
    ) -> Bool {
        // FirebaseApp.configure()  // uncomment if using FCM

        PromptManager.initPrompt(appId: "YOUR_APP_ID", userId: "USER_ID") { _ in }
        RedfastPushManager.shared.configure()
        return true
    }
}
```

`RedfastPushManager` handles the full push lifecycle automatically:

* Requests user permission and registers for remote notifications
* Swizzles `UIApplicationDelegate` push callbacks — no manual forwarding needed
* Posts the APNs/FCM token to Recurly Engage
* Tracks push impression and goal events

Firebase/FCM support is enabled automatically when `FirebaseMessaging` is present in the host app.

See `Redflix/Redflix/redflixApp.swift` for a SwiftUI integration example using `@UIApplicationDelegateAdaptor`.

### Customize the notification action button

```swift
RedfastPushManager.shared.setCustomButton("Remind me later")
```

### Read notification payload

These helpers parse the notification `userInfo` dictionary regardless of whether the payload uses a flat, nested, or APNs `aps.alert` structure:

```swift
let manager = RedfastPushManager.shared

let title       = manager.getTitle(userInfo)
let body        = manager.getBody(userInfo)
let actionUrl   = manager.getActionUrl(userInfo)      // URL to open on tap
let deeplink    = manager.getActionDeeplink(userInfo) // deep link on tap
let images      = manager.getImageUrls(userInfo)
// images.iconUrl, images.smallIconUrl, images.imageUrl
```

***

## In-app purchases (iOS only)

Add the `redfast-ui-iap` product to your target. When a `PromptResult` includes an `inAppProductId`, pass it to `PromptManager.shared.purchase`:

```swift
if case .clicked(let result) = event, let sku = result.inAppProductId {
    let iapResult = await PromptManager.shared.purchase(sku)
    switch iapResult {
    case .successful: break  // entitle the user
    case .cancelled:  break  // user cancelled
    case .pending:    break  // awaiting parental approval
    case .unverified: break  // StoreKit verification failed
    case .unfound:    break  // product ID not found in the store
    case .error:      break  // StoreKit error
    case .unknown:    break
    }
}
```

On a successful purchase the conversion goal is automatically reported to Recurly Engage.

**Local testing:** Redflix ships a `configurations.storekit` file. Use Xcode's StoreKit test environment to test purchases without hitting App Store servers.