---
title: Live
excerpt: >-
  Guide for the Live view in Recurly Engage, which provides near-real-time
  monitoring of prompt interactions and errors.
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
  <div class="rp-overview">The Live view displays near-real-time prompt interactions and exceptions for the prompts you currently have active. Use it to filter, search, and troubleshoot your live prompts.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly Engage subscription plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have <strong>Company</strong>, <strong>App Administrator</strong>, or <strong>App Member</strong> permissions in Recurly Engage.</li>
</ul>

# Definition

<div class="rp-definition">The Live feature streams prompt events, such as impressions, clicks, and timeouts, along with any action errors (External, API, or Website) as they occur, so you can validate behavior and resolve issues immediately.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Instant validation</strong>
    <span>Verify that newly launched prompts are firing correctly the moment they go live.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-filter" aria-hidden="true"></i></div>
    <strong>Comprehensive monitoring</strong>
    <span>Filter interactions by device platform, prompt type, or user ID to pinpoint activity.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-bug" aria-hidden="true"></i></div>
    <strong>Error tracking</strong>
    <span>Switch to <span style={{fontWeight: "bold"}}>Errors</span> mode to surface and investigate any action failures in real time.</span>
  </div>
</div>

# Key details

Use the Live feature to:

<ul class="rp-list">
  <li><strong>Ensure</strong> that recently launched prompts are working properly.</li>
  <li><strong>Monitor</strong> live prompts during critical events.</li>
  <li><strong>Debug</strong> end user support issues.</li>
</ul>


<Image src="https://files.readme.io/c308d679aa03b9f70862664b088bb55718dc605a0fedaa1202edac91d4fd5c9f-image.png" align="center" width="75%" border={true} />



<Image src="https://files.readme.io/c11da48e14ad0d0fdf7007f45bffdd246785856d3086a9656e8d222a9fb737a2-image.png" align="center" width="40%" border={true} />


## Event types

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Type</td><td>Description</td></tr>
  <tr><td>Impression</td><td>User was shown the prompt.</td></tr>
  <tr><td>Timeout</td><td>User did not respond before the prompt timer ran out.</td></tr>
  <tr><td>Dismiss</td><td>User dismissed the prompt by clicking on the X or outside the window (as configured in the Recurly Engage console).</td></tr>
  <tr><td>Decline</td><td>User clicked on the decline link.</td></tr>
  <tr><td>Click</td><td>User accepted the prompt (this has been phased out in favor of Goal).</td></tr>
  <tr><td>Goal</td><td>User accepted the prompt.</td></tr>
  <tr><td><code>CustomGoals[Activity Type]</code></td><td>User completed the defined custom goal after previously performing the specified activity type on a prompt.</td></tr>
  <tr><td>Exclude</td><td>User is part of the holdout group or not eligible for a prompt after the specified User Limit has been exceeded.</td></tr>
  <tr><td>Holdout</td><td>User is part of the holdout group or not eligible for a prompt after the specified User Limit has been exceeded.</td></tr>
</table>
