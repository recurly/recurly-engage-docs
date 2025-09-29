---
title: React Native
excerpt: >-
  Configuration guide for the Recurly Engage React Native SDK, enabling prompt
  rendering and event tracking in your React Native applications.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

The **Recurly Engage React Native SDK** provides components and APIs to render configured prompts—modals (popups, bottom banners, interstitials) and inline views—and handle related user interaction events in React Native apps.

# Key benefits

* **Cross-platform UI**: Seamlessly display modals and inline prompts on both iOS and Android via React Native.
* **Built-in interaction handling**: Automatically track impressions, clicks, dismissals, and other user events.
* **Customizable rendering**: Use prebuilt components or implement your own views based on prompt metadata.

# Key details

The Recurly Engage React Native SDK provides:

* A prompt manager for initialization and user ID management
* Hooks and components for displaying modal prompts and inline prompts
* APIs for reporting user interactions (impression, goal, decline, dismiss, timeout, holdout)

## Install the SDK

Add the following to your `.npmrc` or `.yarnrc.yml` file. Contact your Customer Success Manager for the AUTHTOKEN.

```
# .npmrc
@redfast:registry=https://npm.pkg.github.com
//npm.pkg.github.com/:_authToken=AUTHTOKEN

# .yarnyc.yml
npmAuthToken: "AUTHTOKEN"
```

### Install the package

**Using npm**

```shell
npm install @redfast/redfast-core
npm install @redfast/react-native-redfast
```

**or yarn**

```shell
yarn add @redfast/redfast-core
yarn add @redfast/react-native-redfast
```

## Initialize Engage

Initialize the SDK in your AppRoot.

```javascript
// Initialize the SDK, polling until init is complete
React.useEffect(() => {
  if (dispatch) {
    const promptMgr = new PromptManager(
      'YOUR_APP_ID',
      'INITIAL_USER_ID' // or null
    );
    const intervalId = setInterval(() => {
      if (promptMgr.isInitialized()) {
        dispatch({
          type: PromptAction_Init,
          data: promptMgr,
        });
        setReady(true);
        clearInterval(intervalId);
      }
    }, 1000);
    return () => clearInterval(intervalId);
  }
  return () => {};
}, [dispatch]);

// (optional) Utilize specific fonts for various parts of the prompts
useFonts({
  buttonFont: require('./assets/fonts/fontA.ttf'),
  otherFont: require('./assets/fonts/fontB.ttf'),
});

React.useEffect(() => {
  if (dispatch) {
    const promptMgr = new PromptManager(
      'YOUR_APP_ID',
      'INITIAL_USER_ID'
    );
    const intervalId = setInterval(() => {
      if (promptMgr.isInitialized()) {
        dispatch({
          type: PromptAction_Init,
          data: promptMgr,
        });
        dispatch({
          type: PromptAction_Font_Button,
          data: 'buttonFont',
        });
        dispatch({
          type: PromptAction_Font_Timer,
          data: 'otherFont',
        });
        dispatch({
          type: PromptAction_Font_LegalText,
          data: 'otherFont',
        });
        setReady(true);
        clearInterval(intervalId);
      }
    }, 1000);
    return () => clearInterval(intervalId);
  }
  return () => {};
}, [dispatch]);


```

## Set UserId

You may change the userID after the SDK has been initialized, for example, when the user authenticates mid session. Note that it may take several seconds for the user's prompts to refresh.

```javascript
promptMgr.setUserId(userId)
```

## Render modal prompts

Interstitial (mobile only), Popup and Bottom Banner modals may be triggered upon entering a screen and/or the user registering a click on an element. Add the following code to screens that are eligible to show a modal.

```javascript
// Import from Redfast SDK
import {
  usePrompt, // Prompt state management
  displayPrompt, // Modal prompts
  RedfastInline, // Inline prompts
} from '@redfast/react-native-redfast';

// Trigger when entering the "home" screen
const { path, delaySeconds } = await promptMgr.onScreenChanged("home");
if (path) {
  setTimeout(() => {
    setPathItem(path);
    setShowModal(true);
  }, delaySeconds);
}

// Or, trigger when "clickId" is clicked
const { path, delaySeconds } = await promptMgr.onButtonClicked("clickId");
if (path) {
  setTimeout(() => {
    setPathItem(path);
    setShowModal(true);
  }, delaySeconds);
}

// Display the modal UI for the path object returned above.
// params:
//   - showModal: a boolean to stipulate showing or hiding a Prompt
//   - path: a path object returned from one of the trigger calls above
//   - result: a callback returning PromptResult
displayPrompt(showModal, path, (result) => {
  console.log(JSON.stringify({ ...result, source: 'modal' }, null, 2));
  setShowModal(false);
})
```

## Render inline prompts

You may utilize the `RedfastInline` view to render an inline prompt, if one is available for the current user. Note the inline prompt will scale to fit within its container.

```javascript
<RedfastInline
  zoneId="myZoneId" // ZoneID as specified in Pulse
  closeButtonColor="#000000" // Hex color for close button, if enabled
  closeButtonBgColor="#FFFFFF" // Hex background color for close button
  closeButtonSize="20" // Close button height and width, in pixels
  timerFontSize="14" // Countdown timer font size, if enabled
  timerFontColor="#FFFFFF" // Countdown timer font hex color
  onEvent={(result) =>}
/>

```

## Custom prompt rendering

You may opt to render prompts utilizing the prompt metadata in cases where the desired rendering is different than that produced by the Redfast SDK.

The app should report Prompt interactions via the provided functions on the prompt object.

```javascript
// Example: Retrieve all available prompts of specified type. See PathType values below. Use this if trigger criteria is to be ignored.
let prompts = promptMgr.getPrompts(PathType.ALL);

// Example: Retrieve all available prompts of specified type and trigger criteria (screenName `homeScreen`)
let prompts = promptMgr.getTriggerablePrompts('home_screen','*', PathType.ALL );

// Example: Retrieve all available prompts of specified type and trigger criteria (screenName `homeScreen` and clickId `add_to_watchlist`)
let prompts = promptMgr.getTriggerablePrompts('home_screen','add_to_watchlist', PathType.ALL );

// Access prompt properties (See below for Prompt interface details)
prompt.button1
prompt.button2
prompt.button3
prompt.inAppSku
promot.deeplink
prompt.deviceMeta

// Report prompt interactions
prompt.impression() // prompt shown to user
prompt.goal() // user clicks on primary CTA
prompt.goal2() // user clicks on secondary CTA
prompt.decline() // user clicks on decline (3rd) button
prompt.dismiss() // user dismisses prompt by clicking on "x" close button
prompt.timeout() // prompt is dismissed via countdown timer
promot.holdout() // prompt is triggered, however the user is in the Control group so prompt should not be shown

/* 
PathType values:
  PathType.ALL = -1
  PathType.MODAL = 2 // Referenced as Popup within Pulse
  PathType.HORIZONTAL = 5
  PathType.TEXT = 7
  PathType.VERTICAL = 8
  PathType.TILE = 9
  PathType.INTERSTITIAL = 10
  PathType.BOTTOM_BANNER = 13
  
PromptResultCode values:
  // Success codes
  OK = 1,
  // Error codes
  ERROR = -100,
  NOT_APPLICABLE = -101,
  DISABLED = -102,
  SUPPRESSED = -103,
  // Interactions
  IMPRESSION = 100,
  BUTTON1 = 101, // CLICK
  BUTTON2 = 102, // CLICK2
  BUTTON3 = 103, // DECLINE
  DISMISS = 110,
  TIMEOUT = 111,
  HOLDOUT = 120

interface Prompt {
  id: string;
  type: PathType;
  actions: Action;
  actionGroupId?: string;
  inAppSku?: string;
  deviceMeta?: { [key: string]: any };
  deeplink?: { [key: string]: any };
  button1?: ModalButton;
  button2?: ModalButton;
  button3?: ModalButton;
  buttonBorderRadius: number;
  buttonBorderColor: string;
  buttonBorderThickness: number;
  countDownPrompt: string;
  countDownPromptColor: string;
  countDownPromptFontSize: number;
  countDownPromptInvisible: boolean;
  countDown: number;
  horizontalPoster?: string;
  impression: () => Promise<PromptResult>;
  dismiss: () => Promise<PromptResult>;
  timeout: () => Promise<PromptResult>;
  holdout: () => Promise<PromptResult>;
  goal: () => Promise<PromptResult>;
  goal2: () => Promise<PromptResult>;
  decline: () => Promise<PromptResult>;
}

interface ModalButton {
  label?: string;
  textColor?: string;
  textHightlightColor?: string;
  bgColor?: string;
}
*/
```

## Actions

When a user interacts with the primary prompt CTA, a result callback includes various metadata associated with the Prompt to determine the client-side action that should take place.

```javascript
// Data schema of the result callback
interface PromptResult {
  code: PromptResultCode;
  value?: { [key: string]: any };
  meta?: { [key: string]: any };
  promptMeta?: {
    promptName: string;
    promptID: string;
    promptVariationName: string;
    promptVariationID: string;
    promptExperimentName: string;
    promptExperimentID: string;
    buttonLabel: string;
  };
}
```

### Analytics callback example

```javascript
<RedfastInline
  zoneId="myZoneId" // ZoneID as specified in Pulse
  closeButtonColor="#000000" // Hex color for close button, if enabled
  closeButtonBgColor="#FFFFFF" // Hex background color for close button
  closeButtonSize="20" // Close button height and width, in pixels
  timerFontSize="14" // Countdown timer font size, if enabled
  timerFontColor="#FFFFFF" // Countdown timer font hex color
  onEvent={(result) => {
    const getEventName = (code: PromptResultCode) => {
      switch (code) {
        case PromptResultCode.IMPRESSION:
          return 'Redfast Impression';
        case PromptResultCode.BUTTON1:
          return 'Redfast Click';
        case PromptResultCode.BUTTON2:
          return 'Redfast Click2';
        case PromptResultCode.BUTTON3:
          return 'Redfast Decline';
        case PromptResultCode.DISMISS:
          return 'Redfast Dismiss';
        case PromptResultCode.TIMEOUT:
          return 'Redfast Timeout';
        case PromptResultCode.HOLDOUT:
          return 'Redfast Holdout';
        default:
          return 'Redfast Event';
      }
    };

    const analyticsData = {
      name: getEventName(result.code),
      data: {
        ...result.promptMeta,
        timestamp: new Date().toISOString()
      }
    };
    console.log('ANALYTICS:', JSON.stringify(analyticsData, null, 2));
    /* Example:
      ANALYTICS: {
        "name": "Redfast Click",
        "data": {
          "promptName": "My Prompt Name",
          "promptID": "438c8eec-1111-1111-1111-2222",
          "promptVariationName": "Varation 2",
          "promptVariationID": "438c8eec-1111-1111-1111-2222",
          "promptExperimentName": "My Experiment",
          "promptExperimentID": "438c8eec-1111-1111-1111-3333",
          "promptType": 5,
          "buttonLabel": "Sign me up",
          "timestamp": "2025-02-12T05:41:28.365Z"
        }
      }
    */

    // Send Payload to Analytics
  }}
/>

// Perform the same for modals
{displayPrompt(showModal, pathItem, (result) => {
  // utilize same analytics code above
  setShowModal(false);
})}


```

### Deeplink

You can add a Deeplink to a Prompt within Pulse. When the user invokes the CTA, you can utilize the Deeplink to send the user to a specific location within the app.

```javascript
{
  "code": 0,
  "meta": {
    "meta": {},
    "deeplink": "redflix://test123"
  },
}
```

### In-app purchase

An In-App Purchase product SKU may be configured on the prompt, which indicates that the user should be sent to the In-App Purchase flow for the specified SKU  once the primary CTA has been selected.

### Custom metadata

Custom key-value pairs can be added to an item via Pulse. These values may be used to perform an action that is not the typical media asset deep link, like sending the user to a registration screen or performing an operation on behalf of the user.

```javascript
{
  "code": 0,
  "meta": {
    "meta": {
      "keyName1": "foo",
      "keyName2": "bar",
      "differentKey": "baz"
    },
  },
}
```

## Send usage tracking event

Your app can send custom track events using the SDK. If configured as a tracker within Pulse, these custom events can be used to target prompts at specific sets of users.

```javascript
promptMgr.customTrack(customFieldId)
```

## Debugging

You may reset the current user's prompt status, such that previously suppressed prompts will now be made available.

```javascript
promptMgr.resetGoal()
```

<br />
