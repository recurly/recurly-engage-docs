---
title: Chargify
excerpt: Configuration and usage guide for the Chargify connector in Recurly Engage.
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
  <div class="rp-overview">The Chargify integration lets you manage subscriptions and coupons directly from your prompts, using your Chargify billing system to automate user plan changes and coupon applications.</div>
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
  <li>You must have a valid Chargify account with API access.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>User records in Recurly Engage must include the <code>chargify_id</code> trait for action targeting.</li>
</ul>

# Definition

<div class="rp-definition">The Chargify connector synchronizes products, coupons, and subscription data from Chargify into Recurly Engage, so you can trigger billing-related actions from within prompts.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-gears" aria-hidden="true"></i></div>
    <strong>Automated billing workflows</strong>
    <span>Create or cancel subscriptions directly from prompts.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-ticket" aria-hidden="true"></i></div>
    <strong>Coupon management</strong>
    <span>Apply coupon codes in real time as users interact.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-route" aria-hidden="true"></i></div>
    <strong>Uninterrupted user flow</strong>
    <span>Keep users in the flow without manual backend steps.</span>
  </div>
</div>

# Key details

## Required settings

Configure your Chargify connector under **Settings > Connectors**:

* **API Key**: Your Chargify API key.
* **Domain**: Your Chargify site domain (for example, `your-site.chargify.com`).

## Data integration

* **Products and coupons** are synchronized on a scheduled basis, so they're available in prompt configurations.
* **Chargify ID** must be mapped to the user's `chargify_id` trait in Recurly Engage for action execution.

## Supported actions

Use these actions within your prompt configurations to perform billing operations:

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Action</td><td>Description</td><td>User dependencies</td><td>Additional instructions</td></tr>
  <tr><td>Create subscription</td><td>Subscribes a user to a specified Chargify product plan</td><td><code>chargify_id</code></td><td>Select the desired plan from the connector dropdown.</td></tr>
  <tr><td>Cancel subscription</td><td>Cancels a user's existing subscription to a product plan</td><td><code>chargify_id</code></td><td>Choose which plan to cancel on the prompt screen.</td></tr>
  <tr><td>Add coupon code</td><td>Applies a coupon code to a user's subscription</td><td><code>chargify_id</code></td><td>Select both the plan and coupon code on the prompt.</td></tr>
</table>
