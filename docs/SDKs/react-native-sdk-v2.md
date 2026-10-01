---
title: React Native (V2)
excerpt: >-
  How to install, initialize, and integrate the Recurly Engage React Native SDK
  to render prompts and track user interaction events in iOS and Android
  applications.
deprecated: false
hidden: false
metadata:
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">Use the Recurly Engage React Native software development kit (SDK) to render prompts and handle user interaction events in your React Native app on iOS and Android.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>A Recurly Engage account with a valid App ID</li>
  <li>A React Native project targeting iOS and/or Android</li>
</ul>

### Limitations

* Inline prompts scale to fit within their container, so size your container accordingly
* It may take several seconds for prompts to refresh after calling `setUserId()`
* `<PromptOverlay />` must be placed at the bottom of your app node to ensure correct Z-order

# Definition

<div class="rp-definition">The Recurly Engage React Native SDK provides components and APIs to render configured prompts, including modals (popups, bottom banners, and interstitials) and inline views, and to handle related user interaction events in React Native apps.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-mobile-screen-button" aria-hidden="true"></i></div>
    <strong>Cross-platform UI</strong>
    <span>Display modals and inline prompts on both iOS and Android through React Native with a single integration.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-hand-pointer" aria-hidden="true"></i></div>
    <strong>Built-in interaction handling</strong>
    <span>Automatically track impressions, clicks, dismissals, and other user events without manual wiring.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-paintbrush" aria-hidden="true"></i></div>
    <strong>Customizable rendering</strong>
    <span>Use prebuilt components, or implement your own views based on prompt metadata.</span>
  </div>
</div>

# Key details

The Recurly Engage React Native SDK provides:

* A prompt manager for initialization and user ID management
* Hooks and components for displaying modal prompts and inline prompts
* APIs for reporting user interactions (impression, goal, decline, dismiss, timeout, holdout)

## Install the SDK

The SDK is published on the public npm registry. No registry configuration or authentication token is required.

**npm**

```bash
npm install @recurly/engage-core
npm install @recurly/engage-react-native
```

**Yarn**

```bash
yarn add @recurly/engage-core
yarn add @recurly/engage-react-native
```

<div class="rp-callout rp-callout-important">
  <div><strong><i class="fa-solid fa-circle-exclamation" aria-hidden="true"></i> Important</strong>Also install <code>@react-native-async-storage/async-storage</code>. <code>@recurly/engage-react-native</code> depends on it, but React Native's autolinking only picks up native modules declared directly in your app's <code>package.json</code>, not transitive dependencies. Add it to your own <code>package.json</code> as well (matching the version range <code>@recurly/engage-react-native</code> depends on), or you'll see <code>NativeModule: AsyncStorage is null</code> at runtime.</div>
</div>

```bash
npm install @react-native-async-storage/async-storage
```

## Initialize Engage

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Add the PromptProvider</h4><p>Initialize the SDK in your AppRoot using the <code>&lt;PromptProvider&gt;</code> component at the top of your app node.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Check that the SDK is initialized</h4><p>Pull the SDK to check it has been initialized, using the <code>usePrompt</code> hook and the <code>promptMgr.isInitialized()</code> method.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Add the PromptOverlay</h4><p>Place a <code>&lt;PromptOverlay /&gt;</code> component at the bottom of your app node. It renders any modal (interstitial, popup, bottom banner) prompts that are triggered. Because it's at the bottom of your app node, it has the highest Z-order to show itself.</p></div>
  </div>
</div>

```javascript
// Initialize the SDK at the top of your app node
export default function App() {
  return (
    <PromptProvider appId="YOUR_APP_ID" userId="INITIAL_USER_ID">
      <AppRoot />
    </PromptProvider>
  );
}

// pull the SDK to check it has been initialized
const AppRoot: React.FC = () => {
  const {
    dispatch,
    state: { promptMgr },
  } = usePrompt();
  const [isReady, setReady] = React.useState(false);

  React.useEffect(() => {
    if (!promptMgr) return;
    const intervalId = setInterval(() => {
      if (promptMgr.isInitialized()) {
        setReady(true);
        clearInterval(intervalId);
      }
    }, 1000);
    return () => clearInterval(intervalId);
  }, [promptMgr]); // eslint-disable-line react-hooks/exhaustive-deps

  return (
    <NavigationContainer>
      {isReady && (
        <Stack.Navigator screenOptions={{ headerShown: true }}>
          <Stack.Screen />
          <Stack.Screen />
          ...
        </Stack.Navigator>
      )}
      <PromptOverlay
        onEvent={(result: PromptResult) => {
          // TODO: handle the result
        }}
      />
    </NavigationContainer>
  );
}

// (optional) You can load the SDK with specific fonts for various parts of the prompts
const AppRoot: React.FC = () => {
  ...
  useFonts({
    buttonFont: require('../assets/fonts/AllProDisplayC-Bold.ttf'),
    otherFont: require('../assets/fonts/AllProDisplayC-Regular.ttf'),
  });

  React.useEffect(() => {
    if (!promptMgr) return;
    const intervalId = setInterval(() => {
      if (promptMgr.isInitialized()) {
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
  }, [promptMgr]); // eslint-disable-line react-hooks/exhaustive-deps

  ...
}
```

## Set the user ID

You can change the user ID after the SDK has been initialized, for example, when the user authenticates mid-session. It may take several seconds for the user's prompts to refresh.

```javascript
promptMgr.setUserId(userId);
```

## Privacy consent categories

If your app gates data collection behind a consent banner or preference center, you can restrict which prompts are eligible to show based on the consent categories the user has granted. Prompts configured in Pulse with `consent_categories` are only shown once the categories you set match exactly.

```javascript
import { PrivacyConsentCategory } from '@recurly/engage-core';

// Set the categories the user has consented to (e.g. from your consent banner)
promptMgr.setPrivacyConsentCategories([
  PrivacyConsentCategory.strictlyNecessary,
  PrivacyConsentCategory.performance,
]);

// Read back the categories currently set
promptMgr.getPrivacyConsentCategories();

/*
Available categories:
  PrivacyConsentCategory.strictlyNecessary // 'strictly_necessary'
  PrivacyConsentCategory.performance       // 'performance'
  PrivacyConsentCategory.functional        // 'functional'
  PrivacyConsentCategory.targeting         // 'targeting'
*/
```

Matching behavior:

* Before `setPrivacyConsentCategories` is called, no filtering is applied. All prompts remain eligible regardless of their `consent_categories`.
* Once the categories are set, a prompt is only eligible when its `consent_categories` are an exact match (same categories, order doesn't matter) to the categories you set. A prompt configured without `consent_categories` never matches once any categories have been set.
* The filter applies everywhere prompts are resolved: `screenChanged` / `buttonClicked` triggering, inline zones (`getInlines` / `<RecurlyInline>`), and custom rendering (`getPrompts`, `getTriggerablePrompts`).
* Whenever consent changes (for example, the user updates their preferences), call `setPrivacyConsentCategories` again and re-trigger the current screen (`promptMgr.screenChanged(currentScreen)`) so eligibility is re-evaluated.

## Render modal prompts

Interstitial, Popup, and Bottom Banner modals can be triggered when the user enters a screen and/or registers a click on an element. Add the following code to screens that are eligible to show a modal.

Use the `promptMgr.screenChanged('home')` method for entering a screen with a screen name (a customer-defined string, for example, `"home"`).

Use the `promptMgr.buttonClicked('clickId')` method for registering a click on an element (a customer-defined string, for example, a button with an id of `"clickId"`).

```javascript
// Example a screen
import {
  usePrompt, // Prompt state management
} from '@recurly/engage-react-native';

// Example: trigger when entering the "home" screen
export default function HomeScreen() {
  const {
    dispatch,
    state: { promptMgr },
  } = usePrompt();

  React.useEffect(() => {
    if (promptMgr) {
      promptMgr.screenChanged('home');
    }
  }, [promptMgr]);

  return (
    // Example: trigger when a button is clicked
    <TouchableOpacity
      onPress={async () => {
        if (promptMgr) {
          promptMgr.buttonClicked('clickId');
        }
      }}
    >Hello</TouchableOpacity>
  );
}
```

## Render inline prompts

Use the `RecurlyInline` view to render an inline prompt if one is available for the current user. The inline prompt scales to fit within its container.

```javascript
<RecurlyInline
  zoneId="myZoneId" // ZoneID as specified in Pulse
  closeButtonColor="#000000" // Hex color for close button, if enabled
  closeButtonBgColor="#FFFFFF" // Hex background color for close button
  closeButtonSize="20" // Close button height and width, in pixels
  timerFontSize="14" // Countdown timer font size, if enabled
  timerFontColor="#FFFFFF" // Countdown timer font hex color
  focusStyle={{
    borderWidth: 2,
    borderColor: '#ff0000',
    borderRadius: 5,
  }}
  onEvent={(result) => {}}
/>
```

## Custom prompt rendering

If you want to render prompts differently from what the SDK produces by default, you can render them using the prompt metadata.

Your app should report prompt interactions through the provided functions on the prompt object.

\[TODO: Dev/PO review — possible issue: the example below uses `promot.deeplink` and `promot.holdout()` ("promot" instead of "prompt"), and its comments mention `homeScreen` while the code uses `'home_screen'`. Left verbatim.]

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

When a user interacts with the primary prompt call-to-action (CTA), a result callback includes various metadata associated with the prompt. Use it to determine the client-side action that should take place.

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

## Analytics callback example

```javascript
<RecurlyInline
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
          return 'Engage Impression';
        case PromptResultCode.BUTTON1:
          return 'Engage Click';
        case PromptResultCode.BUTTON2:
          return 'Engage Click2';
        case PromptResultCode.BUTTON3:
          return 'Engage Decline';
        case PromptResultCode.DISMISS:
          return 'Engage Dismiss';
        case PromptResultCode.TIMEOUT:
          return 'Engage Timeout';
        case PromptResultCode.HOLDOUT:
          return 'Engage Holdout';
        default:
          return 'Engage Event';
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
        "name": "Engage Click",
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

// Modal prompts (interstitial, popup, bottom banner) are rendered automatically
// by <PromptOverlay />. Use the same analytics code inside its onEvent callback:
<PromptOverlay
  onEvent={(result: PromptResult) => {
    // utilize same analytics code above
  }}
/>
```

## Deep link

You can add a deep link to a prompt in Pulse. When the user selects the CTA, you can use the deep link to send the user to a specific location within the app.

```javascript
{
  "code": 0,
  "meta": {
    "meta": {},
    "deeplink": "redflix://test123"
  },
}
```

## Custom metadata

You can add custom key-value pairs to an item in Pulse. You can use these values to perform an action other than the typical media asset deep link, such as sending the user to a registration screen or performing an operation on behalf of the user.

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

## Send a usage tracking event

Your app can send custom track events using the SDK. If you configure a tracker in Pulse, you can use these custom events to target prompts at specific sets of users.

```javascript
promptMgr.customTrack(customFieldId);
```

## Debugging

You can reset the current user's prompt status so that previously suppressed prompts become available again.

```javascript
promptMgr.resetGoal();
```

## Migrate from the redfast-scoped packages

If you integrated this SDK before it moved to public npm, update the following:

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Before</td><td>After</td></tr>
  <tr><td><code>@recurly/react-native-redfast</code></td><td><code>@recurly/engage-react-native</code></td></tr>
  <tr><td><code>@recurly/redfast-core</code></td><td><code>@recurly/engage-core</code></td></tr>
  <tr><td><code>RedfastInline</code></td><td><code>RecurlyInline</code></td></tr>
  <tr><td><code>.npmrc</code>/<code>.yarnrc.yml</code> with an AUTHTOKEN for <code>npm.pkg.github.com</code></td><td>Remove entirely. No registry config needed</td></tr>
</table>

You also need to add `@react-native-async-storage/async-storage` as a direct dependency in your own `package.json` if you haven't already. See the note under **Install the SDK** above.

## Claude skill

A Claude skill for this SDK is available for download at <a href="https://github.com/recurly/recurly-engage-react-native-sdk-build/blob/main/docs/SKILL.md" target="_blank">SKILL.md</a>. This skill enables Claude to assist with SDK integration, prompt configuration, and event handling in your React Native application.

<br />
