---
title: Recurly
excerpt: >-
  Configuration guide for the Recurly connector in Recurly Engage, including
  activation, data sync, and 1-Click subscription actions.
deprecated: false
hidden: false
metadata:
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">The Recurly connector links your Recurly account to Recurly Engage, so you can sync subscription data and run billing actions right from your prompts. Apply coupons, switch plans, pause or resume subscriptions, and more — without leaving the prompt interface.</div>
  <div style={{position: "relative", paddingTop: "56.25%", marginBottom: "28px", borderRadius: "10px", overflow: "hidden"}}><iframe src="https://www.loom.com/embed/46bc074c2ae84fcd8fd55d7b342859d2" title="Recurly connector overview" allow="autoplay; fullscreen" allowtransparency="true" frameBorder="0" scrolling="no" allowFullScreen style={{position: "absolute", top: 0, left: 0, width: "100%", height: "100%", border: "none"}}></iframe></div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly Engage plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li><strong>Company</strong> or <strong>App Administrator</strong> permissions in Recurly Engage</li>
  <li>A Recurly account with API access and a valid API key</li>
  <li>The <strong>Integrations</strong> role in Recurly Subscription Management to configure Automated Exports — some exports also require the <strong>Admin</strong> role</li>
</ul>

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>If your application uses custom user IDs (Account Codes), turn on "Use Account Code" in the connector settings.</div>
</div>

# Definition

<div class="rp-definition">The Recurly connector is a built-in integration that syncs subscription data from your Recurly account into Recurly Engage as user traits, and enables 1-Click billing actions — like applying coupons, switching plans, or canceling — to be triggered directly from prompts. It connects Recurly's billing data to Engage's segmentation and prompt delivery without requiring custom code.</div>

# Key benefits

<div class="rp-benefits rp-benefits-2x2">
<div class="rp-benefit">
<div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
<strong>Subscriber segmentation without custom code</strong>
<span>Sync plan codes, subscription state, billing dates, and payment data as user traits you can filter on the moment the connector is active.</span>
</div>
<div class="rp-benefit">
<div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
<strong>1-Click billing actions from prompts</strong>
<span>Let subscribers pause, switch plans, apply coupons, or cancel directly from a prompt — without leaving your site or touching your backend.</span>
</div>
<div class="rp-benefit">
<div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
<strong>Real-time updates via webhooks</strong>
<span>Keep card expiration dates, past-due status, and active coupon codes current as billing events happen in Recurly — no waiting for the next nightly sync.</span>
</div>
<div class="rp-benefit">
<div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
<strong>Custom field targeting</strong>
<span>Map your Recurly subscription custom fields into Engage traits for precise segmentation on your own subscription data.</span>
</div>
</div>

# Key details

## Setup

<div class="rp-steps">
<div class="rp-step">
<div class="rp-step-num">1</div>
<div><h4>Generate an API key</h4><p>Generate an API key in the Recurly console.</p></div>
</div>
<div class="rp-step">
<div class="rp-step-num">2</div>
<div><h4>Enter the key in Engage</h4><p>In Recurly Engage, go to <strong>Settings → Integrations → Recurly</strong> and enter the key.</p></div>
</div>
<div class="rp-step">
<div class="rp-step-num">3</div>
<div><h4>Configure account matching</h4><p>Toggle <strong>Use Account Code</strong> if your Engage user IDs match Recurly account codes.</p></div>
</div>
<div class="rp-step">
<div class="rp-step-num">4</div>
<div><h4>Activate the connector</h4><p>Activate the connector to begin syncing data.</p></div>
</div>
</div>

### Required Recurly exports

Four automated exports must be enabled in Recurly Subscription Management using the **"Modified Yesterday"** filter:

<ul class="rp-list">
<li>Billing Info (v6)</li>
<li>Invoices — Summary (v5)</li>
<li>Subscriptions (v5)</li>
<li>External Subscriptions (v5) — required only if using App Store or Google Play billing</li>
</ul>

<div class="rp-callout rp-callout-warning">
<div><strong><i class="fa-solid fa-triangle-exclamation" aria-hidden="true"></i> Warning</strong>Without these exports, the connector will appear active but subscription traits will not populate. Verify all four are enabled with the "Modified Yesterday" filter before going live.</div>
</div>

## Subscription traits

The following traits are synced from Recurly and made available for segmentation and targeting in Engage. Traits noted as _(webhook)_ are updated in real time when Recurly sends a webhook event; all others sync via the nightly CSV export.

<table class="rp-gw-table">
<tr class="rp-thead-row"><td>Trait</td><td>Description</td></tr>
<tr><td><code>account_code</code></td><td>The Recurly account identifier — the join key linking a Recurly account to an Engage user. Must match the user's ID in Engage, or be mapped via <span style={{fontWeight: "bold"}}>Use Account Code</span>.</td></tr>
<tr><td><code>plan_code</code></td><td>The code of the plan the customer is currently subscribed to.</td></tr>
<tr><td><code>plan_name</code></td><td>The display name of the current plan.</td></tr>
<tr><td><code>state</code></td><td>Current subscription state. Possible values: <code>pending</code>, <code>active</code>, <code>canceled</code>, <code>expired</code>.</td></tr>
<tr><td><code>currency</code></td><td>The three-letter currency code for the subscription (e.g. <code>USD</code>, <code>EUR</code>).</td></tr>
<tr><td><code>total_recurring_amount</code></td><td>The total amount billed on a recurring basis, in the subscription's currency.</td></tr>
<tr><td><code>current_period_started_at</code></td><td>Date and time the current billing period started.</td></tr>
<tr><td><code>current_period_ends_at</code></td><td>Date and time the current billing period ends.</td></tr>
<tr><td><code>trial_started_at</code></td><td>Date and time the trial period began.</td></tr>
<tr><td><code>trial_ends_at</code></td><td>Date and time the trial period ends.</td></tr>
<tr><td><code>activated_at</code></td><td>Date and time the subscription became active.</td></tr>
<tr><td><code>canceled_at</code></td><td>Date and time the subscription was canceled.</td></tr>
<tr><td><code>expires_at</code></td><td>Date and time the subscription will fully expire.</td></tr>
<tr><td><code>status</code></td><td>Invoice status from the subscriber's most recent invoice. Possible values: <code>pending</code>, <code>processing</code>, <code>past_due</code>, <code>paid</code>, <code>failed</code>, <code>voided</code>. <em>(webhook)</em></td></tr>
<tr><td><code>maintenance_url</code></td><td>Link to the subscriber's hosted account maintenance page in Recurly, if the hosted pages feature is enabled.</td></tr>
<tr><td><code>active_coupon_codes</code></td><td>Comma-separated list of coupon codes active on the subscriber's most recent invoice. <em>(webhook)</em></td></tr>
<tr><td><code>plan_coupon_codes</code></td><td>Comma-separated list of coupon codes applied at the subscription level. Distinct from <code>active_coupon_codes</code>, which reflects invoice-level redemptions. <em>(webhook)</em></td></tr>
<tr><td><code>card_expiration_date</code></td><td>The subscriber's credit card expiration date, formatted as <code>YYYY-MM-01</code>. Empty if no card is on file. <em>(webhook)</em></td></tr>
<tr><td><code>has_billing_info</code></td><td>Whether the account has a payment method on file (<code>true</code> or <code>false</code>). Useful for targeting users who need to add payment details. <em>(webhook)</em></td></tr>
<tr><td><code>payment_method_type</code></td><td>The type of payment method on file. Common values: <code>credit_card</code>, <code>paypal</code>, <code>amazon</code>, <code>check</code>. <em>(webhook)</em></td></tr>
<tr><td><code>past_due_invoice_date</code></td><td>The date of the subscriber's most recent past-due invoice. Set when a <code>past_due</code> webhook event is received. <em>(webhook)</em></td></tr>
</table>

<div class="rp-callout rp-callout-note">
<div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>Traits marked <em>(webhook)</em> require Recurly webhooks to be configured and active. The nightly CSV export does not populate these traits.</div>
</div>

## Subscription add-ons

The `subscription_add_ons` trait contains a list of all add-ons currently attached to the subscriber's subscription. It can be used to segment users based on which add-ons they have active.

Each item in the list is an object with the following fields:

<table class="rp-gw-table">
<tr class="rp-thead-row"><td>Field</td><td>Description</td></tr>
<tr><td><code>add_on_code</code></td><td>The unique code identifying the add-on.</td></tr>
<tr><td><code>add_on_name</code></td><td>The display name of the add-on.</td></tr>
<tr><td><code>quantity</code></td><td>How many units of the add-on the subscriber has.</td></tr>
<tr><td><code>unit_amount</code></td><td>The per-unit price of the add-on.</td></tr>
<tr><td><code>created_at</code></td><td>Date and time the add-on was added to the subscription.</td></tr>
<tr><td><code>expired_at</code></td><td>Date and time the add-on expired, if applicable.</td></tr>
</table>

<div class="rp-callout rp-callout-note">
<div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong><code>subscription_add_ons</code> is updated via Recurly webhooks. Ensure webhooks are active for this trait to stay current.</div>
</div>

## External subscription traits

For merchants using Recurly's App Management feature — subscriptions sold through the Apple App Store or Google Play — an additional set of traits is synced nightly from the External Subscriptions export.

<table class="rp-gw-table">
<tr class="rp-thead-row"><td>Trait</td><td>Description</td></tr>
<tr><td><code>external_product_reference_code</code></td><td>The reference code for the external product.</td></tr>
<tr><td><code>external_product_reference_source</code></td><td>The source of the external subscription. Common values: <code>apple_app_store</code>, <code>google_play_store</code>.</td></tr>
<tr><td><code>external_product_name</code></td><td>The display name of the external product.</td></tr>
<tr><td><code>external_product_activated_at</code></td><td>Date and time the external subscription was activated.</td></tr>
<tr><td><code>external_product_expires_at</code></td><td>Date and time the external subscription expires.</td></tr>
<tr><td><code>external_product_state</code></td><td>Current state of the external subscription.</td></tr>
</table>

<div class="rp-callout rp-callout-warning">
<div><strong><i class="fa-solid fa-triangle-exclamation" aria-hidden="true"></i> Warning</strong>External subscription traits require the <span style={{fontWeight: "bold"}}>External Subscriptions (v5)</span> export to be enabled in Recurly Subscription Management. If you're not using Recurly App Management, this section doesn't apply.</div>
</div>

## 1-Click actions — required traits

To use 1-Click subscription actions in prompts — such as Apply Coupon, Switch Plan, or Cancel Subscription — Recurly Engage needs to look up the subscriber's account in Recurly. Depending on your integration configuration, one of the following traits must be present on the user's profile:

<table class="rp-gw-table">
<tr class="rp-thead-row"><td>Trait</td><td>When to use</td></tr>
<tr><td><code>account_code</code></td><td>Used when <span style={{fontWeight: "bold"}}>Use Account Code</span> is enabled in the integration settings. Recurly Engage assumes the user's ID matches their Recurly account code — no separate trait is needed.</td></tr>
<tr><td><code>recurly_account_code</code></td><td>Used when <span style={{fontWeight: "bold"}}>Use Account Code</span> is <em>not</em> enabled and your Engage user IDs differ from Recurly account codes. Set this trait to the subscriber's Recurly account code so Engage can look up their account.</td></tr>
<tr><td><code>recurly_subscription_id</code></td><td>Optional. When set, Recurly Engage targets this specific subscription rather than looking up the subscriber's active subscription automatically. Useful for multi-subscription accounts.</td></tr>
</table>

## Custom subscription fields

If you use Recurly's custom subscription fields feature, Recurly Engage can sync those field values as additional user traits. This lets you use any custom data stored on subscriptions in Recurly for segmentation and targeting in Engage.

Custom field mapping is configured per app in **Pulse → Settings → Integrations → Recurly**. For each custom field, you define the Recurly field name and, optionally, a different trait name to use in Engage. Trait names are app-specific and will vary by merchant.

Contact <a href="mailto:support@recurly.com">[support@recurly.com](mailto:support@recurly.com)</a> or your CSM to enable this feature.

## Available 1-Click actions

Once connected, the following actions can be triggered directly from a prompt without the subscriber leaving your site:

<ul class="rp-list">
<li>Apply Coupon Code</li>
<li>Pause Subscription</li>
<li>Resume Subscription</li>
<li>Switch Plan</li>
<li>Create Subscription</li>
<li>Reactivate Subscription</li>
<li>Cancel Subscription</li>
<li>Update Pricing</li>
<li>Convert Trial</li>
<li>Record Usage</li>
</ul>
