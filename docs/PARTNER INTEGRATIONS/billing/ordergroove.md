---
title: Ordergroove
excerpt: >-
  Seamlessly integrate Recurly Engage with Ordergroove to unify subscriber data,
  enable proactive, targeted engagement, and offer customers 1-click
  subscription management.
deprecated: false
hidden: false
metadata:
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">The Recurly Engage integration with Ordergroove lets merchants use their subscription data for advanced customer engagement and automated, one-click subscription management. It syncs subscription and order information from Ordergroove into Recurly Engage, and it lets Recurly Engage trigger key subscription actions back in Ordergroove.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

# Definition

<div class="rp-definition">The Ordergroove integration gives you a unified view of the subscriber lifecycle. It syncs subscription and order data (traits) from Ordergroove into Recurly Engage, and it runs 1-Click subscription actions from Recurly Engage that update the customer's subscription in Ordergroove.</div>

The integration is built around two core capabilities:

1. **Data ingestion**: Sync comprehensive user subscription and order data (traits) from Ordergroove into Recurly Engage. Webhooks provide real-time ingestion for events like day 1 cancellations and other critical subscription or order changes.
2. **1-Click actions**: Run top-supported subscription actions from Recurly Engage that directly update the customer's subscription in Ordergroove.

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-database" aria-hidden="true"></i></div>
    <strong>Unified subscriber data</strong>
    <span>Automatically sync subscription information such as status, frequency, product, and next order date from Ordergroove to Recurly Engage, creating a single source of truth for subscriber data.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-bell" aria-hidden="true"></i></div>
    <strong>Proactive engagement</strong>
    <span>Use Ordergroove webhooks to track critical subscription and order changes (for example, billing or subscription changes) in Recurly Engage right away, so you can send targeted communication that prevents churn or encourages re-engagement.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-hand-pointer" aria-hidden="true"></i></div>
    <strong>1-Click management</strong>
    <span>Let customers manage, delay, or skip their Ordergroove subscriptions with 1-Click actions directly from Recurly Engage prompts.</span>
  </div>
</div>

# Key details

The integration involves configuring data ingestion and setting up 1-Click actions in both Recurly Engage and Ordergroove.

## Sync traits with subscription reports

To give Recurly Engage the most up-to-date subscriber information, configure Automating Subscription Reports in Ordergroove. This method syncs core subscription traits.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Ensure access to automated reports</h4><p>Make sure you have access to automated reports in Ordergroove.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Specify fields</h4><p>Make sure the report includes the key fields (traits) Recurly Engage needs, such as:</p></div>
  </div>
</div>

<ul class="rp-list">
  <li><code>Ordergroove User ID</code></li>
  <li><code>Merchant User ID</code></li>
  <li><code>Subscription ID</code></li>
  <li><code>Status (Active, Canceled, etc.)</code></li>
  <li><code>Frequency</code></li>
  <li><code>Quantity</code></li>
  <li><code>SKU</code></li>
  <li><code>Price</code></li>
  <li><code>Cancel Date</code></li>
  <li><code>Next Order Date</code></li>
</ul>

For a full list of available fields, see <a href="https://help.ordergroove.com/hc/en-us/articles/360050746374-Automating-Subscription-Reports" target="_blank">Ordergroove's Automating Subscription Reports</a> documentation.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Configure delivery</h4><p>Upload your file in the Recurly Engage management console.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Review the trait mapping</h4><p>Recurly Engage maps the delivered data fields (for example, <code>Subscription ID</code> and <code>Next Order Date</code>) to the corresponding subscriber traits in the Engage platform.</p></div>
  </div>
</div>

## Sync events with webhooks

To track critical events like churn, cancellations, and order issues in real time, configure <a href="https://developer.ordergroove.com/reference/webhooks-overview" target="_blank">Ordergroove Webhooks</a> to notify Recurly Engage of changes.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Configure the endpoint</h4><p>Enter the endpoint URL provided by Recurly Engage for receiving Ordergroove webhooks.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Select events</h4><p>Select the events you want to receive notifications for. The most critical events for Recurly Engage are:</p></div>
  </div>
</div>

<ul class="rp-list">
  <li>Subscription changes</li>
  <li>Subscriber changes</li>
  <li>Order changes (especially <code>order.reject</code>)</li>
</ul>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Authenticate the webhook</h4><p>Use the Verification Key provided in the Ordergroove Admin to secure the webhook. Recurly Engage uses this key to verify that requests are genuinely issued by Ordergroove.</p></div>
  </div>
</div>

## Configure 1-Click actions

Recurly Engage uses the Ordergroove 1-Click APIs to enable real-time subscription management. The following 1-Click actions are supported and can be triggered from Recurly Engage:

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>1-Click action</td><td>Ordergroove API action</td><td>Description</td></tr>
  <tr><td>Cancel subscription</td><td><a href="https://developer.ordergroove.com/reference/subscriptions-cancel" target="_blank">Cancel subscription</a></td><td>Terminates an active subscription.</td></tr>
  <tr><td>Change quantity</td><td><a href="https://developer.ordergroove.com/reference/subscriptions-change-quantity" target="_blank">Change quantity</a></td><td>Increases or decreases the number of units in a subscription.</td></tr>
  <tr><td>Change frequency</td><td><a href="https://developer.ordergroove.com/reference/subscriptions-change-frequency" target="_blank">Change frequency</a></td><td>Modifies the order placement frequency (for example, from 30 to 60 days).</td></tr>
  <tr><td>Reactivate</td><td><a href="https://developer.ordergroove.com/reference/subscriptions-reactivate" target="_blank">Reactivate</a></td><td>Turns on an existing, inactive subscription.</td></tr>
  <tr><td>Change product</td><td><a href="https://developer.ordergroove.com/reference/subscriptions-change-product" target="_blank">Change product</a></td><td>Swaps the current product for a different one.</td></tr>
  <tr><td>Delay next order date</td><td><a href="https://developer.ordergroove.com/reference/change-next-order-date" target="_blank">Change next order date</a></td><td>Pushes the next scheduled order date further out.</td></tr>
  <tr><td>Accelerate next order date</td><td><a href="https://developer.ordergroove.com/reference/change-next-order-date" target="_blank">Change next order date</a></td><td>Moves the next scheduled order date closer.</td></tr>
  <tr><td>Skip order</td><td><a href="https://developer.ordergroove.com/reference/skip-subscription" target="_blank">Skip subscription</a></td><td>Skips the next recurring order placement.</td></tr>
  <tr><td>Enable auto renew</td><td><a href="https://developer.ordergroove.com/reference/subscriptions-change-payment" target="_blank">Change prepaid renewal behavior</a></td><td>Changes the prepaid subscription renewal setting.</td></tr>
  <tr><td>Apply coupon (offer)</td><td><a href="https://developer.ordergroove.com/reference/subscriptions-update" target="_blank">Subscriptions update</a></td><td>Applies discounts to the subscription.</td></tr>
</table>

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Configuration</strong>Recurly Engage requires your Ordergroove <span style={{fontWeight: "bold"}}>API credentials</span> to authenticate and run these 1-Click actions against your subscriber data. Consult your Recurly Engage implementation team for the secure exchange and configuration of these credentials.</div>
</div>
