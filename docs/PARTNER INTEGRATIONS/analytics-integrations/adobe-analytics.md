---
title: Adobe Analytics
excerpt: >-
  Integration guide for sending Recurly Engage prompt events to Adobe Analytics
  using the Experience Platform Web SDK (Alloy.js).
deprecated: false
hidden: false
metadata:
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">The Adobe Analytics connector uses the existing Alloy.js instance on your site to report prompt interaction events (impressions, clicks, and dismissals) in the same session context as your page analytics.</div>
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
  <li>You must have an Adobe Experience Platform Web software development kit (SDK) (<a href="https://github.com/adobe/alloy?tab=readme-ov-file" target="_blank">Alloy.js</a>) set up on your web property.</li>
  <li>You must have access to <strong>Recurly Engage → Settings → Integrations → External → Adobe Analytics</strong>.</li>
</ul>

# Definition

<div class="rp-definition">The Adobe Analytics integration fires custom events for Recurly Engage prompt interactions directly through Alloy.js, preserving user and session data in your Adobe Analytics reports.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-link" aria-hidden="true"></i></div>
    <strong>Consistent session data</strong>
    <span>Events emit using the same Alloy session context as your other Analytics events.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-plug" aria-hidden="true"></i></div>
    <strong>Built-in tracking</strong>
    <span>No additional SDKs are required. The integration uses your existing Alloy.js configuration.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-eye" aria-hidden="true"></i></div>
    <strong>Full interaction visibility</strong>
    <span>Capture all prompt lifecycle events in Adobe Analytics.</span>
  </div>
</div>

# Key details

## Event details

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Activity</td><td>Description</td></tr>
  <tr><td>Recurly Engage Prompt Impression</td><td>A user has seen the prompt</td></tr>
  <tr><td>Recurly Engage Prompt Dismiss</td><td>A user has dismissed the prompt by clicking the 'X' or outside the prompt (if enabled)</td></tr>
  <tr><td>Recurly Engage Prompt Timeout</td><td>The prompt has closed automatically due to a timer</td></tr>
  <tr><td>Recurly Engage Prompt Decline</td><td>A user has declined the prompt by clicking the decline button</td></tr>
  <tr><td>Recurly Engage Prompt Click</td><td>A user has accepted the prompt using the primary call-to-action (CTA) button</td></tr>
  <tr><td>Recurly Engage Prompt Holdout</td><td>A holdout user has been served the prompt but not exposed</td></tr>
  <tr><td>Recurly Engage Prompt Click 2</td><td>A user has accepted the prompt using the secondary CTA button</td></tr>
</table>

Each event includes these attributes when available:

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Event property</td><td>Description</td></tr>
  <tr><td><code>promo_id</code></td><td>Unique prompt identifier (from the Prompt ID field under Details)</td></tr>
  <tr><td><code>promo_name</code></td><td>The name of the prompt</td></tr>
  <tr><td><code>variation_id</code></td><td>Identifier of the experiment variation (if any)</td></tr>
  <tr><td><code>variation_name</code></td><td>Name of the experiment variation (if any)</td></tr>
  <tr><td><code>event_timestamp</code></td><td>Timestamp of when the interaction occurred</td></tr>
</table>

## Setup

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Create or select a Data Stream</h4><p>In Adobe Experience Platform, create or select a <span style={{fontWeight: "bold"}}>Data Stream</span>. Make sure you have an associated schema, report suite, and field group configured to accept custom event fields.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Open the Adobe Analytics settings</h4><p>In <span style={{fontWeight: "bold"}}>Recurly Engage</span>, navigate to <span style={{fontWeight: "bold"}}>Settings → Integrations → External → Adobe Analytics</span>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Enter your IDs</h4><p>Enter your <span style={{fontWeight: "bold"}}>Data Stream ID</span> and <span style={{fontWeight: "bold"}}>Adobe Org ID</span>. See the <a href="https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/orgid" target="_blank">Org ID docs</a>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Save your settings</h4><p>Save your integration settings. Prompt events are now sent through Alloy.js to Adobe Analytics under your Data Stream.</p></div>
  </div>
</div>
