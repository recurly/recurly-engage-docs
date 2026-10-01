---
title: Braintree
excerpt: Setup and action guide for the Braintree connector in Recurly Engage.
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
  <div class="rp-overview">The Braintree integration lets you subscribe users to plans or apply discounts directly from Recurly Engage prompts, using your Braintree gateway.</div>
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
  <li>You must have an active Braintree account with access to the control panel to retrieve your gateway credentials.</li>
</ul>

# Definition

<div class="rp-definition">The Braintree connector syncs with your Braintree gateway using your merchant credentials, so you can trigger subscription management actions directly from prompts.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-credit-card" aria-hidden="true"></i></div>
    <strong>Direct payment workflows</strong>
    <span>Subscribe users to plans or apply discounts without redirecting them.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-lock" aria-hidden="true"></i></div>
    <strong>Secure integrations</strong>
    <span>Use official Braintree API keys for authentication.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-pen-ruler" aria-hidden="true"></i></div>
    <strong>Customizable prompts</strong>
    <span>Offer in-context subscription options and promotions.</span>
  </div>
</div>

# Key details

## Required settings

Under **Settings > Connectors**, provide:

* **Merchant ID**
* **Public key**
* **Secret key**

## Supported actions

Use these connector actions within your prompts to manage subscriptions:

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Action</td><td>Description</td><td>User dependencies</td><td>Additional instructions</td></tr>
  <tr><td>Subscribe Plan</td><td>Subscribe the user to a specific plan</td><td><code>braintree_id</code> or <code>email_address</code></td><td>Select a plan from the dropdown</td></tr>
  <tr><td>Add Discount</td><td>Apply a discount to a user's subscription</td><td><code>braintree_id</code> or <code>email_address</code></td><td>Select a discount code from the dropdown</td></tr>
</table>

## Additional resources

Learn how to retrieve your Braintree credentials: <a href="https://developer.paypal.com/braintree/articles/control-panel/important-gateway-credentials" target="_blank">Braintree API keys</a>.
