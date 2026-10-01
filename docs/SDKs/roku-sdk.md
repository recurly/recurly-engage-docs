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
<div class="rp-page">
  <div class="rp-overview">The Recurly Engage Roku software development kit (SDK) lets you monitor consumption and show configured prompts within your native Roku app. The SDK automatically handles prompt display and user-triggered events.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">1</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">2</span>Key details</a>
  </div>
</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-plug" aria-hidden="true"></i></div>
    <strong>Simple integration</strong>
    <span>Add prompt functionality to your Roku apps through the Roku SceneGraph SDK.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-wand-magic-sparkles" aria-hidden="true"></i></div>
    <strong>Automatic event handling</strong>
    <span>Built-in support for prompt display, button clicks, and lifecycle events without extra UI code.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-bolt" aria-hidden="true"></i></div>
    <strong>Flexible triggers</strong>
    <span>Activate prompts by screen name or button click to fit your application flow.</span>
  </div>
</div>

# Key details

## Install the SDK

Download the latest Roku SDK (v1.0.49) <a href="https://assets.redfastlabs.com/sdk/roku-sdk-1.0.49.zip" target="_blank">with Roku Pay support</a> or <a href="https://assets.redfastlabs.com/sdk/roku-sdk-noiap-1.0.49.zip" target="_blank">without Roku Pay support</a>. A demo app with an example integration is available by request.

To build a project using the Recurly Engage SDK for Roku, your project must have been built with the SceneGraph SDK. Unzip the SDK into the app `components` directory.

## Initialize the SDK

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Initialize in the main scene XML</h4><p>Initialize the SDK within the main scene XML (initial screen) file.</p></div>
  </div>
</div>

```xml
 < PromotionManager id="promoMgr" />
```

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Add the initialization code</h4><p>Within the main scene BrightScript (<code>.brs</code>) file, add the following lines into the <code>sub init()</code> function, and specify the values for the appId and userId. The userId may be changed later on.</p></div>
  </div>
</div>

\[TODO: Dev/PO review — possible issue: the `initPromotion` call below uses the key `annonymousUserId` (double n). Left verbatim.]

```brightscript
sub init()
  ' other app initialization code here

  ' optionally specify cta-button and timer countdown fonts
  ctaF = CreateObject("roSGNode", "Font")
  ctaF.uri = "pkg:/fonts/Roboto-Regular.ttf"
  ctaF.size = 16
  timeoutF = CreateObject("roSGNode", "Font")
  timeoutF.uri = "pkg:/fonts/Roboto-Regular.ttf"
  timeoutF.size = 16

  m.promoMgr = m.top.GetScene().findNode("promoMgr") ' or m.top.findNode("promoMgr")
  print m.promoMgr.callFunc("getVersion") ' lookup current SDK version
  m.promoMgr.observeField("result", "onInitialized")
  ' appId argument is required, all others are optional
  m.promoMgr.callFunc("initPromotion", {appId: "[YOUR APP ID]", userId: "[USER ID]", annonymousUserId: "[ANON USER ID]", ctaFont: ctaF, timeoutFont: timeoutF})
end sub

sub onInitialized()
  m.promoMgr.unobserveField("result")
  m.sceneStack = m.top.findNode("sceneStack")
  scene = createObject("RoSGNode", "[YOUR FIRST SCREEN OF THE APP]")
  m.sceneStack.appendChild(scene)
end sub
```

It may take a few seconds after app start for the SDK initialization to complete. After that, prompts are available to present to the user.

## Set the user ID

You can change the userId after the SDK has been initialized. The function returns instantly, but all prompts relevant to the updated userId may take a few seconds to be ready.

```brightscript
m.promoMgr.callFunc("setUserId", {userId: "[new user id]"})
```

## Set the anonymous user ID

You can update the anonymousUserId after the SDK has been initialized. If you don't set it, the SDK assigns the user a randomly generated universally unique identifier (UUID).

```brightscript
m.promoMgr.callFunc("setAnonymousUserId", {userId: "[new anon user id]"})
```

## Set privacy consent categories

You can configure prompts in Pulse to require one or more privacy consent categories. To restrict which prompts are eligible to be shown, specify the categories the user has consented to (for example, after they interact with a cookie or privacy consent banner). A prompt is only considered eligible when its configured consent categories are an exact match (the same set) of the categories you specify here.

If `setPrivacyConsentCategories` is never called, consent filtering is disabled and all prompts remain eligible regardless of their configured consent categories.

```brightscript
' Supported category values, see `PrivacyConsentCategory()` in the SDK `consts.brs` file:
' m.strictlyNecessary = "strictly_necessary"
' m.performance = "performance"
' m.functional = "functional"
' m.targeting = "targeting"

m.promoMgr.callFunc("setPrivacyConsentCategories", {categories: ["strictly_necessary", "performance"]})
```

You can retrieve the currently set categories at any time:

```brightscript
categories = m.promoMgr.callFunc("getPrivacyConsentCategories")
```

## Supported prompt types

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Prompt type</td><td>Enum value</td></tr>
  <tr><td>Modal</td><td>2</td></tr>
  <tr><td>Horizontal</td><td>5</td></tr>
  <tr><td>Video</td><td>6</td></tr>
  <tr><td>Interstitial</td><td>10</td></tr>
  <tr><td>Bottom banner</td><td>13</td></tr>
</table>

## Trigger a modal via screen name

You can use the SDK to display a modal on a specified screen. If the prompt also requires a button click, the trigger doesn't occur until the associated `onButtonClicked` function is called.

Add the following lines in the screen `init` function:

\[TODO: Dev/PO review — possible issue: the example below uses `//` comments and the typo "registed", and BrightScript comments normally start with an apostrophe. Left verbatim.]

```brightscript
sub init()
  ...
  m.promoMgr = m.top.GetScene().findNode("promoMgr")
  // Make sure a callback function is registed (and registed for only once) here to receive any status from m.promoMgr
  // A sample onPromotionEvent is provided in the next section
  m.promoMgr.observeField("result", "onPromotionEvent")
  m.promoMgr.callFunc("onScreenChanged", {root: m.viewRoot, screenName: "ViewController" })
  ...
end sub
```

Make sure you add an event listener before calling any function on `m.promoMgr`, so that you can observe the result from a screen change, button click, popup, or inline item:

```brightscript
  m.promoMgr.observeField("result", "onPromotionEvent")
```

## Trigger a modal via button click

The sample code below demonstrates:

1. Tracking a button click event
2. Displaying a modal, if one applies to the button

A previous `onScreenChanged` call is required if the prompt trigger is configured to be invoked only when the button click occurs on a specified screen name.

```brightscript
sub onButtonClicked()
  m.promoMgr.callFunc("onButtonClicked", {root: m.viewRoot 'the root component of the screen, id: "[Optional button ID]"}) 
end sub
                                          
'Note: If the prompt is displayed and dismissed, the result will be passed back to:
sub onModalDismissed()
  if m.promoMgr.result.value = 101 'button1
    dialog = createObject("roSGNode", "Dialog")
    dialog.title = "Thank you"
    dialog.optionsDialog = true
    dialog.message = "Thanks for accepting"
    m.top.dialog = dialog
  end if
end sub

' Note: The full set of status codes can be found in the SDK `const.brs` file:
' Success codes
m.ok = 1

' Error codes
m.error = -100
m.notApplicable = -101
m.disabled = -102
m.suppressed = -103

' Interactions
m.impression = 100
m.button1 = 101
m.button2 = 102
m.button3 = 103
m.dismissed = 110
m.timerExpired = 111
m.holdout = 120

```

## Show a modal via manual trigger

You can trigger a prompt manually if triggering by screen name or button click isn't what you want.

```brightscript
prompt = m.promoMgr.callFunc("getPrompt", {pathId: "myPathId"})
m.promoMgr.callFunc("showPrompt", {root: m.viewRoot, prompt: prompt})
```

## Show an inline prompt

An eligible inline prompt can be rendered within a SceneGraph node. We recommend defining a Rectangle or Poster node as a container for the inline prompt. The `scale` argument determines how the inline prompt scales to fit within the allocated space of the specified node.

```
' -- Scenegraph component file (.xml) --
<Rectangle id="myBanner" width="1920" height="420" />
  
' -- Brightscript file (.brs) --

' showInline Args:
'   root: parent node
'   type: Zone ID
'   scale: "scaleToFit", "scaleToFill", "scaleToZoom", "noScale"
m.inline = m.promoMgr.callFunc("showInline", {root: m.myBanner, type: "myZoneId", scale: "scaleToFill"
})
' Observe Prompt Interactions
if m.inline <> invalid
  m.inline.observeField("result", "onInlineResult")
end if

```

## Retrieve inline prompts

For custom rendering, the SDK provides a method to retrieve the inline prompts in the specified Zone ID that are eligible for the current userId. You can access the properties of the inline prompts to render them in the appropriate locations within the app.

```brightscript
inlineItems = m.promoMgr.callFunc("getInlines", {type: "myZoneId"})
```

The following example code accesses attributes of the prompt for rendering within a new child node. You can find the full list of attributes <a href="/reference/prompt-attributes#/" target="_blank">here</a>.

```brightscript
featured = createObject("RoSGNode", "ContentNode")
di = CreateObject("roDeviceInfo")
displaySize = di.GetDisplaySize()
for ii = 0 To inlineItems.count() - 1
    item = featured.createChild("ContentNode")
    inlineItem = inlineItems[ii]
    heightSuffix = ""
    if displaySize.h = 480
        heightSuffix = "&screen_size=480"
    else if displaySize.h = 720
        heightSuffix = "&screen_size=720"
    end if
    item.HDPOSTERURL = inlineItem.actions.rf_settings_bg_image_roku_os_tv_composite + heightSuffix
end for
featured.title = "Featured"
contentNode.insertChild(featured, 2)
```

Prompt interactions for inline prompts must be reported within your application code.

```brightscript
' Report impression when inline prompt is viewed
promoMgr.onInlineViewed(inlineItem)

' Report click
promoMgr.onInlineClicked(inlineItem)

' Report dismiss
promoMgr.onInlineDismissed(inlineItem)
```

## Respond to prompt interactions

The SDK returns a PromptResult object upon any prompt interaction performed by the user.

The PromptResult schema includes the following properties:

* `code`: Interaction code (for example, 100 for impression, 101 for button1 click)
* `meta`: Device metadata specified within the prompt
* `promptMeta`
  * `promptName`
  * `promptID`
  * `promptType`
  * `promptVariationName`
  * `promptVariationID`
  * `promptExperimentName`
  * `promptExperimentID`
  * `buttonLabel`

```brightscript
' Observe Prompt Interactions
m.promoMgr.observeField("result", "onPromptResult")

' Perform actions on resulting interaction
sub onPromptResult()
		' Call custom sendAnalytics() function
    sendAnalytics(m.promoMgr.result)

		' Kick off Roku Pay flow for specified SKU if specified
    if  m.promoMgr.result.roku <> invalid and m.promoMgr.result.roku <> ""
        m.promoMgr.callFunc("purchaseIap", {sku: m.promoMgr.result.roku, qty: 1})
    else
        if m.modal.visible
            m.detail.setFocus(true)
        else
            m.home.setFocus(true)
        end if
    end if
end sub

```

## Send a usage tracking event

Your app can report custom tracker events through the SDK. If you configure a tracker in Pulse, you can use these custom events to target prompts at specific sets of users. Create the custom tracker in Pulse first, so you can retrieve the `customFieldId` value.

```brightscript
m.promoMgr.callFunc("customTrack", {customFieldId: "my-usage-event"})
```

## Deep link to a media asset

Invoke the Roku app <a href="https://developer.roku.com/docs/developer-program/discovery/implementing-deep-linking.md" target="_blank">deep linking</a> functionality by specifying the mediaType and contentId for the prompt in Pulse. When the user selects the call-to-action (CTA) on the prompt, you can use these parameters to send the user to a specific media asset within the app. The following example shows how to invoke deep linking after the user selects the CTA.

```brightscript
sub onPromotionEvent()
  if m.promoMgr.result.value = 0 // m.accepted from `const.brs` file
    deeplink = m.promoMgr.result.extra.deeplink
    [your deeplink handler function](deeplink)
  end if
end sub
```

## Access device metadata

You can add device key-value pair metadata to a prompt in Pulse. The app receives these values as shown in the examples below. You can use them to perform an action other than the typical media asset deep link, like sending the user to a registration screen.

### Popup

When the user dismisses a popup with an Accept, Decline, or Timeout action, the custom metadata is saved in the `extra.meta` field.

```brightscript
sub onPromotionEvent()
  metadata = m.promoMgr.result.extra.meta
end sub
```

### Inline item

When the `onInlineClicked` API is invoked with the currently selected inline item:

```brightscript
sub onPromotionEvent()
  metadata = m.promoMgr.result.extra.meta
end sub
```

## Prompt type enum values

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Enum prompt type</td><td>Integer value</td></tr>
  <tr><td>all</td><td>-1</td></tr>
  <tr><td>invisible</td><td>1</td></tr>
  <tr><td>modal</td><td>2</td></tr>
  <tr><td>horizontal</td><td>5</td></tr>
  <tr><td>video</td><td>6</td></tr>
  <tr><td>interstitial</td><td>10</td></tr>
  <tr><td>bottom banner</td><td>13</td></tr>
</table>

## Disable the SDK

In some cases, you may need to temporarily disable the SDK for the current session. When the SDK is disabled, popups aren't triggered, and API communication between the SDK and Recurly Engage servers is paused.

```brightscript
// To disable
m.promoMgr.callFunc("enablePromotion", {enabled: false})

// To re-enable
m.promoMgr.callFunc("enablePromotion", {enabled: true})
```

## Debug view

The SDK provides a debug view modal. Use the onscreen keyboard to reset all prompts for the current user, set a new userId, or set the active privacy consent categories (a comma-separated list, for example, `strictly_necessary,performance`; leave it blank to disable consent filtering).

To trigger the debug view for a specific screen, add the `DebugView` component and connect it to a local variable on the screen:

```
<DebugView id="debugView" />

m.debugView = m.top.findNode("debugView")
```

In the screen's `onKeyEvent` function:

```brightscript
m.debugView.callFunc("onKeyDetection", {key: key, screen: m.top})
```

When the `*` key on the remote control is pressed, the debug view is displayed.

## Claude skill

A Claude skill for this SDK is available for download at <a href="https://github.com/recurly/redfast-sdk-roku/blob/main/docs/SKILL.md" target="_blank">SKILL.md</a>. This skill enables Claude to assist with SDK integration, prompt configuration, and event handling in your Roku application.
