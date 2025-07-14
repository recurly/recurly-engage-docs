---
title: Roku
excerpt: >-
  Configuration guide for the Recurly Engage Roku SDK, which enables native
  prompt display and usage tracking in your Roku applications.
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

The **Recurly Engage Roku SDK** provides the ability to monitor consumption and show configured prompts within your native Roku app. The SDK automatically handles prompt display and user-triggered events.

# Key benefits

* **Seamless integration**: Easily add prompt functionality to your Roku apps via the Roku SceneGraph SDK.
* **Automatic event handling**: Built-in support for prompt display, button clicks, and lifecycle events without extra UI code.
* **Flexible triggers**: Activate prompts by screen name or button click to fit your application flow.

# Key details

## Install the SDK

Download the latest Roku SDK (v1.0.25) with Roku Pay support [here](https://assets.redfastlabs.com/sdk/roku-sdk-1.0.25.zip) or without Roku Pay support [here](https://assets.redfastlabs.com/sdk/roku-sdk-noiap-1.0.25.zip). A demo app featuring an example integration is available on request.

To build your project with the Recurly Engage Roku SDK, ensure it’s using the Roku SceneGraph SDK, then unzip the SDK into your app’s `components` directory.

## Initialize SDK

1. In your main scene XML file, add the PromotionManager node:

   ```xml
   <PromotionManager id="promoMgr" />
   ```

2. In the main BrightScript (`.brs`) file’s `sub init()` function, initialize and observe:

   ```brightscript
   sub init()
     m.promoMgr = m.top.findNode("promoMgr")
     m.promoMgr.observeField("result", "onInitialized")
     m.promoMgr.callFunc("initPromotion", {appId: "[YOUR APP ID]", userId: "[USER ID]"})
   end sub

   sub onInitialized()
     m.promoMgr.unobserveField("result")
     m.sceneStack = m.top.findNode("sceneStack")
     scene = createObject("RoSGNode", "[YOUR_FIRST_SCREEN]")
     m.sceneStack.appendChild(scene)
   end sub
   ```

   > It may take a few seconds after startup for initialization to complete.

3. To obtain the manager instance in other screens:

   ```brightscript
   sub init()
     m.promoMgr = m.top.GetScene().findNode("promoMgr")
   end sub
   ```

## Set UserId

Change the user ID at any time; prompts update after a short delay:

```brightscript
m.promoMgr.callFunc("setUserId", {userId: "[NEW_USER_ID]"})
```

## Trigger popup via screen name

In the screen’s init, observe and call:

```brightscript
sub init()
  m.promoMgr.observeField("result", "onPromotionEvent")
  m.promoMgr.callFunc("onScreenChanged", {root: m.viewRoot, screenName: "HomeScreen"})
end sub
```

> Ensure the `observeField("result", ...)` listener is registered before calling.

## Trigger popup via button click

After an `onScreenChanged` call, trigger on click:

```brightscript
sub onButtonClicked()
  m.promoMgr.callFunc("onButtonClicked", {root: m.viewRoot})
end sub
```

Handle the result in your callback:

```brightscript
sub onModalDismissed()
  if m.promoMgr.result.value = 101 ' button1
    dialog = createObject("roSGNode", "Dialog")
    dialog.title = "Thank you"
    dialog.optionsDialog = true
    dialog.message = "Thanks for accepting"
    m.top.dialog = dialog
  end if
end sub
```

> See status codes in `const.brs` for full list.

## Retrieve inline prompts

Fetch inline items eligible for a zone ID:

```brightscript
inlineItems = m.promoMgr.callFunc("getInlines", {type: "myZoneId"})
```

Then render each item’s properties (e.g. `rf_settings_bg_image_roku_os_tv_composite`, `rf_retention_title`, etc.)—see [Prompt Attributes](/reference/prompt-attributes#/) for full details.

## Send usage tracking event

Report custom tracker events (configured in Pulse):

```brightscript
m.promoMgr.callFunc("customTrack", {customFieldId: "my-usage-event"})
```

## Deep link to a media asset

Enable Roku deep linking by specifying `mediaType` and `contentId` in Pulse. Handle in your promotion event:

```brightscript
sub onPromotionEvent()
  if m.promoMgr.result.value = 1 ' accepted
    deeplink = m.promoMgr.result.extra.deeplink
    handleDeepLink(deeplink)
  end if
end sub
```

## Access device metadata

* **Popup**: Retrieved in `result.extra.meta` after accept, decline, or timeout.
* **Inline**: Retrieved in `result.extra.meta` on inline click.

```brightscript
metadata = m.promoMgr.result.extra.meta
```

## Disable SDK

Pause or resume prompts and network calls:

```brightscript
// Disable
m.promoMgr.callFunc("enablePromotion", {enabled: false})
// Re-enable
m.promoMgr.callFunc("enablePromotion", {enabled: true})
```

## Debug view

Add the debug component to your main scene:

```xml
<DebugView id="debugView" />
```

Then trigger on remote key:

```brightscript
m.debugView = m.top.findNode("debugView")
sub onKeyEvent(key as String)
  if key = "*" then
    m.debugView.callFunc("onKeyDetection", {key: key, screen: m.top})
  end if
end sub
```