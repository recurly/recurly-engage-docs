---
title: Google Analytics
excerpt: >-
  Integration guide for sending Recurly Engage prompt interaction events to
  Google Analytics via client-side SDK and server-side Measurement Protocol.
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
  <div class="rp-overview">Send Recurly Engage prompt events to Google Analytics (GA) to see prompt engagement alongside your existing site metrics. You can use a client integration, a server integration, or both.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly Engage subscription plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have <strong>Company</strong> or <strong>App Administrator</strong> permissions in Recurly Engage.</li>
  <li>You must have a Google Analytics property and tracking ID (GA Tag ID).</li>
  <li>You must have access to <strong>Recurly Engage → Settings → Integrations → External → Google Analytics</strong>.</li>
  <li>For server-side calls, you should be familiar with the Measurement Protocol (v1).</li>
</ul>

# Definition

<div class="rp-definition">The Google Analytics integration provides two methods for sending prompt events to GA: a client integration and a server integration.</div>

1. **Client integration**: Uses your existing GA JavaScript software development kit (SDK) instance to fire custom events for prompt interactions.
2. **Server integration**: Sends events through an API action using the Google Analytics Measurement Protocol.

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-chart-line" aria-hidden="true"></i></div>
    <strong>Unified reporting</strong>
    <span>View prompt metrics in your GA dashboards alongside pageviews and user behavior.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-link" aria-hidden="true"></i></div>
    <strong>Session continuity</strong>
    <span>Events fire in the same session context as your GA page events.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-sliders" aria-hidden="true"></i></div>
    <strong>Custom payloads</strong>
    <span>Use GA's Measurement Protocol to include any relevant parameters.</span>
  </div>
</div>

# Key details

## Client integration

For web-based devices, Recurly Engage uses the running instance of the Google Analytics JavaScript SDK. This preserves session and user context when it reports real-time prompt events.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open the Google Analytics settings</h4><p>In <span style={{fontWeight: "bold"}}>Recurly Engage</span>, go to <span style={{fontWeight: "bold"}}>Settings → Integrations → External → Google Analytics</span>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Enter your GA Tag ID</h4><p>Enter your <a href="https://support.google.com/analytics/answer/9539598?hl=en" target="_blank">GA Tag ID</a>.</p></div>
  </div>
</div>

### Event details

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Activity</td><td>Description</td></tr>
  <tr><td>Recurly Engage Prompt Impression</td><td>A user has seen the prompt</td></tr>
  <tr><td>Recurly Engage Prompt Dismiss</td><td>A user has dismissed the prompt by clicking the close button or outside the prompt view</td></tr>
  <tr><td>Recurly Engage Prompt Timeout</td><td>The prompt closed automatically due to a timer</td></tr>
  <tr><td>Recurly Engage Prompt Decline</td><td>A user has declined the prompt by clicking the decline button</td></tr>
  <tr><td>Recurly Engage Prompt Click</td><td>A user has accepted the prompt by clicking the primary call-to-action (CTA) button</td></tr>
  <tr><td>Recurly Engage Prompt Holdout</td><td>A holdout user has reached the prompt but not seen it</td></tr>
  <tr><td>Recurly Engage Prompt Click 2</td><td>A user has accepted the prompt by clicking the secondary CTA button</td></tr>
</table>

Each event includes these attributes when applicable:

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Event property</td><td>Description</td></tr>
  <tr><td><code>promo_id</code></td><td>Unique prompt identifier (see Prompt Details)</td></tr>
  <tr><td><code>promo_name</code></td><td>Name of the prompt</td></tr>
  <tr><td><code>variation_id</code></td><td>Identifier of the experiment variation (if any)</td></tr>
  <tr><td><code>variation_name</code></td><td>Name of the experiment variation (if any)</td></tr>
  <tr><td><code>event_timestamp</code></td><td>Timestamp when the interaction occurred</td></tr>
</table>

## Server integration

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Create an API action</h4><p>In <span style={{fontWeight: "bold"}}>Settings → Actions → API Actions</span>, configure a POST action to send events through the Google Analytics Measurement Protocol (v1). Use the following endpoint.</p></div>
  </div>
</div>

```
https://www.google-analytics.com/collect
```


<Image src="https://files.readme.io/ebf7cc4-Google_Analytics_Custom_Action.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Specify the payload</h4><p>Include the required and optional Measurement Protocol parameters listed below.</p></div>
  </div>
</div>

* **Required**: `v` (protocol version), `tid` (Tracking ID), and `t` (hit type, for example, `event`).
* **Optional**: `cid` (Client ID), `ec` (event category), `ea` (event action), `el` (event label), and `ev` (event value).

See the full <a href="https://developers.google.com/analytics/devguides/collection/protocol/v1/parameters" target="_blank">Measurement Protocol parameter reference</a>.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Add the action to a prompt</h4><p>Attach the new API action to a prompt interaction (Accept, Decline, and so on) or within a guide or experience. For detailed steps, follow the <a href="/recurly-engage/docs/actions-1" target="_blank">Add Action guide</a>.</p></div>
  </div>
</div>
