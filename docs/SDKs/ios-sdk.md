---
title: iOS
excerpt: >-
  Configuration guide for the Recurly Engage iOS and tvOS SDK, enabling native
  prompt display and usage tracking in your mobile apps.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

The **Recurly Engage Apple SDK** provides native support for iOS and tvOS apps, automatically handling modal, banner, video popups, and inline prompt rendering, as well as tracking user-triggered events.

# Key benefits

* **SDK integration**: Seamlessly embed prompts and track user events in native iOS and tvOS applications.
* **Automatic UI handling**: Built-in support for modals, banners, and inline prompts without manual UI code.
* **Deep linking & metadata**: Leverage custom metadata and deep links for tailored in-app navigation.

# Key details

The Recurly Engage Apple SDK brings the ability to monitor consumption and show configured prompts within your native iOS and tvOS apps. The SDK automatically handles display of modals (popups, video popups, and banners) and the related user-triggered events. Inline prompts are accessible via helper functions with the necessary metadata for rendering in chosen areas of the app.

## Install the SDK

The Recurly Engage Apple SDK includes support for iOS and tvOS. The latest SDK version and example app source code are available [here](https://github.com/redfast/redfast-sdk-apple/releases). Contact your Customer Success Manager for access keys to run the example.

### Swift Package Manager

You may add the SDK from the public GitHub [repository](https://github.com/redfast/redfast-sdk-apple).

**Steps**:

1. **Add** a new Package Dependency to your existing project.

<Image align="center" className="border" border={true} src="https://files.readme.io/b69fc2ebde28f7ca810e40ffcc781d6eb0838fe6c859fe97c482ca0f1cd8cbac-Screenshot_2024-11-20_at_19.55.49.png" />

2. **Paste** the GitHub repo URL and select an appropriate Dependency Rule. Add to your project.

<Image align="center" className="border" border={true} src="https://files.readme.io/fa893cbcac4f982e312da89be3b511bec8b321c4c8f4fc7f53f660f30157edd8-Screenshot_2024-11-20_at_19.58.25.png" />

3. **Complete** adding the package.

<Image align="center" className="border" border={true} src="https://files.readme.io/76fdc54ab8b032fd78e26a3b5e14d80593d14279d6707f81b9e69747926936cf-Screenshot_2024-11-20_at_19.59.52.png" />

4. **Confirm** successful package installation.

<Image align="center" className="border" border={true} src="https://files.readme.io/9dcc3755e04a1a6daa30fd8f890f99fe420cc12675e2f918e70c2dce8fd88b6e-Screenshot_2024-11-20_at_20.02.19.png" />

### Legacy installation via local SDK

**Steps**:

1. In Xcode, **select** **Target > General > Frameworks, Libraries, and Embedded Content**, then **click** `+`.

2. **Choose** **Add Other > Add Files**, and **select** the `RecurlyEngage.xcframework`.

<Image align="center" className="border" border={true} width="50% " src="https://files.readme.io/0824267-Screenshot_2024-05-23_at_3.19.28_PM.png" />

3. **Ensure** the **Embed & Sign** option is selected.
4. **Import** the SDK into your project.

<Image align="center" className="border" border={true} width="70% " src="https://files.readme.io/ff07460-Screenshot_2024-05-23_at_3.22.56_PM.png" />

5. **Initialize** the SDK per instructions below.

## Initialize Recurly Engage

In `AppDelegate.swift`, add to `application(_:didFinishLaunchingWithOptions:)`—replace with your AppID and UserID (found under **Settings > Application** in Pulse):

````swift
func application(
   _ application: UIApplication,
   didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?
) -> Bool {
   PromotionManager.initPromotion(
     appId: "[Your AppID]",
     userId: "[Your UserID]"
   ) { result in
     // handle result
   }
   return true
}

## Trigger popup via screen name

Add inside your view controller’s `viewDidLoad()`:

```swift
override func viewDidLoad() {
    super.viewDidLoad()
    PromotionManager.setScreenName(self, "ViewController") { result in
        switch result.code {
        case .timerExpired, .declined, .abort, .accepted:
            // handle each case
            break
        default:
            break
        }
    }
}
````

## Trigger popup via button click

Add in your button’s `touchUpInside` handler:

```swift
@IBAction func buttonClicked(_ sender: Any) {
    PromotionManager.buttonClick(self, "unsubscribe") { [weak self] result in
        switch result.code {
        case .accepted, .declined, .timerExpired, .abort:
            // handle each case
            break
        default:
            break
        }
    }
}
```

## Retrieve inline prompts

Use async API to fetch inline prompts and report activities:

```swift
func fetchPrompts() async {
    if let prompt = PromotionManager
        .getTriggerablePrompts(screenName: "screenName", clickId: nil)
        .first 
    {
        // Access prompt properties
        try? await prompt.impression()
        try? await prompt.dismiss()
        // other events...
    }
}
```

## Deep link and custom metadata

* Deep links and custom metadata added in Pulse are available in callbacks for `setScreenName()`, `buttonClick()`, and `getTriggerablePrompts()`.
* Decode metadata using `prompt.deviceMeta?.decodeValue(to: Meta.self)`.

## Send Usage Tracking Event

```swift
Task {
    try? await PromotionManager.customTrack("[customTrackId]")
}
```

## Update user ID

Change the user ID mid-session after authentication:

```swift
PromotionManager.setUserId("[New UserID]")
```

## Debug view

Display the debug modal to reset or set a new user ID:

```swift
PromotionManager.showDebugView(self)
```