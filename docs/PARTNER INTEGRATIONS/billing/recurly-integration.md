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

<div class="rp-definition">The Recurly connector imports subscription traits from your Recurly account into Recurly Engage every night, and gives you 1-Click actions for managing subscriptions — applying coupons, switching plans, pausing, and resuming — directly from your prompts.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Billing without leaving the prompt</strong>
    <span>Apply coupons, switch plans, pause, and resume subscriptions right from the prompt interface.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Data that stays current</strong>
    <span>Nightly imports keep your segments and prompts aligned with the latest subscription state.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Flexible configuration</strong>
    <span>Map your own account codes and choose from a range of subscription actions.</span>
  </div>
</div>

# Key details

## Activation

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Generate an API key</h4><p>In the Recurly console, generate an API key for the connector to use.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Add the key to Recurly Engage</h4><p>Go to Settings → Integrations → Recurly and paste your API key.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Set Use Account Code</h4><p>Toggle Use Account Code to On if you map your own user IDs to Recurly account codes.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Activate the connector</h4><p>Toggle Active to On.</p></div>
  </div>
</div>

For help generating a key, see the <a href="https://docs.recurly.com/recurly-engage/docs/api-actions" target="_blank">API key instructions</a>.

## Configure automated exports in Recurly Subscription Management

The connector's nightly sync depends on four exports being enabled on the Recurly Subscription Management side.

<div class="rp-callout rp-callout-warning">
  <div><strong><i class="fa-solid fa-triangle-exclamation" aria-hidden="true"></i> Warning</strong>Without these four exports enabled, the connector still shows as Active in Recurly Engage — but no traits will populate.</div>
</div>

In Recurly Subscription Management, go to **Integrations → Automated Exports** and enable each of the following, filtered on **Modified Yesterday**:

<table class="rp-pm-table">
  <tr class="rp-thead-row"><td>Export</td><td>Version</td><td>Filter</td></tr>
  <tr><td>Billing Info</td><td>v6</td><td>Modified Yesterday</td></tr>
  <tr><td>Invoices — Summary</td><td>v5</td><td>Modified Yesterday</td></tr>
  <tr><td>Subscriptions</td><td>v5</td><td>Modified Yesterday</td></tr>
  <tr><td>External Subscriptions</td><td>v5</td><td>Modified Yesterday — only if you use App Management</td></tr>
</table>

The Modified Yesterday filter keeps each export scoped to the previous day's changes, which is what lets Recurly Engage stay in sync on its nightly cadence. For general setup steps, see <a href="https://docs.recurly.com/recurly-subscriptions/docs/automated-exports" target="_blank">Automated exports</a>.

## Verify the connection

Once exports are enabled in Recurly Subscription Management and the connector is active in Recurly Engage, confirm both sides are set up correctly:

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Check the connector status</h4><p>In Recurly Engage, go to Settings → Integrations → Recurly and confirm the connector shows Active.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Confirm the exports</h4><p>In Recurly Subscription Management, go to Integrations → Automated Exports and confirm all four exports are enabled with a recent successful run.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Check your user traits</h4><p>In Recurly Engage, go to Settings → User Traits and confirm the imported attributes are populating.</p></div>
  </div>
</div>

If traits aren't appearing after the first nightly cycle, check that:

<ul class="rp-list">
  <li>All four exports are still enabled and haven't been superseded by a newer version. Recurly doesn't auto-upgrade export versions, so when a new version is released you'll need to delete and recreate the export configuration manually.</li>
  <li>The API key in the connector hasn't expired or been regenerated on the Recurly Subscription Management side.</li>
  <li>The Modified Yesterday filter is applied to every export. Without it, an export can return more or less data than the connector expects.</li>
</ul>

## Data integration

Automated exports sync on a nightly basis, and each run imports the subscription traits below. Learn more about <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-engage-integration#step-4-import-user-traits-using-both-recurly-and-recurly-engage-sites" target="_blank">importing user traits</a> with Recurly, or about configuring <a href="https://docs.recurly.com/recurly-subscriptions/docs/automated-exports" target="_blank">Automated Exports</a> in Recurly Subscription Management. To receive near real-time data instead of waiting for the nightly sync, integrate with <a href="https://docs.recurly.com/recurly-engage/docs/recurly-webhooks" target="_blank">Recurly webhooks</a>.

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Trait</td><td>Description</td></tr>
  <tr><td><code>state</code></td><td>Current state of the subscription (pending, active, canceled, expired)</td></tr>
  <tr><td><code>plan_code</code></td><td>Plan code the customer is subscribed to</td></tr>
  <tr><td><code>currency</code></td><td>Currency of the subscription</td></tr>
  <tr><td><code>current_period_started_at</code></td><td>Date and time the current billing period starts</td></tr>
  <tr><td><code>current_period_ends_at</code></td><td>Date and time the current billing period ends</td></tr>
  <tr><td><code>trial_started_at</code></td><td>Date and time the trial period began</td></tr>
  <tr><td><code>trial_ends_at</code></td><td>Date and time the trial period ends</td></tr>
  <tr><td><code>activated_at</code></td><td>Date and time the subscription became active</td></tr>
  <tr><td><code>canceled_at</code></td><td>Date and time the subscription was canceled</td></tr>
  <tr><td><code>expires_at</code></td><td>Date and time the subscription will churn</td></tr>
  <tr><td><code>status</code></td><td>Invoice status (pending, processing, past_due, paid, failed, voided)</td></tr>
  <tr><td><code>maintenance_url</code></td><td>Link to the customer's hosted account maintenance page, if enabled</td></tr>
  <tr><td><code>total_recurring_amount</code></td><td>The total amount, in the subscription's currency, billed on a recurring basis</td></tr>
</table>

## Supported actions

Once your connector is active and data is synced, you can attach these 1-Click actions to prompt interactions.

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>Each user must have the account_code or account_number trait present for these actions to work.</div>
</div>

<table class="rp-pm-table">
  <tr class="rp-thead-row"><td>Action</td><td>Description</td><td>API integration</td><td>Additional instructions</td></tr>
  <tr><td>Apply Coupon Code</td><td>Applies a coupon code to the user's account or subscription</td><td>Coupon Redemption</td><td>Select the coupon code</td></tr>
  <tr><td>Pause Subscription</td><td>Pauses a user's subscription</td><td>Pause Subscription</td><td>Select how many billing cycles to pause for</td></tr>
  <tr><td>Resume Subscription</td><td>Resumes a paused subscription</td><td>Resume Subscription</td><td>—</td></tr>
  <tr><td>Switch Subscription</td><td>Switches the user to a new plan</td><td>Subscription Change</td><td>Select the plan</td></tr>
  <tr><td>Create Subscription</td><td>Creates a subscription for an existing account</td><td>Create Subscription</td><td>Select the plan and enter the currency</td></tr>
  <tr><td>Reactivate Subscription</td><td>Reactivates a canceled subscription</td><td>Reactivate Subscription</td><td>—</td></tr>
  <tr><td>Update Subscription Price</td><td>Updates the price of an active subscription</td><td>Subscription Change</td><td>—</td></tr>
  <tr><td>Convert Trial</td><td>Converts a trial to a paid subscription</td><td>Convert Trial</td><td>—</td></tr>
  <tr><td>Record Usage</td><td>Logs a usage record for a subscription add-on</td><td>Log Usage Record</td><td>Select the add-on and amount</td></tr>
  <tr><td>Cancel Subscription</td><td>Stops auto-renewal for an active subscription</td><td>Cancel Subscription</td><td>Select refund option</td></tr>
</table>
