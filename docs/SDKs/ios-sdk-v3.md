---
title: iOS & tvOS SDK (V3)
excerpt: >-
  How to install, initialize, and integrate the Recurly Engage Apple SDK into
  native iOS and tvOS applications, including prompt display, event tracking,
  push notifications, and in-app purchases.
deprecated: false
hidden: false
metadata:
  robots: noindex
---
<div class="rp-page">
  <div class="rp-overview">The Recurly Engage Apple software development kit (SDK) lets you display prompts and track user events in native iOS and tvOS apps.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>A Recurly Engage account with a valid App ID (found in <strong>Settings → Application</strong>)</li>
  <li>Xcode with an iOS 15+ or tvOS 15+ deployment target</li>
  <li>Swift Package Manager or access to the <code>RedFast.xcframework</code> file for legacy installation</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>Push notification support is available on iOS only, not tvOS</li>
  <li>In-app purchase support is available on iOS only</li>
  <li><code>PromptManager</code> is a <code>@MainActor</code>-isolated singleton, so all public methods must be called from the main thread</li>
  <li>Requires iOS 15+ or tvOS 15+</li>
</ul>

# Definition

<div class="rp-definition">The Recurly Engage Apple SDK is a native library for iOS and tvOS apps that handles prompt rendering and user event tracking automatically. It provides built-in SwiftUI components for modals, banners, interstitials, and inline prompts, and gives you full control over deep linking, custom metadata, push notifications, and in-app purchases.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-mobile-screen-button" aria-hidden="true"></i></div>
    <strong>SDK integration</strong>
    <span>Embed prompts and track user events directly in native iOS and tvOS applications, with no web views or workarounds needed.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-wand-magic-sparkles" aria-hidden="true"></i></div>
    <strong>Automatic UI handling</strong>
    <span>Built-in SwiftUI components for modals, banners, interstitials, and inline prompts take care of rendering so you can focus on your app logic.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-link" aria-hidden="true"></i></div>
    <strong>Deep links and custom metadata</strong>
    <span>Use custom metadata and deep links for tailored in-app navigation configured directly from Recurly Engage.</span>
  </div>
</div>

# Key details

## Install the SDK

The Recurly Engage Apple SDK supports iOS 15+ and tvOS 15+. The latest SDK version and a sample app are available at <a href="https://github.com/redfast/redfast-sdk-apple/releases" target="_blank">github.com/redfast/redfast-sdk-apple/releases</a>.

### Swift Package Manager

Add the SDK from the public GitHub <a href="https://github.com/redfast/redfast-sdk-apple" target="_blank">repository</a>.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Add a package dependency</h4><p>Add a new Package Dependency to your existing project.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/b69fc2ebde28f7ca810e40ffcc781d6eb0838fe6c859fe97c482ca0f1cd8cbac-Screenshot_2024-11-20_at_19.55.49.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Paste the repository URL</h4><p>Paste the GitHub repo URL and select the appropriate Dependency Rule.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/fa893cbcac4f982e312da89be3b511bec8b321c4c8f4fc7f53f660f30157edd8-Screenshot_2024-11-20_at_19.58.25.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Complete adding the package</h4><p>Complete adding the package.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/76fdc54ab8b032fd78e26a3b5e14d80593d14279d6707f81b9e69747926936cf-Screenshot_2024-11-20_at_19.59.52.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Confirm the installation</h4><p>Confirm successful package installation.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/9dcc3755e04a1a6daa30fd8f890f99fe420cc12675e2f918e70c2dce8fd88b6e-Screenshot_2024-11-20_at_20.02.19.png" align="center" width="75%" border={true} />


The SDK ships three products. Add only what your target needs:

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Product</td><td>Contents</td></tr>
  <tr><td><code>redfast-ui</code></td><td>Core + SwiftUI components (modals, banners, interstitials, inline)</td></tr>
  <tr><td><code>redfast-ui-iap</code></td><td><code>redfast-ui</code> + StoreKit 2 in-app purchase support</td></tr>
  <tr><td><code>redfast-ui-push</code></td><td><code>redfast-ui</code> + push notification support (iOS only)</td></tr>
</table>

### Legacy installation via local SDK

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open the frameworks list</h4><p>In Xcode, select <span style={{fontWeight: "bold"}}>Target → General → Frameworks, Libraries, and Embedded Content</span> and select <span style={{fontWeight: "bold"}}>+</span>.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Add the framework file</h4><p>Select <span style={{fontWeight: "bold"}}>Add Other → Add Files</span> and open the <code>RedFast.xcframework</code> file.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/0824267-Screenshot_2024-05-23_at_3.19.28_PM.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Set the embed option</h4><p>Set the embed option to <span style={{fontWeight: "bold"}}>Embed &amp; Sign</span>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/ff07460-Screenshot_2024-05-23_at_3.22.56_PM.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Initialize the SDK</h4><p>Initialize the SDK per the instructions below.</p></div>
  </div>
</div>

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

## Display prompts with SwiftUI (recommended)

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

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Case</td><td>When to use</td></tr>
  <tr><td><code>.screen(String)</code></td><td>User navigated to a screen</td></tr>
  <tr><td><code>.button(String)</code></td><td>User tapped a button with a configured click ID</td></tr>
  <tr><td><code>.prompt(Prompt?)</code></td><td>Display a specific <code>Prompt</code> object directly</td></tr>
</table>

Setting `trigger` to `nil` hides any active prompt.

## Manually trigger by screen name

Call `onScreenChanged` when a new screen becomes active. It returns a `CandidatePathItem` with the matched path and any configured display delay.

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

## Manually trigger by button click

Call `onButtonClicked` in a button's action handler. You can use it alongside `onScreenChanged` when a trigger requires both a screen name and a click ID.

```swift
@IBAction func cancelButtonTapped(_ sender: Any) {
    let candidate = PromptManager.shared.onButtonClicked(clickId: "unsubscribe")

    if let path = candidate.path {
        let prompt = PromptManager.shared.getPrompt(id: path.id)
        // render prompt
    }
}
```

## Inline prompts

### SwiftUI component

`PromptInline` is a drop-in SwiftUI view that fetches and renders a zone-based inline prompt automatically. It handles impression and dismiss tracking internally.

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

Use `getTriggerablePrompts` when you need to render inline prompts in a custom UI. Pass the current screen name and/or click ID. Use `type` to filter by prompt type and `zoneId` to filter by placement zone.

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

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Value</td><td>Display name</td></tr>
  <tr><td><code>.MODAL</code></td><td>Popup prompt</td></tr>
  <tr><td><code>.INTERSTITIAL</code></td><td>Full-screen interstitial</td></tr>
  <tr><td><code>.BOTTOM_BANNER</code></td><td>Bottom banner</td></tr>
  <tr><td><code>.HORIZONTAL</code></td><td>Horizontal banner</td></tr>
  <tr><td><code>.VERTICAL</code></td><td>Vertical banner</td></tr>
  <tr><td><code>.TILE</code></td><td>Tile</td></tr>
  <tr><td><code>.VIDEO</code></td><td>Video popup</td></tr>
  <tr><td><code>.INVISIBLE</code></td><td>No UI — metadata/config only</td></tr>
</table>

## Manual tracking

Use these methods when you render prompts in a custom UI instead of the built-in components. All methods return a `PromptResult`.

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

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Key</td><td>Description</td></tr>
  <tr><td><code>promptName</code></td><td>Prompt name</td></tr>
  <tr><td><code>promptID</code></td><td>Prompt ID</td></tr>
  <tr><td><code>promptVariationName</code></td><td>Variation name</td></tr>
  <tr><td><code>promptVariationID</code></td><td>Variation ID</td></tr>
  <tr><td><code>promptExperimentName</code></td><td>Experiment name</td></tr>
  <tr><td><code>promptExperimentID</code></td><td>Experiment ID</td></tr>
  <tr><td><code>promptType</code></td><td>Numeric path type</td></tr>
  <tr><td><code>buttonLabel</code></td><td>Label of the button that was tapped</td></tr>
</table>

### PromptResultCode values

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Code</td><td>Meaning</td></tr>
  <tr><td><code>.OK</code></td><td>SDK initialized successfully</td></tr>
  <tr><td><code>.IMPRESSION</code></td><td>Impression recorded</td></tr>
  <tr><td><code>.BUTTON1</code></td><td>User accepted (button 1)</td></tr>
  <tr><td><code>.BUTTON2</code></td><td>User accepted (button 2)</td></tr>
  <tr><td><code>.BUTTON3</code></td><td>User declined (button 3)</td></tr>
  <tr><td><code>.DISMISS</code></td><td>User dismissed</td></tr>
  <tr><td><code>.TIMEOUT</code></td><td>Auto-dismiss timer expired</td></tr>
  <tr><td><code>.HOLDOUT</code></td><td>User is in holdout group</td></tr>
  <tr><td><code>.NOT_APPLICABLE</code></td><td>No matching trigger</td></tr>
  <tr><td><code>.SUPPRESSED</code></td><td>Matched but suppressed</td></tr>
  <tr><td><code>.DISABLED</code></td><td>Prompts disabled via <code>enablePrompt(false)</code></td></tr>
  <tr><td><code>.ERROR</code></td><td>SDK error</td></tr>
</table>

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

## Deep links and custom metadata

You configure deep link key-value pairs and custom metadata in Recurly Engage.

```swift
// From a Prompt object (inline)
let deeplink   = prompt.deeplink    // [String: String?]?
let customMeta = prompt.deviceMeta  // [String: String?]?

// From a PromptResult (modal/banner, after a goal event)
let deeplink   = result.value       // [String: Any?]?
let customMeta = result.meta        // [String: Any?]?
```

## Invisible prompts (metadata only)

Prompts of type `.INVISIBLE` carry no UI. They deliver metadata that's visible across all screens. Use `getMeta()` to read the merged metadata from all active invisible prompts.

```swift
let meta = PromptManager.shared.getMeta() // [String: Any]
```

## Send a custom tracking event

```swift
PromptManager.shared.customTrack(customFieldId: "YOUR_CUSTOM_TRACK_ID")
```

## Update the user ID

Change the user ID after initialization, for example when a user authenticates mid-session. Prompts refresh automatically within a few seconds.

```swift
PromptManager.shared.setUserId("NEW_USER_ID")
```

## Enable or disable prompts

Pause and resume all prompt display without re-initializing the SDK.

```swift
PromptManager.shared.enablePrompt(enabled: false) // pause
PromptManager.shared.enablePrompt(enabled: true)  // resume
```

## Reset suppression

Clear all suppressed prompt state and report a goal reset to Recurly Engage. This is useful for QA or when a user's subscription state changes.

```swift
PromptManager.shared.resetGoal()
```

## Push notifications (iOS only)

Add the `redfast-ui-push` product to your target. Integrate in this order:

1. `FirebaseApp.configure()`: optional, only if you use Firebase Cloud Messaging (FCM)
2. `PromptManager.initPrompt(...)`: must come before the push manager
3. `RedfastPushManager.shared.configure()`: requests permission and registers for remote notifications

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
* Swizzles `UIApplicationDelegate` push callbacks, so no manual forwarding is needed
* Posts the Apple Push Notification service (APNs) or FCM token to Recurly Engage
* Tracks push impression and goal events

Firebase/FCM support is enabled automatically when `FirebaseMessaging` is present in the host app.

See `Redflix/Redflix/redflixApp.swift` for a SwiftUI integration example using `@UIApplicationDelegateAdaptor`.

### Customize the notification action button

```swift
RedfastPushManager.shared.setCustomButton("Remind me later")
```

### Read the notification payload

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

On a successful purchase, the conversion goal is automatically reported to Recurly Engage.

**Local testing**: Redflix ships a `configurations.storekit` file. Use Xcode's StoreKit test environment to test purchases without hitting App Store servers.

## Claude skill

A Claude skill for this SDK is available for download at <a href="https://github.com/redfast/redfast-sdk-android/blob/main/SKILL.md" target="_blank">SKILL.md</a>. This skill enables Claude to assist with SDK integration, prompt configuration, and event handling in your Android application.

<br />
