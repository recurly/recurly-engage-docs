---
title: Evergent
excerpt: >-
  Configuration guide for the Evergent connector in Recurly Engage—activation,
  data sync, and supported subscription actions.
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
  <div class="rp-overview">The Evergent integration lets you synchronize subscriber data and trigger subscription management actions from Recurly Engage prompts by connecting to your Evergent REST API.</div>
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
</ul>

### Limitations

<ul class="rp-list">
  <li>The connector uses the Evergent REST API. Legacy SOAP-only setups may require assistance from Customer Success. Contact your Customer Success team or <a href="mailto:support@recurly.com">support@recurly.com</a>.</li>
</ul>

# Definition

<div class="rp-definition">The Evergent connector for Recurly Engage synchronizes subscriber traits from Evergent and enables prompt-driven subscription workflows, such as coupon redemption, service changes, pauses, and resumes.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-bolt" aria-hidden="true"></i></div>
    <strong>Real-time subscriber data</strong>
    <span>Import detailed subscription traits for precise segment targeting.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-sliders" aria-hidden="true"></i></div>
    <strong>Direct subscription control</strong>
    <span>Run subscription actions (pause, resume, and change service) directly from prompts.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-wand-magic-sparkles" aria-hidden="true"></i></div>
    <strong>Customizable workflows</strong>
    <span>Tailor actions to your Evergent instance and business logic.</span>
  </div>
</div>

# Key details

## Activation

To enable the Evergent connector, go to **Settings > Connectors** and provide:

* **Domain**: Your Evergent API domain.
* `apiKey`: Your Evergent REST API key.
* `channelPartnerID`: Your channel partner identifier.

## Data integration

Schedule a daily comma-separated values (CSV) export from Evergent into Recurly Engage through Amazon S3. The CSV should include the following subscriber traits for audience targeting:

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Trait name</td><td>Description</td></tr>
  <tr><td><code>customer_id</code></td><td>Customer/User ID</td></tr>
  <tr><td><code>business_unit</code></td><td>Business unit owning subscription</td></tr>
  <tr><td><code>country</code></td><td>Billing country</td></tr>
  <tr><td><code>current_payment_method</code></td><td>[Google Wallet, App Store Billing, Credit Card, Roku Payment, Coupon, etc]</td></tr>
  <tr><td><code>pack_id</code></td><td>Package ID</td></tr>
  <tr><td><code>package</code></td><td>Package Name</td></tr>
  <tr><td><code>pack_price</code></td><td>Package Price</td></tr>
  <tr><td><code>pack_type</code></td><td>Package Type</td></tr>
  <tr><td><code>currency_code</code></td><td>Three-character currency code</td></tr>
  <tr><td><code>valid_from_date</code></td><td>Billing period start</td></tr>
  <tr><td><code>valid_to_date</code></td><td>Billing period end</td></tr>
  <tr><td><code>payment_status</code></td><td>[Declined, Posted]</td></tr>
  <tr><td><code>payment_type</code></td><td>[Renewal, Purchase]</td></tr>
  <tr><td><code>payment_date</code></td><td>Date of most recent payment</td></tr>
  <tr><td><code>declined_reason</code></td><td>Reason for payment decline</td></tr>
  <tr><td><code>promotion_amount</code></td><td>Promotion amount (if applicable)</td></tr>
  <tr><td><code>promotion_code</code></td><td>Promotion code (if applicable)</td></tr>
  <tr><td><code>coupon_code</code></td><td>Coupon code (if applicable)</td></tr>
  <tr><td><code>cancellation_requested_date</code></td><td>Date of cancellation request (if applicable)</td></tr>
  <tr><td><code>classification</code></td><td>Subscription classification status ([Paid, Free Trial, Retail, etc])</td></tr>
</table>

## Supported actions

<div class="rp-callout rp-callout-important">
  <div><strong><i class="fa-solid fa-circle-exclamation" aria-hidden="true"></i> Important</strong>Evergent configurations can vary. Verify which APIs your instance supports.</div>
</div>

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Action</td><td>Description</td><td>API method</td></tr>
  <tr><td>Redeem Coupon</td><td>Apply a coupon code to an existing package/product</td><td><code>redeemCoupon</code></td></tr>
  <tr><td>Change Service</td><td>Upgrade or downgrade an existing service (specify from and to services)</td><td><code>changeService</code></td></tr>
  <tr><td>Pause Subscription</td><td>Pause an active subscription for up to 90 days</td><td><code>pauseSubscription</code></td></tr>
  <tr><td>Resume Subscription</td><td>Resume a previously paused subscription</td><td><code>resumeSubscription</code></td></tr>
  <tr><td>Reactivate Subscription</td><td>Reactivate a subscription marked for cancellation (subject to package terms)</td><td><code>reactivateSubscription</code></td></tr>
  <tr><td>Remove Subscription</td><td>Remove (cancel) a subscription at period end</td><td><code>removeSubscription</code></td></tr>
</table>
