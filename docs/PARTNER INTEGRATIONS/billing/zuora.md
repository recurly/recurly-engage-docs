---
title: Zuora
excerpt: >-
  Configuration guide for the Zuora connector in Recurly Engage, including
  setup, data sync, and 1-Click subscription actions.
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
  <div class="rp-overview">The Zuora integration connects your Zuora tenant to Recurly Engage, so you can sync subscription data and manage subscriptions directly from prompts.</div>
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
  <li>You must have a Zuora tenant with API access credentials (Client ID and Client Secret).</li>
</ul>

# Definition

<div class="rp-definition">The Zuora connector synchronizes subscription traits and product rate plans from Zuora into Recurly Engage, so you can attach 1-Click actions to prompt interactions and manage subscriptions.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-sliders" aria-hidden="true"></i></div>
    <strong>Real-time subscription control</strong>
    <span>Add, remove, or modify rate plans within your prompts.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-rotate" aria-hidden="true"></i></div>
    <strong>Lifecycle management</strong>
    <span>Suspend, resume, or cancel subscriptions through in-app actions.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-database" aria-hidden="true"></i></div>
    <strong>Automated data flows</strong>
    <span>Keep Recurly Engage updated with the latest account and subscription balances.</span>
  </div>
</div>

# Key details

## Required settings

Under **Settings > Connectors**, configure your Zuora connector by providing:

* **API URL**: Your Zuora REST API endpoint.
* **Client ID** and **Client Secret**: OAuth credentials for API authentication.

## Data integration

Coordinate with Customer Success, or contact <a href="mailto:support@recurly.com">[support@recurly.com](mailto:support@recurly.com)</a>, to schedule daily imports of the following Zuora account and subscription traits into Recurly Engage through Amazon Web Services (AWS) S3 or your preferred comma-separated values (CSV) pipeline:

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Trait name</td><td>Values</td></tr>
  <tr><td><code>account_number</code></td><td>Zuora account number</td></tr>
  <tr><td><code>status</code></td><td><code>Active</code>, <code>Canceled</code>, <code>Draft</code></td></tr>
  <tr><td><code>payment_term</code></td><td>Configured payment term (for example, Net 30)</td></tr>
  <tr><td><code>balance</code></td><td>Outstanding account balance</td></tr>
  <tr><td><code>total_invoice_balance</code></td><td>Total invoiced balance</td></tr>
  <tr><td><code>credit_balance</code></td><td>Available credit balance</td></tr>
  <tr><td><code>contracted_mrr</code></td><td>Contracted monthly recurring revenue</td></tr>
  <tr><td><code>term_type</code></td><td><code>TERMED</code>, <code>EVERGREEN</code></td></tr>
  <tr><td><code>subscription_start_date</code></td><td>Date the subscription term starts</td></tr>
  <tr><td><code>subscription_end_date</code></td><td>Date the subscription term ends</td></tr>
  <tr><td><code>term_start_date</code></td><td>Start date of the current term (may differ from subscription start if renewed)</td></tr>
  <tr><td><code>term_end_date</code></td><td>End date of the current term (null or cancellation date for evergreen subscriptions)</td></tr>
  <tr><td><code>auto_renew</code></td><td><code>true</code> or <code>false</code></td></tr>
  <tr><td><code>rate_plan_name</code></td><td>Name of the most recent rate plan</td></tr>
</table>

## 1-Click actions

Once your connector is activated and rate plans have synchronized, you can configure these 1-Click actions in your prompt editor. The <code>account_number</code> trait must be present on user records to target actions.

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Action</td><td>Description</td><td>Additional instructions</td></tr>
  <tr><td><strong>Add Plan</strong></td><td>Add a specified rate plan to an account</td><td>Select the desired <strong>Product Rate Plan</strong> from the dropdown</td></tr>
  <tr><td><strong>Remove Plan</strong></td><td>Remove a specified rate plan from an account</td><td>Select the <strong>Product Rate Plan</strong> to remove from the dropdown</td></tr>
  <tr><td><strong>Cancel Subscription</strong></td><td>Cancel the active subscription</td><td>Choose a <strong>Cancellation Policy</strong> (<code>EndOfCurrentTerm</code>, <code>EndOfLastInvoicePeriod</code>, <code>SpecificDate</code>) and <strong>Apply Credit</strong> (<code>true</code>/<code>false</code>)</td></tr>
  <tr><td><strong>Suspend Subscription</strong></td><td>Pause an active subscription</td><td>Specify <strong>Suspend Policy</strong> (<code>Today</code>, <code>EndOfLastInvoicePeriod</code>, <code>SpecificDate</code>, <code>FixedPeriodsFromToday</code>)</td></tr>
  <tr><td><strong>Resume Subscription</strong></td><td>Reactivate a suspended subscription</td><td>Select <strong>Resume Policy</strong> (<code>Today</code>, <code>FixedPeriodsFromSuspendDate</code>, <code>FixedPeriodsFromToday</code>, <code>SpecificDate</code>)</td></tr>
  <tr><td><strong>Change Auto Renewal</strong></td><td>Toggle auto-renewal setting</td><td>Choose <strong>AutoRenew</strong> (<code>true</code> or <code>false</code>)</td></tr>
  <tr><td><strong>Create Subscription</strong></td><td>Create a new subscription with specified rate plan</td><td>Provide <strong>contractEffectiveDate</strong>, <strong>renewalTerm</strong>, <strong>Rate Plan</strong>, and <strong>Term Type</strong></td></tr>
</table>

## Configure a 1-Click Zuora action

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Add an action</h4><p>In your prompt editor, select <span style={{fontWeight: "bold"}}>Add Action</span>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Choose Zuora</h4><p>Choose <span style={{fontWeight: "bold"}}>Zuora</span> as the connector and select the action you want (for example, <span style={{fontWeight: "bold"}}>Add Plan</span>).</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Pick the plan or policy</h4><p>Pick the <span style={{fontWeight: "bold"}}>Product Rate Plan</span> or policy settings from the dropdown.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Save and publish</h4><p>Save and publish your prompt.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/f6b632e-Zuora_action.png" align="center" width="75%" border={true} />


## Additional references

<ul class="rp-list">
  <li><a href="https://www.zuora.com/developer/api-reference/" target="_blank">Zuora API reference</a></li>
</ul>
