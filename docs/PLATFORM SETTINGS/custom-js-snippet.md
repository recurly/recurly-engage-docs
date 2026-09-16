---
title: Custom JS snippet
excerpt: >-
  Override default identification, trait syncing, consent, promotion display,
  and analytics behaviors in the Recurly Engage JavaScript SDK by supplying
  custom Settings functions.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
<div class="rp-page"> <div class="rp-overview">Admin users can override a range of default behaviors in the Recurly Engage JavaScript SDK by supplying custom implementations of the <code>Settings</code> class. This covers user identification, trait syncing, consent, promotion gating, analytics, and language.</div> <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div> <div class="rp-toc"> <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a> <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a> <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a> </div> </div>

**Prerequisites:**

<ul class="rp-list"> <li>Company or App Administrator permissions in Recurly Engage</li> <li>Familiarity with your site's user identification methods (localStorage, cookies, dataLayer)</li> </ul>

## Definition

<div class="rp-definition">The Custom JS Snippet feature lets you override the default behavior of the Recurly Engage JavaScript SDK by providing your own implementation of the Settings class. Each static function on the class controls a specific behavior — from identifying users to gating when prompts can show.</div>

## Key benefits

<div class="rp-benefits"> <div class="rp-benefit"> <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div> <strong>Accurate user matching</strong> <span>Tie prompts and 1-click actions to your existing user IDs, authenticated or anonymous.</span> </div> <div class="rp-benefit"> <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div> <strong>Seamless integration</strong> <span>Use any client-side storage — cookies, local or session storage, or the dataLayer.</span> </div> <div class="rp-benefit"> <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div> <strong>Enhanced reporting</strong> <span>Ensure downstream analytics and connector actions receive the correct user identifiers and event data.</span> </div> <div class="rp-benefit"> <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div> <strong>Finer control</strong> <span>Gate when prompts can appear, respect consent choices, and control the prompt display language.</span> </div> </div>

## Key details

Admin users may override the following functions on the Settings class. Upon deploying Recurly Engage for the first time, review and configure the functions relevant to your app to ensure users are recognized, tracked, and prompted correctly. You may need to work with your developers to determine the best method for each. Reach out to <a href="mailto:support@recurly.com">[support@recurly.com](mailto:support@recurly.com)</a> if you need assistance.

### `fetchUserId()` (required)

Returns the authenticated user's unique ID. This string can come from cookies, local storage, a database, or an async endpoint fetch. This function runs when the Recurly Engage JS tag loads.

```javascript
static async fetchUserId() {
  const user = JSON.parse(localStorage.getItem("user_object"));
  return user.id;
}
```

<div class="rp-callout rp-callout-note"> <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>If no authenticated user is available, return <code>null</code>.</div> </div>

### `fetchUserJwt()`

Returns a JSON Web Token (JWT) for the current user, if your app issues one. Recurly Engage uses this to verify the user's identity for secure operations.

```javascript
static async fetchUserJwt() {
  return window.userJwt;
}
```

### `fetchAnonUserId()` (optional)

Returns a stable anonymous ID for unauthenticated users. If omitted, Recurly Engage automatically generates and assigns one.

```javascript
static async fetchAnonUserId() {
  return JSON.parse(localStorage.getItem("ajs_anonymous_id"));
}
```

### `fetchUserTraits()` (optional)

Returns an object of user traits to sync to Recurly Engage. Traits can come from cookies, local storage, a database, or an async endpoint fetch, and are used for segmentation, personalization, and reporting.

```javascript
static async fetchUserTraits() {
  const user = JSON.parse(localStorage.getItem("user_object"));
  return {
    is_registered: !!user.token,
    member_since: user.registrationDate,
    accepted_tos: localStorage.getItem("tos_acceptance_date")
  };
}
```

### `canShowPromotion()`

Specifies app-wide conditions under which prompts should never be shown. Returns a boolean — when false, no overlay prompts are shown. Unlike the other functions, this one is not async.

```javascript
static canShowPromotion() {
  return !document.querySelector(".full-screen-video-player");
}
```

### `onPromptInteraction(eventName, payload)`

Called whenever a prompt event occurs, for custom analytics purposes.

<table class="rp-params"> <tr class="rp-thead-row"><td>Parameter</td><td>Description</td></tr> <tr><td><code>eventName</code></td><td>The event type: <code>impression</code>, <code>click</code>, <code>click2</code>, <code>decline</code>, <code>dismiss</code>, <code>timeout</code>, or <code>holdout</code>.</td></tr> <tr><td><code>payload</code></td><td>An object describing the interaction — see fields below.</td></tr> </table>

```javascript
static onPromptInteraction(eventName, payload) {
  analytics.track(payload.activity, payload);
}
```

The `payload` object includes:

<table class="rp-params"> <tr class="rp-thead-row"><td>Field</td><td>Description</td></tr> <tr><td><code>activity</code></td><td>The activity name, e.g. "Redfast Prompt Click"</td></tr> <tr><td><code>cta</code></td><td>The CTA button text</td></tr> <tr><td><code>el</code></td><td>The interacted HTML element</td></tr> <tr><td><code>event_timestamp</code></td><td>ISO 8601 timestamp of the event</td></tr> <tr><td><code>promo_id</code></td><td>The prompt's unique ID</td></tr> <tr><td><code>promo_name</code></td><td>The prompt's name</td></tr> <tr><td><code>user_id</code></td><td>The identified user's ID</td></tr> <tr><td><code>variation_id</code></td><td>The variation's unique ID</td></tr> <tr><td><code>variation_name</code></td><td>The variation's name</td></tr> <tr><td><code>redirect_url</code></td><td>The website action's redirect URL, if applicable</td></tr> <tr><td><code>rf_metadata</code></td><td>Custom key-value metadata attached to the prompt</td></tr> <tr><td><code>experiment_name</code></td><td>The experiment's name, if applicable</td></tr> <tr><td><code>experiment_id</code></td><td>The experiment's unique ID, if applicable</td></tr> <tr><td><code>promo_input_1_value</code> – <code>promo_input_3_value</code></td><td>Values entered into form inputs on the prompt</td></tr> <tr><td><code>survey_input_value</code></td><td>The value entered into a survey input</td></tr> </table>

### `canPing()`

Specifies whether the user has opted into being identified by Recurly Engage. Returns a boolean — use this to honor CCPA/GDPR opt-outs. When false, user information is not collected.

```javascript
static canPing() {
  return true;
}
```

### `setLanguage()`

Specifies the user's language, controlling the display language of prompts that have languages configured. Returns a 2-letter or 4-letter language code, or null to use the default.

```javascript
static setLanguage() {
  return null;
}
```
