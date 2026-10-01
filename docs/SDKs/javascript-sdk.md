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
<div class="rp-page">
  <div class="rp-overview">The JavaScript software development kit (SDK) enables prompt delivery and tracking in standard web browsers as well as HTML5-based connected TV (CTV) platforms.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">1</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">2</span>Key details</a>
  </div>
</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-laptop-mobile" aria-hidden="true"></i></div>
    <strong>Cross-platform support</strong>
    <span>Use a single SDK for both web and CTV environments.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-tv" aria-hidden="true"></i></div>
    <strong>Custom device targeting</strong>
    <span>Deliver prompts selectively to named CTV devices.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-user-check" aria-hidden="true"></i></div>
    <strong>Consistent user ID fetching</strong>
    <span>Ensure correct user identification across different app contexts.</span>
  </div>
</div>

# Key details

The JavaScript SDK supports web browsers as well as HTML5-based CTV devices. To install it, see the <a href="/recurly-engage/docs/add-the-redfast-tag" target="_blank">Recurly Engage JavaScript tag</a> article.

## CTV considerations

We recommend the following when you integrate the JavaScript SDK on CTV apps:

* Create a custom device in **Settings > Custom Devices**. You can define multiple entries, for example `SamsungTV`, `LGTV`, and `Vidaa`.
* Create prompts for the custom devices. This gives you control over exactly which prompts are delivered to each CTV platform.
* Specify the custom device that represents the CTV platform in the JavaScript tag. For example: `<script src="..." data-rf-device-type="SamsungTV" />`
* Make sure `fetchUserId()` is integrated, because user ID retrieval on CTV is often different from a normal desktop or mobile web app.
* CTV apps are normally implemented as single-page apps, so using prompts to navigate to specific screens may require a discussion with your development team.
* If you have any questions, contact your Customer Success Manager or <a href="mailto:support@recurly.com">[support@recurly.com](mailto:support@recurly.com)</a>.

## Analytics

Recurly Engage has built-in integrations with several analytics services. To report all prompt interaction events in a custom analytics payload instead, implement a callback function in **Settings > Custom JS Snippet**. The callback is invoked whenever a user interaction occurs.

### Callback function example

\[TODO: Dev/PO review — possible issue: in the example below, `case "dismiss"` has no colon, and `static` appears on a standalone function. Left verbatim.]

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

### Google Analytics (GA4) example

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

### Segment example

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

## Implementation best practices

These implementation strategies help the Recurly Engage JavaScript snippet start executing as quickly as possible, which minimizes delay on your site.

### Load type comparison

The implementation method you choose directly affects execution speed and how soon the script is available on the page.

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Implementation method</td><td>Load type</td><td>Primary benefit</td><td>Use case</td></tr>
  <tr><td>Minimal Latency</td><td>Synchronous</td><td>Fastest execution time. The script starts loading and executing immediately, minimizing delay.</td><td>Critical: Required when the Engage script must execute before or during initial page rendering (for example, to prevent content flicker or ensure immediate availability).</td></tr>
  <tr><td>Standard</td><td>Deferred/Async</td><td>Minimal impact on initial page rendering time (Time to First Paint).</td><td>Non-Critical: Acceptable when the Engage script can wait for the page content to load before running.</td></tr>
</table>

### Minimal latency implementation

To get the fastest script execution time, we recommend a three-step approach that prioritizes immediate script loading and execution by the browser.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Load the script synchronously</h4><p>Synchronous loading means scripts load sequentially, one after another, starting with the <code>&lt;head&gt;</code> tag. Don't include the <code>async</code> or <code>defer</code> attributes on the script tag. This forces the browser to pause HTML parsing, fetch the resource, and execute the Recurly Engage script immediately, which is essential for rapid feature initiation.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Place the snippet in the head</h4><p>Place the synchronous snippet in the <code>&lt;head&gt;</code> of the HTML document, immediately after critical meta and CSS elements. Placing it high up ensures it's discovered and executed early in the parsing process.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Add preload and preconnect resource hints</h4><p>To further accelerate the network phase, include the following resource hints at the very top of your <code>&lt;head&gt;</code>.</p></div>
  </div>
</div>

* **preconnect**: Initiates an early connection handshake with the Recurly Engage
* **preload**: Instructs the browser to fetch the script resource immediately with high priority

### Example

Replace `YOUR_TAG_URL` with your specific Recurly Engage script URL.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <!-- 1. Resource Hints (preconnect and preload) -->
    <link rel="preconnect" href="YOUR_TAG_URL">
    <link rel="preload" href="YOUR_TAG_URL/redfast.js" as="script">
    <!-- Other meta tags and stylesheets here -->
    <!-- 2. Synchronous Recurly Engage Script (placed high in <head>) -->
    <script src="YOUR_TAG_URL/redfast.js"></script>

    <title>Your Website Title</title>
</head>
<body>
    <!-- Page Content -->
</body>
</html>

```

<br />

<br />
