---
title: Goals
excerpt: How to set up and use custom conversion goals for your Recurly Engage prompts.
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
  <div class="rp-overview">Custom goals let you track conversions beyond the built-in "prompt accepted" metric, such as page visits, API events, or activity in external systems. Attach a goal to a prompt and see how many users complete the action you care about.</div>
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

### Limitations

<ul class="rp-list">
  <li>At least one usage tracker must exist before you add a custom goal.</li>
</ul>

# Definition

<div class="rp-definition">A custom goal is a user-defined conversion event, tracked through a usage tracker, that you attach to a prompt to measure success against your own criteria.</div>

# Key benefits

<div class="rp-benefits rp-benefits-2x2">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-ruler-combined" aria-hidden="true"></i></div>
    <strong>Flexible measurement</strong>
    <span>Define conversions like page visits, payment completions, or external API events.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-bullseye" aria-hidden="true"></i></div>
    <strong>Accurate attribution</strong>
    <span>Attribute custom goals to prompt interactions with configurable time windows.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-chart-line" aria-hidden="true"></i></div>
    <strong>Deeper insights</strong>
    <span>Compare prompt acceptance with actual business outcomes to optimize more effectively.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-bolt" aria-hidden="true"></i></div>
    <strong>Near real-time updates</strong>
    <span>The enhanced integration with Recurly Subscription Management provides near real-time subscription status information, so you can target and track custom events in Recurly Engage faster. <a href="https://docs.recurly.com/recurly-engage/docs/recurly-webhooks#/" target="_blank">Learn more</a></span>
  </div>
</div>

# Key details

## What you can track

<ul class="rp-list">
  <li>Visits to a specific URL path (for example, <code>/payment-updated</code>)</li>
  <li>Arrivals on a particular app screen (mobile or TV)</li>
  <li>Backend events (payment processed, subscription changed)</li>
  <li>External system activities accessible through your usage tracker</li>
  <li>Recurly Subscription Management webhook events, which deliver near real-time subscription status updates (for example, plan changes, payment failures, and cancellations) for instant targeting and custom goal events in Recurly Engage. <a href="https://docs.recurly.com/recurly-engage/docs/recurly-webhooks#/" target="_blank">Learn more</a></li>
</ul>

To use a custom goal, first create a <a href="/recurly-engage/docs/usage-tracking-1" target="_blank">usage tracker</a>. Then follow the steps below to attach it to a prompt.

## Attach a custom goal to a prompt

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Locate your usage tracker</h4><p>Find the usage tracker you want to use. In this example, we track when a user updates their payment method and lands on <code>/payment-updated</code>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/c80c651-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Edit the prompt details</h4><p>Open the prompt you want to measure and select <span style={{fontWeight: "bold"}}>Edit prompt details</span>.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Add a custom goal</h4><p>Scroll to the <span style={{fontWeight: "bold"}}>Custom Goal</span> section and select <span style={{fontWeight: "bold"}}>Add custom goal</span>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/ea36176-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Configure and save the goal</h4><p>In the popup, select your usage tracker, set the attribution window (for example, 24 hours), and select <span style={{fontWeight: "bold"}}>Save</span>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/075d4bd-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Publish your prompt</h4><p>Publish your prompt to start recording custom goal completions.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">6</div>
    <div><h4>Review performance</h4><p>Under <span style={{fontWeight: "bold"}}>Performance</span>, a <span style={{fontWeight: "bold"}}>Custom goal</span> bar displays the number of users who completed the tracked action after interacting with the prompt.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/f478e3a-image.png" align="center" width="75%" border={true} />


<br />

<br />
