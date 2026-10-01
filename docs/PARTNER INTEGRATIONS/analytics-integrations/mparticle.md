---
title: mParticle
excerpt: >-
  Integration guide for capturing Recurly Engage prompt interactions as custom
  events in mParticle via Custom Feed.
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
  <div class="rp-overview">The mParticle connector lets you export prompt events and attributes from Recurly Engage to your mParticle workspace, so you can track user activity across platforms in one place.</div>
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
  <li>You must have an mParticle account with permissions to create Custom Feeds.</li>
  <li>You must have access to your mParticle workspace's Server Key and Secret.</li>
</ul>

# Definition

<div class="rp-definition">Using mParticle's Custom Feed integration, Recurly Engage sends prompt interaction events and related attributes to mParticle for real-time analytics and segmentation.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-file-export" aria-hidden="true"></i></div>
    <strong>Streamlined event export</strong>
    <span>Automatically push Recurly Engage events into mParticle without custom coding.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-id-card" aria-hidden="true"></i></div>
    <strong>Unified user data</strong>
    <span>Use mParticle's identity resolution and data pipeline for prompt events.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-bolt" aria-hidden="true"></i></div>
    <strong>Real-time insights</strong>
    <span>View prompt impressions, clicks, and custom goals alongside all other mParticle-tracked events.</span>
  </div>
</div>

# Key details

## Activate the integration

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open Inputs</h4><p>In <span style={{fontWeight: "bold"}}>mParticle</span>, navigate to <span style={{fontWeight: "bold"}}>Setup → Inputs</span>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/d0f22ee-mParticle_add_new_custom_feed.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Add a Custom Feed</h4><p>Select the <span style={{fontWeight: "bold"}}>Feeds</span> tab and add a <span style={{fontWeight: "bold"}}>Custom Feed</span> by selecting the <span style={{fontWeight: "bold"}}>+</span> icon.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/9b94f9b-mParticle_add_new_custom_feed_1.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Share the feed details</h4><p>Provide a <span style={{fontWeight: "bold"}}>Configuration Name</span>, and then share the <span style={{fontWeight: "bold"}}>Server Key</span>, <span style={{fontWeight: "bold"}}>Server Secret</span>, and <span style={{fontWeight: "bold"}}>API Endpoint</span> with your Recurly Engage Customer Success Manager or <a href="mailto:support@recurly.com">support@recurly.com</a>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/27a2abc-mParticle_add_new_custom_feed_2.png" align="center" width="75%" border={true} />


## Required settings

Under **Settings → Integrations → External → mParticle** in Recurly Engage, configure:

* **Base API Endpoint** (including the mParticle Pod)
* **Server Key**
* **Server Secret**
* **Mode**: Production or Development

## Supported actions

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Action</td><td>Description</td></tr>
  <tr><td><strong>Export Events</strong></td><td>Reports custom events with user-specific prompt interactions and attributes</td></tr>
</table>

## Custom events and attributes

After activation, mParticle receives the following custom events, tagged to the user's identity and visible in the User Activity screen:


<Image src="https://files.readme.io/b504573-mparticle-user-activity-4.png" align="center" width="75%" border={true} />



<Image src="https://files.readme.io/e006d0a-mparticle-custom-event-5.png" align="center" width="75%" border={true} />


<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Custom event</td><td>Description</td></tr>
  <tr><td><strong>Recurly Engage Prompt Impression</strong></td><td>A user has seen the prompt</td></tr>
  <tr><td><strong>Recurly Engage Prompt Dismiss</strong></td><td>A user has dismissed the prompt by clicking close or outside (if enabled)</td></tr>
  <tr><td><strong>Recurly Engage Prompt Timeout</strong></td><td>The prompt closed automatically due to a timer</td></tr>
  <tr><td><strong>Recurly Engage Prompt Decline</strong></td><td>A user declined the prompt by clicking the decline button</td></tr>
  <tr><td><strong>Recurly Engage Prompt Click</strong></td><td>A user accepted the prompt using the primary call-to-action (CTA)</td></tr>
  <tr><td><strong>Recurly Engage Prompt Custom Goal</strong></td><td>A user completed the custom goal action defined for the prompt</td></tr>
</table>

These attributes are sent with each event (when available):

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Custom attribute</td><td>Description</td></tr>
  <tr><td><code>app_name</code></td><td>The name of your Recurly Engage instance in Pulse</td></tr>
  <tr><td><code>prompt_id</code></td><td>Unique prompt identifier (from Details)</td></tr>
  <tr><td><code>prompt_name</code></td><td>The name of the prompt</td></tr>
  <tr><td><code>experiment_id</code></td><td>Unique experiment identifier (if the prompt is part of an A/B test)</td></tr>
  <tr><td><code>experiment_name</code></td><td>Name of the running experiment</td></tr>
  <tr><td><code>variation_id</code></td><td>Identifier for the specific prompt variation</td></tr>
  <tr><td><code>variation_name</code></td><td>Name of that prompt variation</td></tr>
  <tr><td><code>survey_value</code></td><td>Value of selected survey option (if survey is enabled on the prompt)</td></tr>
</table>

## Additional resources

<ul class="rp-list">
  <li><a href="https://docs.mparticle.com/integrations/custom-feed/feed/" target="_blank">mParticle Custom Feed Reference</a></li>
</ul>
