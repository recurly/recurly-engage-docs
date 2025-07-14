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

**Add** the Recurly Engage registry to your package manager config (`.npmrc` or `.yarnrc.yml`):

```text
# .npmrc
@redfast:registry=https://npm.pkg.github.com
//npm.pkg.github.com/:_authToken=AUTHTOKEN

# .yarnrc.yml
npmAuthToken: "AUTHTOKEN"
```

**Install** packages:

```shell
npm install @redfast/redfast-core
npm install @redfast/react-native-redfast

# or with yarn
yarn add @redfast/redfast-core
yarn add @redfast/react-native-redfast
```

## Initialize Recurly Engage

In your App root component, initialize the prompt manager and wait for it to be ready:

```javascript
import React from 'react';
import { PromptManager, PromptAction_Init } from '@redfast/redfast-core';

React.useEffect(() => {
  const promptMgr = new PromptManager('YOUR_APP_ID', 'INITIAL_USER_ID');
  const intervalId = setInterval(() => {
    if (promptMgr.isInitialized()) {
      dispatch({ type: PromptAction_Init, data: promptMgr });
      setReady(true);
      clearInterval(intervalId);
    }
  }, 1000);
  return () => clearInterval(intervalId);
}, [dispatch]);
```

## Set UserId

Update the current user ID at runtime (e.g., after login):

```javascript
promptMgr.setUserId(newUserId);
```

## Render modal prompts

Use the `displayPrompt` helper to show interstitials, popups, or banners upon screen entry or button click:

```javascript
import { displayPrompt } from '@redfast/react-native-redfast';

const { path, delaySeconds } = await promptMgr.onScreenChanged('home');
if (path) {
  setTimeout(() => {
    setPathItem(path);
    setShowModal(true);
  }, delaySeconds);
}

// In your component:
displayPrompt(showModal, path, (result) => {
  console.log('Prompt result:', result);
  setShowModal(false);
});
```

## Render inline prompts

Use the `RedfastInline` component to render an inline prompt:

```jsx
import { RedfastInline } from '@redfast/react-native-redfast';

<RedfastInline
  zoneId="myZoneId"
  closeButtonColor="#000000"
  closeButtonBgColor="#FFFFFF"
  closeButtonSize="20"
  timerFontSize="14"
  timerFontColor="#FFFFFF"
  onEvent={(result) => {
    console.log('Inline event:', result);
  }}
/>
```

## Custom prompt rendering

Optionally fetch and render prompts yourself using the prompt manager API:

```javascript
// Fetch all prompts
let prompts = promptMgr.getPrompts(PathType.ALL);

// Fetch triggerable prompts
let triggers = promptMgr.getTriggerablePrompts('home_screen', 'clickId', PathType.ALL);

// Report interactions
prompts.forEach(prompt => {
  prompt.impression();
  prompt.goal();
  prompt.decline();
  prompt.dismiss();
  prompt.timeout();
  prompt.holdout();
});
```

### PathType values

```text
PathType.ALL = -1
PathType.MODAL = 2
PathType.HORIZONTAL = 5
PathType.TEXT = 7
PathType.VERTICAL = 8
PathType.TILE = 9
PathType.INTERSTITIAL = 10
PathType.BOTTOM_BANNER = 13
```

### PromptResultCode values

```text
OK = 1
ERROR = -100
NOT_APPLICABLE = -101
DISABLED = -102
SUPPRESSED = -103
IMPRESSION = 100
BUTTON1 = 101
BUTTON2 = 102
BUTTON3 = 103
DISMISS = 110
TIMEOUT = 111
HOLDOUT = 120
```

## Actions

Result callbacks include metadata to drive client-side actions:

```javascript
interface PromptResult {
  code: PromptResultCode;
  value?: Record<string, any>;
  meta?: Record<string, any>;
  promptMeta?: Record<string, any>;
}
```

## Deeplink, in-app purchase and custom metadata

* **Deeplink**: Configured in Pulse, available in `result.meta.deeplink`.
* **In-app purchase**: SKU defined on prompt, trigger purchase flow on `result` callback.
* **Custom metadata**: Available in `result.meta.meta` for bespoke behavior.

## Send usage tracking event

Report custom tracking events to enable segmentation:

```javascript
promptMgr.customTrack(customFieldId);
```

## Debug view

Reset a user’s prompt state for testing:

```javascript
promptMgr.resetGoal();
```