---
title: Cleeng
excerpt: >-
  Configuration and usage guide for the Cleeng connector in Recurly Engage,
  including API setup, supported actions, and subscription data syncing.
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
  <div class="rp-overview">The Cleeng integration lets you manage subscriber offers, coupons, and reactivations directly from prompts in Recurly Engage by connecting to your Cleeng account.</div>
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
  <li>You must have a Cleeng Publisher account with a valid API Broadcaster Token.</li>
</ul>

# Definition

<div class="rp-definition">The Cleeng connector synchronizes offers and subscription data from Cleeng, so you can trigger subscription management actions from within your prompts.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-arrow-up-right-dots" aria-hidden="true"></i></div>
    <strong>Flexible plan management</strong>
    <span>Upgrade or downgrade user subscriptions through prompts.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-ticket" aria-hidden="true"></i></div>
    <strong>Coupon application</strong>
    <span>Apply promo codes instantly when users interact.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-rotate-left" aria-hidden="true"></i></div>
    <strong>Reactivation support</strong>
    <span>Reactivate churned subscribers through targeted prompts.</span>
  </div>
</div>

# Key details

## Required settings

Configure your Cleeng connector under **Settings > Connectors**:

* **API Key**: Your Broadcaster Token. <a href="https://publisher.support.cleeng.com/hc/en-us/articles/218389137-Obtaining-your-API-Broadcaster-Token" target="_blank">See how to obtain your API Broadcaster Token</a>.

## Supported actions

These billing actions are available to attach to prompt interactions:

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Action</td><td>Description</td><td>Dependencies</td></tr>
  <tr><td>Switch Subscription</td><td>Subscribe user to a different offer (upgrade or downgrade)</td><td>Offer upgrade or downgrade configured in the Cleeng console</td></tr>
  <tr><td>Apply Coupon</td><td>Apply coupon code to the user's subscription</td><td>None</td></tr>
  <tr><td>Reactivate Subscription</td><td>Reactivate a subscription marked for cancellation</td><td>None</td></tr>
</table>

## Sync subscription data

Schedule a periodic export of subscription data from Cleeng into Recurly Engage using comma-separated values (CSV) files delivered through Amazon S3.


<Image src="https://files.readme.io/217df5b-Screenshot_2024-06-02_at_10.08.45_PM.png" align="center" width="75%" border={true} />


## Set up the sync

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open Segments</h4><p>In the Cleeng console, navigate to <span style={{fontWeight: "bold"}}>Segments</span>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Open the schedule settings</h4><p>Select <span style={{fontWeight: "bold"}}>Build a Segment</span>, and then select the gear icon (upper right).</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Select Schedule</h4><p>Select <span style={{fontWeight: "bold"}}>Schedule</span> from the dropdown.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Create the schedule</h4><p>Select <span style={{fontWeight: "bold"}}>New</span>, and then name the schedule (for example, "Recurly Engage Sync").</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Choose the delivery method</h4><p>Choose <span style={{fontWeight: "bold"}}>Amazon S3</span> as the delivery method.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">6</div>
    <div><h4>Enter your S3 credentials</h4><p>Fill in <span style={{fontWeight: "bold"}}>Bucket</span>, <span style={{fontWeight: "bold"}}>Optional Path</span>, <span style={{fontWeight: "bold"}}>Access Key</span>, and <span style={{fontWeight: "bold"}}>Secret Key</span> from <span style={{fontWeight: "bold"}}>Pulse &gt; Settings &gt; User Traits &gt; AWS S3 Credentials</span>. Select <span style={{fontWeight: "bold"}}>US West (Oregon) – us-west-2</span> for the region.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">7</div>
    <div><h4>Set the format</h4><p>Set the format to <span style={{fontWeight: "bold"}}>CSV</span>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">8</div>
    <div><h4>Set the trigger</h4><p>For <span style={{fontWeight: "bold"}}>Trigger</span>, choose <span style={{fontWeight: "bold"}}>Repeating interval</span>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">9</div>
    <div><h4>Schedule delivery</h4><p>Under <span style={{fontWeight: "bold"}}>Deliver this Schedule</span>, select <span style={{fontWeight: "bold"}}>Daily → Every day</span> at a post-midnight time (for example, 1:00 AM).</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">10</div>
    <div><h4>Set the advanced options</h4><p>Expand <span style={{fontWeight: "bold"}}>Advanced Options</span> and configure the following settings.</p></div>
  </div>
</div>

1. **Send this schedule if**: "there are results".
2. Check "and results changed since last run".
3. Set **Timezone** to "United States – Los Angeles".

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">11</div>
    <div><h4>Test the transfer</h4><p>Use <span style={{fontWeight: "bold"}}>Send Test</span>, and coordinate with your Customer Success Manager to verify the data transfer.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">12</div>
    <div><h4>Save the schedule</h4><p>Select <span style={{fontWeight: "bold"}}>Save All</span> to finalize the schedule.</p></div>
  </div>
</div>
