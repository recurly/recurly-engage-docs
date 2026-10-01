---
title: Vindicia
excerpt: >-
  Guide to configuring the Vindicia connector in Recurly Engage—setup, data
  sync, and subscription actions.
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
  <div class="rp-overview">The Vindicia integration brings your Vindicia subscription and account data into Recurly Engage, and lets you update subscriptions directly from prompts.</div>
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
  <li>You must have a Vindicia account with REST API credentials.</li>
</ul>

# Definition

<div class="rp-definition">The Vindicia connector imports subscription and account traits from Vindicia and provides 1-Click actions (replace products, add campaigns, and add products) within your prompts.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-arrows-rotate" aria-hidden="true"></i></div>
    <strong>Direct subscription updates</strong>
    <span>Swap or add products in user subscriptions without backend calls.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-ticket" aria-hidden="true"></i></div>
    <strong>Promotional management</strong>
    <span>Attach campaigns, such as free trials and discounts, to active subscriptions.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-database" aria-hidden="true"></i></div>
    <strong>Automated data sync</strong>
    <span>Keep Recurly Engage updated with the latest billing and campaign data.</span>
  </div>
</div>

# Key details

## Required settings

Under **Settings > Connectors**, enter your Vindicia API credentials:

* **API Username**
* **API Password**

## Data integration

<ul class="rp-list">
  <li>Vindicia billing traits and account data are ingested automatically when you activate the connector.</li>
  <li>Products and campaigns synchronize periodically to stay current.</li>
  <li>User records in Recurly Engage must include <code>vindicia_subscription_id</code> or <code>vindicia_account_id</code> traits to enable action targeting.</li>
</ul>

## Supported actions

Use these actions within your prompt configurations to manage Vindicia subscriptions:

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Action</td><td>Description</td><td>User dependencies</td><td>Additional instructions</td></tr>
  <tr><td>Replace product</td><td>Replace a product in the user's subscription with another</td><td><code>vindicia_subscription_id</code> or <code>vindicia_account_id</code></td><td>Select the new Product(s) from the dropdown</td></tr>
  <tr><td>Add campaign</td><td>Attach a campaign (promo/trial) to the existing subscription</td><td><code>vindicia_subscription_id</code> or <code>vindicia_account_id</code></td><td>Select the Campaign from the dropdown</td></tr>
  <tr><td>Add product</td><td>Add an additional product to the user's subscription</td><td><code>vindicia_subscription_id</code> or <code>vindicia_account_id</code></td><td>Select the Product from the dropdown</td></tr>
</table>
