---
title: Chargebee
excerpt: >-
  Configuration guide for the Chargebee connector in Recurly Engage, including
  activation, data sync, and 1-Click subscription actions.
deprecated: false
hidden: false
metadata:
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">The Chargebee integration lets you sync your subscription data and run billing actions directly from Recurly Engage prompts, using your existing Chargebee account.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

# Definition

<div class="rp-definition">The Chargebee connector imports subscription traits nightly from three data sources (subscription info, payment and dunning status, and payment source details) and provides actions for managing subscriptions through prompts.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-file-invoice-dollar" aria-hidden="true"></i></div>
    <strong>Streamlined billing workflows</strong>
    <span>Manage subscriptions, trials, coupons, and payment recovery without leaving the prompt interface.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-database" aria-hidden="true"></i></div>
    <strong>Comprehensive data sync</strong>
    <span>Nightly imports pull subscription state, invoice and dunning status, and card expiration data to keep your segments and prompts accurate.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-sliders" aria-hidden="true"></i></div>
    <strong>Flexible subscription actions</strong>
    <span>Support the full subscription lifecycle, from onboarding through cancellation and reactivation.</span>
  </div>
</div>

# Key details

## Activation

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Generate an API key</h4><p>Log in to your Chargebee account and generate an API key.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Add the key to Recurly Engage</h4><p>In Recurly Engage, navigate to <span style={{fontWeight: "bold"}}>Settings &gt; Integrations &gt; Chargebee</span> and paste your API key.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Activate the connector</h4><p>Toggle <span style={{fontWeight: "bold"}}>Active</span> to <span style={{fontWeight: "bold"}}>On</span>.</p></div>
  </div>
</div>

## Imported traits

Nightly imports pull the following traits from Chargebee.

### Subscription traits

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Trait name</td><td>Description</td></tr>
  <tr><td><code>state</code></td><td>Current state of the subscription (pending, active, cancelled, expired)</td></tr>
  <tr><td><code>plan_code</code></td><td>Plan the customer is subscribed to</td></tr>
  <tr><td><code>currency</code></td><td>Currency of the subscription</td></tr>
  <tr><td><code>current_period_started_at</code></td><td>Date/time when the current billing period started</td></tr>
  <tr><td><code>current_period_ends_at</code></td><td>Date/time when the current billing period ends</td></tr>
  <tr><td><code>trial_started_at</code></td><td>Date/time when the trial period began</td></tr>
  <tr><td><code>trial_ends_at</code></td><td>Date/time when the trial period ends</td></tr>
  <tr><td><code>activated_at</code></td><td>Date/time the subscription became active</td></tr>
  <tr><td><code>cancelled_at</code></td><td>Date/time the subscription was cancelled</td></tr>
  <tr><td><code>expires_at</code></td><td>Date/time when the subscription will churn</td></tr>
</table>

### Dunning traits

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Trait name</td><td>Description</td></tr>
  <tr><td><code>status</code></td><td>Invoice status (pending, processing, past_due, paid, failed, voided)</td></tr>
</table>

### Payment traits

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Trait name</td><td>Description</td></tr>
  <tr><td><code>card_expiry_month</code></td><td>Month the payment card expires</td></tr>
  <tr><td><code>card_expiry_year</code></td><td>Year the payment card expires</td></tr>
</table>

## Supported actions

Once your connector is active and data is synced, you can attach these 1-Click actions to prompt interactions. The customer ID trait must be present on users.

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Action</td><td>Description</td></tr>
  <tr><td>Switch Subscription</td><td>Changes a user's subscription to a new plan</td></tr>
  <tr><td>Create Subscription</td><td>Creates a subscription for an existing customer account</td></tr>
  <tr><td>Reactivate Subscription</td><td>Reactivates a user's cancelled or expired subscription</td></tr>
  <tr><td>Cancel Subscription</td><td>Cancels a user's subscription at period end or immediately</td></tr>
  <tr><td>Terminate Subscription</td><td>Immediately deletes a subscription record</td></tr>
  <tr><td>Update Auto Collection</td><td>Toggles automatic card charging on or off</td></tr>
  <tr><td>Pause Subscription</td><td>Temporarily halts billing for a user</td></tr>
  <tr><td>Resume Subscription</td><td>Restarts billing for a paused user</td></tr>
  <tr><td>Convert Trial</td><td>Converts a trial to a paid subscription immediately</td></tr>
  <tr><td>Extend Trial Period</td><td>Pushes the trial end date to a future date</td></tr>
  <tr><td>Apply Coupon Code</td><td>Applies a coupon or discount to a user's subscription</td></tr>
  <tr><td>Update Subscription Price</td><td>Manually overrides the price on a per-subscription basis</td></tr>
  <tr><td>Record Usage</td><td>Logs a usage record for a subscription add-on (metered billing)</td></tr>
</table>
