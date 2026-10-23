---
title: Recurly webhooks
excerpt: >-
  This document outlines the process for integrating your Recurly account with
  our system using webhooks to enable real-time updates for subscription
  events. Recurly Engage supports JSON webhooks and legacy XML webhooks, each
  with a dedicated ingestion endpoint secured via HTTP Basic Authentication.
deprecated: false
hidden: false
metadata:
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">Connect Recurly webhooks to Recurly Engage to keep your users' subscription data up to date in real time. This page covers the JSON webhook endpoint, the authentication credentials, the events to subscribe to, how to track Recurly events as custom goals, multi-subscription data, and the XML webhook endpoint.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

# Definition

<div class="rp-definition">A Recurly webhook is an automatic HTTP POST notification that Recurly sends in real time to a specified URL, called the Ingestion Endpoint, when a subscription-related event occurs. Examples include a subscription being activated, updated, canceled, or expiring.</div>

Recurly Engage supports the two notification formats Recurly can deliver, each with a dedicated ingestion endpoint:

1. **JSON webhooks** (recommended) — Recurly's modern webhook endpoint configuration, which delivers events as JSON. Engage enriches each event by querying the Recurly API to sync a full set of subscription, invoice, and billing traits for the user. JSON webhooks also power custom goal tracking and multi-subscription data.
2. **XML webhooks** (legacy format) — a legacy Recurly endpoint configuration that delivers events as XML. Engage saves only the fields present in the XML payload. This endpoint is used to sync payment failure details, such as `failure_type`, that are not available through the JSON webhook flow.

Both endpoints use the same authentication credentials and can be configured together. The designated Ingestion Endpoints are:

**JSON webhooks:**

`https://conduit.redfast.com/ingest/APP_ID/update_user_subscription?source=recurly`

**XML webhooks:**

`https://conduit.redfast.com/ingest/APP_ID/update_user_subscription_xml?source=recurly`

The `APP_ID` is a unique identifier (universally unique identifier, or UUID) for your application.

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-bolt" aria-hidden="true"></i></div>
    <strong>Real-time data sync</strong>
    <span>Get immediate notification of subscription status changes, so your system's user traits are updated promptly.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-user-check" aria-hidden="true"></i></div>
    <strong>Enhanced user experience</strong>
    <span>Take timely action based on subscription events, such as adjusting service access, triggering tailored communication, or managing lifecycle campaigns.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-rotate" aria-hidden="true"></i></div>
    <strong>Data consistency</strong>
    <span>Keep your Recurly billing data and your internal user management system synchronized.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-layer-group" aria-hidden="true"></i></div>
    <strong>Multi-subscription targeting</strong>
    <span>Sync every subscription a user holds — not just the most recent one — and target based on any of them.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-magnifying-glass" aria-hidden="true"></i></div>
    <strong>Payment failure insights</strong>
    <span>Capture why a payment failed, such as a gateway decline, to power winback and involuntary churn messaging.</span>
  </div>
</div>

# Key details

## Ingestion Endpoint

The designated Ingestion Endpoint for subscription change events is:

`https://conduit.redfast.com/ingest/APP_ID/update_user_subscription?source=recurly`

The `APP_ID` is a unique identifier (universally unique identifier, or UUID) for your application.

## Configure the JSON webhook endpoint

These steps configure the JSON webhook endpoint in your Recurly account.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Locate your authentication credentials</h4><p>You need two credentials for authentication, listed below. Both endpoints use the same credentials.</p></div>
  </div>
</div>

* **Username**: Your Application ID (`APP_ID`), which is the UUID in the Ingestion Endpoint URL.
* **Password**: Your Application API key, available in Pulse under Settings → Application.


<Image src="https://files.readme.io/a706f0863987825de8a1601eaceaf60f424d87555296f3ee3690a918d9ccc086-Screenshot_2025-10-03_at_11.21.59_AM.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Configure the Recurly webhooks endpoint</h4><p>Make sure the endpoint's payload format is set to <span style={{fontWeight: "bold"}}>JSON</span>. Then open the Webhook Endpoint configuration screen in your Recurly application's settings and complete the actions below.</p></div>
  </div>
</div>

1. **Enter the Ingestion Endpoint URL**: Input the complete URL, replacing `APP_ID` with your application UUID: `https://conduit.redfast.com/ingest/APP_ID/update_user_subscription?source=recurly`.
2. **Configure authentication**: Enable HTTP Basic Authentication for the endpoint.
   1. Enter your **Application ID** as the Username.
   2. Enter your **Application API Key** as the Password.
3. **Subscribe to events**: Select the subscription-related events you want to track in real time. For a comprehensive update, we recommend subscribing to all relevant subscription change events, such as:
   1. `subscription.created`
   2. `subscription.updated`
   3. `subscription.canceled`
   4. `subscription.renewed`
   5. `subscription.paused`
   6. `subscription.resumed`
   7. `subscription.expired`
   8. `charge_invoice.paid`
   9. `charge_invoice.past_due`

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Enable Recurly events as custom goals</h4><p>Engage supports using specific Recurly webhook events to increment custom goals for end users. A Recurly Subscription Management user can configure the webhook to fire on these events and track them as custom goal completions. Custom goal tracking is only available through the JSON webhook endpoint.</p></div>
  </div>
</div>

Engage automatically supports the following two Recurly webhook events as custom goals:

* `subscription.canceled`
* `billing_info.updated`

To enable tracking for these custom goals, make sure you've subscribed to the relevant events (`subscription.canceled` and `billing_info.updated`) in the Recurly webhook endpoint configuration (Step 2, item 3).

## Advanced usage and custom goals

To implement additional Recurly events as custom goals beyond the default two, create usage trackers in Engage with the proper label attributes. These labels must match the Recurly webhook payload, using the convention `object_type.event_type`. Learn more about <a href="https://docs.recurly.com/recurly-engage/docs/usage-tracking-1#/" target="_blank">usage tracking</a>.

1. Navigate to **Settings > Usage Tracking > +Add New Tracker**.
2. Create a new custom tracker by adding the name, label (be sure to match the Recurly webhook payload), and description of the tracker. Make sure the tracker type is set to "Custom".


<Image src="https://files.readme.io/c0a9d08cc7a0f407ce69c81b6426b05956a2fd8d6485bc1398aab980c28564c6-Screenshot_2025-10-16_at_9.45.37_AM.png" align="center" width="75%" border={true} />

## Multi-subscription webhook data

If your users can hold multiple subscriptions — for example, a bundle plus an add-on product — you can sync **all** of a user's subscriptions to Engage, not just the most recent one, and target based on any of them.

To enable:

1. In Recurly Engage, navigate to **Settings > Integrations > Recurly**.
2. Toggle **Multi Subscription Webhooks** to **On**.

Once enabled, every qualifying Recurly webhook event (subscription, account, or invoice events) triggers Engage to fetch all of the user's subscriptions from Recurly and write them to the user's profile as a `subscriptions` trait. This trait is a complex collection — an array of subscription records, each with the following sub-attributes:

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Sub-attribute</td><td>Description</td></tr>
  <tr><td>plan_code</td><td>Plan code of the subscription</td></tr>
  <tr><td>plan_name</td><td>Plan name of the subscription</td></tr>
  <tr><td>state</td><td>Subscription state (pending, active, canceled, expired)</td></tr>
  <tr><td>currency</td><td>Currency of the subscription</td></tr>
  <tr><td>current_period_started_at</td><td>Date/time when the current billing period starts</td></tr>
  <tr><td>current_period_ends_at</td><td>Date/time when the current billing period ends</td></tr>
  <tr><td>activated_at</td><td>Date/time the subscription became active</td></tr>
  <tr><td>auto_renew</td><td>Whether the subscription auto-renews</td></tr>
  <tr><td>canceled_at</td><td>Date/time the subscription was canceled</td></tr>
  <tr><td>converted_at</td><td>Date/time a trial was converted to a paid subscription</td></tr>
  <tr><td>created_at</td><td>Date/time the subscription was created</td></tr>
  <tr><td>expiration_reason</td><td>Reason the subscription reached its final state</td></tr>
  <tr><td>expires_at</td><td>Date/time when the subscription will churn</td></tr>
  <tr><td>paused_at</td><td>Date/time the subscription was paused</td></tr>
</table>

Notes:

* Engage syncs up to 50 subscription records per user per webhook event.
* The `subscriptions` trait is refreshed on every qualifying webhook event, so the full set stays current as subscriptions are added, changed, or canceled.
* To filter segments on this trait, see <a href="https://docs.recurly.com/recurly-engage/docs/complex-collections" target="_blank">Complex collections</a> — including how filters on different sub-attributes are evaluated across all of a user's subscription records.

## XML webhooks

XML webhooks use a separate endpoint configuration in Recurly from the JSON webhook above. Configure it only if you want to sync data that is available exclusively in the XML payload (currently: payment failure reasons).

<div class="rp-callout rp-callout-important">
  <div><strong><i class="fa-solid fa-circle-exclamation" aria-hidden="true"></i> Limited availability</strong>XML webhook ingestion must be enabled for your application by Recurly Engage. Contact your CSM or Recurly Engage support to enable it.</div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>The Recurly integration is enabled for your application, with the integration <strong>Active</strong> in Settings &rarr; Integrations &rarr; Recurly.</li>
  <li><strong>Use Account Code</strong> is enabled in your Recurly connector settings. Engage identifies users on this endpoint by their Recurly <code>account_code</code>, so your Engage user IDs must match your Recurly account codes.</li>
</ul>

### Configure XML webhooks in Recurly

1. In your Recurly dashboard, go to **Integrations → Webhooks**.
2. **Enter the Ingestion Endpoint URL**, replacing `APP_ID` with your application UUID: `https://conduit.redfast.com/ingest/APP_ID/update_user_subscription_xml?source=recurly`.
3. **Set the Format** to **XML**.
4. **Enable HTTP Basic Authentication** and enter the credentials from Step 1 (Application ID as Username, Application API Key as Password).
5. **Subscribe to notification types**: Select the notification types you want delivered. Currently, `failed_payment_notification` is the type Engage processes.

### Supported notification types

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Notification type</td><td>Data synced</td><td>Description</td></tr>
  <tr><td>failed_payment_notification</td><td>failure_type</td><td>The reason a payment failed, e.g. "Declined by the gateway"</td></tr>
</table>

The `failure_type` trait enables targeting based on why a payment failed — for example, a winback prompt for users whose payment was declined by the gateway, handled separately from other churn reasons.

Other notification types are delivered to the endpoint and acknowledged without processing.

### User identification

Engage identifies users by the `account_code` field in the XML payload's `<account>` block, which maps to the visitor's `user_id` in Recurly Engage. Ensure your Recurly account codes match the user IDs in your Engage application.

### Example payload

For reference, Recurly will POST a body like this to the endpoint:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<failed_payment_notification>
  <account>
    <account_code>user_123</account_code>
    <email>user@example.com</email>
  </account>
  <transaction>
    <id>a5143c1d3a6f4a8287d0e2cc1d4c0427</id>
    <failure_type>Declined by the gateway</failure_type>
    <status>Declined</status>
    <amount_in_cents type="integer">1000</amount_in_cents>
  </transaction>
</failed_payment_notification>
```

### Response codes

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Status</td><td>Meaning</td></tr>
  <tr><td>200 OK</td><td>Notification processed successfully</td></tr>
  <tr><td>401 Unauthorized</td><td>Invalid credentials</td></tr>
  <tr><td>422 Unprocessable Entity</td><td>Unknown source, app not found, disabled app, malformed XML, or processing error</td></tr>
  <tr><td>500 Internal Server Error</td><td>Unexpected error</td></tr>
</table>

### XML webhook limitations

Compared to the JSON webhook endpoint, XML webhooks:

* **Save only the fields present in the XML payload.** Engage does not query the Recurly API to enrich the user profile from this endpoint.
* **Do not support custom goal tracking.** Events received on this endpoint cannot increment custom goals, because goal labels follow a different naming convention than XML notification types.
* **Do not replace the JSON webhook.** To take full advantage of webhook features (rich trait sync via the Recurly API, custom goal increments), keep the JSON webhook endpoint configured. Both endpoints can be configured at the same time, and Recurly can deliver both formats for the same event.

### Related: transaction details via the transactions export

Two additional transaction fields are available outside webhooks:

* `failure_type` is also available in the <a href="https://docs.recurly.com/recurly-subscriptions/docs/transaction-export" target="_blank">Recurly transactions export</a>, which Engage can ingest on a daily schedule (contact your CSM to enable transaction export ingestion).
* `processor_response_text` is **not available in webhooks** — it is only available via the transactions export (export version 9 or later) or in Recurly's internal logs.

<br />

<br />