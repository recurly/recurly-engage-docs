---
title: Javascript (Web and CTV)
excerpt: >-
  Configuration guide for the JavaScript SDK, supporting both web browsers and
  HTML5-based CTV devices in Recurly Engage.
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

The **JavaScript SDK** enables prompt delivery and tracking in standard web browsers as well as HTML5-based connected TV (CTV) platforms.

# Key benefits

* **Cross-platform support**: Use a single SDK for both web and CTV environments.
* **Custom device targeting**: Deliver prompts selectively to named CTV devices.
* **Consistent user ID fetching**: Ensure correct user identification across different app contexts.

# Key details

The JavaScript SDK supports web browsers as well as HTML5-based CTV devices. To install the JavaScript SDK, please visit this [article](add-the-redfast-tag).

## CTV considerations

We recommend the following when integrating the JS SDK on CTV apps:

* Create a Custom Devices within Settings > Custom Devices. Multiple entries may be defined, e.g. `SamsungTV`, `LGTV`, `Vidaa`.
* Prompts should be created for the Custom Device(s). This allows for control over exactly which prompts are delivered to the various CTV platforms.
* The JS tag should specify the Custom Device representing the CTV platform. For example: `<script src="..." data-rf-device-type="SamsungTV" />`
* Ensure that the fetchUserId() functionality is integrated as this is often different than the normal Desktop/mobile web-app.
* As CTV apps are normall implemented as Single Page Apps, using prompts to navigate to specific screens may require a discussion with your dev team.
* Reach out to your Customer Success Manager if you have any questions!

## Analytics

While there are a number of built in integrations with Analytics services, you may want to generate a custom analytics payload to report all events relating to user interactions against Recurly Engage prompts. You may implement a callback function that is invoked whenever a user interaction occurs within Settings > Custom JS Snippet.

**Example**

```javascript
/*
  This function is called whenever a prompt event occurs, for custom analytics purposes
  @param {string} eventName: impression, click, click2, decline, dismiss, timeout, holdout
  @param {object} payload: {
    activity: "Redfast Prompt Click",
    cta: "CTA Button Text",
    el: <HTMLElement>,
    event_timestamp: "2025-01-01T08:00:00.000Z",
    promo_id: "abcd1234-1234-abcd-1234-abcdef123456",
    promo_name: "Prompt Name",
    user_id: "abcdef1234567890abcdef1234567890abcdef1234567890abcdef1234567890",
    variation_id: "abcd1234-1234-abcd-1234-abcdef123456",
    variation_name: "Experiment Name",
  }
*/
static onPromptInteraction(eventName, payload) {
  switch(eventName) {
    case "impression":
      myAnalytics.track("Prompt Impression", { "id": payload.promo_id, "name": payload.promo_name });
      break;
    case "dismiss"
      myAnalytics.track("Prompt Dismiss", { "id": payload.promo_id, "name": payload.promo_name });
      break;
  }
}
```

**Google Analytics (GA4) Example**:

```javascript
static onPromptInteraction(eventName, payload) {
  const baseParams = {
    promo_id: payload.promo_id,
    promo_name: payload.promo_name,
    variation_id: payload.variation_id,
    variation_name: payload.variation_name,
    cta: payload.cta,
    activity: payload.activity,
    user_id: payload.user_id,
    event_timestamp: payload.event_timestamp,
  };

  switch(eventName) {
    case "impression":
      gtag("event", "prompt_impression", baseParams);
      break;

    case "click":
    case "click2":
      gtag("event", "prompt_click", { ...baseParams, click_type: eventName });
      break;

    case "decline":
      gtag("event", "prompt_decline", baseParams);
      break;

    case "dismiss":
      gtag("event", "prompt_dismiss", baseParams);
      break;

    case "timeout":
      gtag("event", "prompt_timeout", baseParams);
      break;

    case "holdout":
      gtag("event", "prompt_holdout", baseParams);
      break;

    default:
      console.warn("Unknown event:", eventName);
  }
}

```

**Segment example**

```javascript
static onPromptInteraction(eventName, payload) {
  const properties = {
    promo_id: payload.promo_id,
    promo_name: payload.promo_name,
    variation_id: payload.variation_id,
    variation_name: payload.variation_name,
    cta: payload.cta,
    activity: payload.activity,
    event_timestamp: payload.event_timestamp,
  };

  switch(eventName) {
    case "impression":
      analytics.track("Prompt Impression", properties);
      break;

    case "click":
    case "click2":
      analytics.track("Prompt Click", { ...properties, click_type: eventName });
      break;

    case "decline":
      analytics.track("Prompt Decline", properties);
      break;

    case "dismiss":
      analytics.track("Prompt Dismiss", properties);
      break;

    case "timeout":
      analytics.track("Prompt Timeout", properties);
      break;

    case "holdout":
      analytics.track("Prompt Holdout", properties);
      break;

    default:
      console.warn("Unknown event:", eventName);
  }
}

```

<br />
