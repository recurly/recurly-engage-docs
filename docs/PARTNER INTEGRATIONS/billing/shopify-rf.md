---
title: Shopify
excerpt: >-
  Configuration guide for the Shopify connector in Recurly Engage—setup,
  supported actions, and usage steps.
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
  <div class="rp-overview">The Shopify integration lets Recurly Engage web prompts add items to a cart, redirect users to Shopify pages, and apply discount codes on your Shopify storefront.</div>
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
  <li>Your site must be hosted on Shopify with the storefront API enabled.</li>
</ul>

# Definition

<div class="rp-definition">The Shopify connector enables web prompts to interact with your Shopify storefront, including adding items to carts, redirecting to product or checkout pages, and applying discount codes.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-cart-shopping" aria-hidden="true"></i></div>
    <strong>Streamlined purchase flows</strong>
    <span>Let users add products or apply discounts without leaving your prompt.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-arrow-trend-up" aria-hidden="true"></i></div>
    <strong>Increased conversions</strong>
    <span>Reduce friction by embedding cart actions directly in your engagement messages.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-route" aria-hidden="true"></i></div>
    <strong>Flexible redirects</strong>
    <span>Guide users to specific Shopify pages (collections, products, or checkout) with a single click.</span>
  </div>
</div>

# Key details

## Required settings

Under **Settings > Connectors > Shopify**, provide:

* **Shop URL**: Your Shopify store domain (for example, `your-store.myshopify.com`).

## Supported actions

Use the following actions within web prompts to drive ecommerce interactions:

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Action</td><td>Description</td><td>User dependencies</td><td>Additional instructions</td></tr>
  <tr><td>Add to cart</td><td>Add one or more items to the existing cart</td><td>None</td><td>Specify SKU(s) and quantity</td></tr>
  <tr><td>Redirect</td><td>Navigate the user to a Shopify URL</td><td>None</td><td>Enter the target URL (product, checkout, etc.)</td></tr>
  <tr><td>Add Discount</td><td>Apply a discount code to the existing cart</td><td>None</td><td>Provide the discount code</td></tr>
</table>

## Configure a Shopify action

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open website actions</h4><p>In Recurly Engage, go to <span style={{fontWeight: "bold"}}>Settings → Actions → Website Actions</span>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Add an action</h4><p>Scroll to the <span style={{fontWeight: "bold"}}>Shopify</span> section and select <span style={{fontWeight: "bold"}}>Add Action</span>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Select the action type</h4><p>Select your desired action type (for example, <span style={{fontWeight: "bold"}}>Add to cart</span>).</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Configure the action details</h4><p>Configure the details for the action type you selected.</p></div>
  </div>
</div>

<ul class="rp-list">
  <li><strong>Add to cart</strong>: Enter SKU(s) and quantity for each item.</li>
  <li><strong>Redirect</strong>: Provide the Shopify URL to navigate users to.</li>
  <li><strong>Add Discount</strong>: Input the discount code to apply.</li>
</ul>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Save the action</h4><p>Save the action.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">6</div>
    <div><h4>Attach it to a prompt</h4><p>Attach this action to any <span style={{fontWeight: "bold"}}>Web</span> prompt under the <span style={{fontWeight: "bold"}}>Actions</span> panel.</p></div>
  </div>
</div>

Once the prompt is published, users who interact with it can add items to their cart, get redirected to a Shopify page, or apply a discount code, all directly from your engagement messages.
