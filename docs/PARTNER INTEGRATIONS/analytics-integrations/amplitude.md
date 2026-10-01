---
title: Amplitude
excerpt: >-
  Integration guide for sending Recurly Engage prompt events to Amplitude and
  syncing user data via CSV, Webhooks, or Export API.
deprecated: false
hidden: false
metadata:
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">The Amplitude integration streams Recurly Engage prompt interactions (impressions, clicks, dismissals, and timeouts) into your Amplitude analytics instance using the existing Amplitude JavaScript software development kit (SDK). It also supports inbound user and event data syncs.</div>
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
  <li>You must have an Amplitude account with a project API key and access to the SDK or Export API.</li>
  <li>For outbound events, the Amplitude JavaScript SDK must be initialized on your site.</li>
</ul>

# Definition

<div class="rp-definition">The Amplitude connector sends Recurly Engage prompt events to Amplitude and imports user and event data into Recurly Engage.</div>

* **Outbound events**: Use the running Amplitude JavaScript SDK to fire prompt events in-session.
* **Inbound data sync**: Import historical events and user traits through comma-separated values (CSV) uploads, webhooks, or scheduled Export API jobs.

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-link" aria-hidden="true"></i></div>
    <strong>Same-session event tracking</strong>
    <span>Capture prompt interactions in the same session context as your other Amplitude events.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-file-import" aria-hidden="true"></i></div>
    <strong>Flexible data import</strong>
    <span>Choose CSV, webhooks, or the Export API based on your data flow needs.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-chart-line" aria-hidden="true"></i></div>
    <strong>Unified analytics</strong>
    <span>Analyze prompt performance alongside full user behavior in Amplitude.</span>
  </div>
</div>

# Key details

## Outbound events

For web-based devices, Recurly Engage uses the existing Amplitude JavaScript SDK instance to emit events. To confirm your SDK configuration and enable the integration, contact your Customer Success Manager or <a href="mailto:support@recurly.com">[support@recurly.com](mailto:support@recurly.com)</a>.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open the Amplitude settings</h4><p>In <span style={{fontWeight: "bold"}}>Recurly Engage</span>, navigate to <span style={{fontWeight: "bold"}}>Settings → Integrations → External → Amplitude</span>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Enter your Project API Key</h4><p>Enter your Amplitude <span style={{fontWeight: "bold"}}>Project API Key</span>. See <a href="https://amplitude.com/docs/apis/authentication" target="_blank">Amplitude authentication</a>.</p></div>
  </div>
</div>

### Event details

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Activity</td><td>Description</td></tr>
  <tr><td>Recurly Engage Prompt Impression</td><td>A user has seen the prompt</td></tr>
  <tr><td>Recurly Engage Prompt Dismiss</td><td>A user has dismissed the prompt by clicking close or outside (if enabled)</td></tr>
  <tr><td>Recurly Engage Prompt Timeout</td><td>The prompt closed automatically due to a timer</td></tr>
  <tr><td>Recurly Engage Prompt Decline</td><td>A user declined the prompt by clicking the decline button</td></tr>
  <tr><td>Recurly Engage Prompt Click</td><td>A user accepted the prompt using the primary call-to-action (CTA)</td></tr>
  <tr><td>Recurly Engage Prompt Holdout</td><td>A holdout user reached the prompt without exposure</td></tr>
  <tr><td>Recurly Engage Prompt Click 2</td><td>A user accepted using the secondary CTA</td></tr>
</table>

Attributes sent with each event:

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Property</td><td>Description</td></tr>
  <tr><td><code>promo_id</code></td><td>Unique prompt identifier (from Details)</td></tr>
  <tr><td><code>promo_name</code></td><td>Prompt name</td></tr>
  <tr><td><code>variation_id</code></td><td>Experiment variation identifier (if any)</td></tr>
  <tr><td><code>variation_name</code></td><td>Variation name</td></tr>
  <tr><td><code>event_timestamp</code></td><td>When the event occurred</td></tr>
</table>

## Inbound data sync

Depending on your use case, you can import user or event data into Recurly Engage using these methods.

### CSV export

Download one-off reports from Amplitude (make sure **User ID** is the first column) and upload them to **Settings → User Traits → CSV Import** in Pulse.

### Webhook

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Add a webhook destination</h4><p>In Amplitude's Data Catalog, add a <span style={{fontWeight: "bold"}}>Webhook</span> destination.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Configure the endpoint</h4><p>Configure the endpoint details provided by your Customer Success Manager.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Filter the events</h4><p>Filter for only the events you need for your use cases.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Test the connection</h4><p>Test the connection to validate payload delivery.</p></div>
  </div>
</div>

### Export API

For automated exports, work with your Customer Success team to schedule jobs using the Amplitude <a href="https://developers.amplitude.com/docs/export-api" target="_blank">Export API</a>. Provide an API key with appropriate permissions, and configure the schedule to sync data into Recurly Engage automatically.

***

📋 TODO before publishing:

- [ ] Confirm the title. The draft had none, so I used "Amplitude".
