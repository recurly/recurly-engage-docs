---
title: Stripe
excerpt: >-
  Configuration guide for the Stripe connector in Recurly Engage—activation,
  data sync, 1-Click actions, and subscription management.
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
  <div class="rp-overview">The Stripe integration lets you manage subscriptions, trials, coupons, and usage-based workflows directly from Recurly Engage prompts by connecting to your Stripe account.</div>
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
  <li>You must have a Stripe account with API access credentials and webhook capability.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>Users in Recurly Engage must have <code>stripe_id</code> or <code>email_address</code> traits for action targeting and webhook syncing.</li>
</ul>

# Definition

<div class="rp-definition">The Stripe connector offers two activation methods, Stripe Connect and API key, and supports real-time and nightly data syncs plus 1-Click billing actions from prompts.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-plug" aria-hidden="true"></i></div>
    <strong>Flexible activation</strong>
    <span>Choose Open Authorization (OAuth)-based Stripe Connect or API key authentication.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-bolt" aria-hidden="true"></i></div>
    <strong>Real-time updates</strong>
    <span>Sync subscription status and billing event traits through webhooks.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-sliders" aria-hidden="true"></i></div>
    <strong>Comprehensive actions</strong>
    <span>Upgrade, extend trials, apply coupons, and manage subscriptions without leaving prompts.</span>
  </div>
</div>

# Key details

## Activation

You can activate the Stripe connector using one of two methods: Stripe Connect or an API key. Stripe Connect integrates with Recurly Engage by authenticating with an existing Stripe user account. Alternatively, you can generate a new API key.

### Option 1: Stripe Connect

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Authenticate with Stripe</h4><p>Go to <span style={{fontWeight: "bold"}}>Settings → Actions → Stripe</span> and select the button shown below to authenticate through Stripe.com.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/c2a06fc-Stripe_Connect.png" align="center" width="75%" border={true} />


### Option 2: API key

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Create a restricted key</h4><p>In the Stripe Dashboard, navigate to <span style={{fontWeight: "bold"}}>Developers → API Keys</span>. Create a new <span style={{fontWeight: "bold"}}>Restricted Key</span> and grant the permissions listed below.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/3020621-Stripe_key.png" align="center" width="75%" border={true} />


<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Resource type</td><td>Permissions</td><td>Connect permissions</td></tr>
  <tr><td>Customers</td><td>Write</td><td>None</td></tr>
  <tr><td>Subscriptions</td><td>Write</td><td>None</td></tr>
  <tr><td>Products</td><td>Read</td><td>None</td></tr>
  <tr><td>Prices</td><td>Read</td><td>None</td></tr>
  <tr><td>Coupons</td><td>Read</td><td>None</td></tr>
  <tr><td>Promotion Codes</td><td>Read</td><td>None</td></tr>
</table>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Copy the key into Recurly Engage</h4><p>Copy the generated API key into the <span style={{fontWeight: "bold"}}>Settings → Actions → Stripe</span> form in Recurly Engage.</p></div>
  </div>
</div>

## Data integration

### 1-Click actions

After activation, available plans and coupons sync periodically for use in prompts. Make sure each user record includes `stripe_id` or `email_address`.

### Automated data sync

When you use Stripe Connect, Recurly Engage creates a webhook to sync subscription events in real time. The imported traits include:

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Trait name</td><td>Values</td></tr>
  <tr><td><code>subscription_status</code></td><td><code>incomplete</code>, <code>incomplete_expired</code>, <code>trialing</code>, <code>active</code>, <code>past_due</code>, <code>canceled</code>, <code>unpaid</code>, <code>paused</code> or <code>NONE</code></td></tr>
  <tr><td><code>delinquent</code></td><td><code>true</code>, <code>false</code> (set to <code>true</code> when a payment fails)</td></tr>
  <tr><td><code>current_period_start</code></td><td>&lt;Start date of current billing period&gt;</td></tr>
  <tr><td><code>current_period_end</code></td><td>&lt;End date of current billing period&gt;</td></tr>
  <tr><td><code>canceled_at</code></td><td>&lt;Date of cancellation&gt;</td></tr>
  <tr><td><code>cancel_at_period_end</code></td><td><code>true</code>, <code>false</code></td></tr>
  <tr><td><code>trial_start</code></td><td>&lt;Start date of trial&gt;</td></tr>
  <tr><td><code>trial_end</code></td><td>&lt;End date of trial&gt;</td></tr>
  <tr><td><code>subscription_plan</code></td><td>&lt;Name of current or most recent subscription plan&gt;</td></tr>
  <tr><td><code>recurring_interval</code></td><td><code>day</code>, <code>week</code>, <code>month</code>, <code>year</code></td></tr>
  <tr><td><code>coupon</code></td><td>&lt;Coupon name&gt;</td></tr>
  <tr><td><code>payment_card_brand</code></td><td><code>&lt;card brand&gt;</code> (for example, <code>visa</code>, <code>mastercard</code>, <code>amex</code>, <code>unknown</code>)</td></tr>
  <tr><td><code>payment_card_country</code></td><td><code>&lt;country code&gt;</code> (two-character ISO)</td></tr>
  <tr><td><code>payment_card_expiration</code></td><td>&lt;Payment card expiration date&gt;</td></tr>
  <tr><td><code>payment_card_wallet_type</code></td><td><code>&lt;wallet type&gt;</code> (for example, <code>apple_pay</code>, <code>google_pay</code>, etc.)</td></tr>
</table>

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>You must also perform a nightly comma-separated values (CSV) sync that maps your internal user IDs to Stripe Customer IDs.</div>
</div>

## Supported actions

Attach these 1-Click actions to prompt interactions once your data sync is active:

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Action</td><td>Description</td><td>User dependencies</td><td>Additional instructions</td></tr>
  <tr><td>Update existing subscription</td><td>Switch user to a different product</td><td><code>stripe_id</code> or <code>email_address</code></td><td>Multiple proration options are available. See the <a href="https://stripe.com/docs/billing/subscriptions/upgrade-downgrade#proration" target="_blank">Stripe Proration Guide</a>.</td></tr>
</table>

## Additional resources

<ul class="rp-list">
  <li><a href="https://docs.stripe.com/keys" target="_blank">Stripe API Key Setup</a></li>
  <li><a href="https://stripe.com/docs/billing/subscriptions/upgrade-downgrade#proration" target="_blank">Stripe Proration Guide</a></li>
</ul>
