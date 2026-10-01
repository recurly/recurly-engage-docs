---
title: Recurly webhooks
excerpt: >-
  This document outlines the process for integrating your Recurly account with
  our system using webhooks to enable real-time updates for subscription events.
  The integration utilizes a dedicated ingestion endpoint secured via HTTP Basic
  Authentication.
deprecated: false
hidden: false
metadata:
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">Connect Recurly webhooks to Recurly Engage to keep your users' subscription data up to date in real time. This page covers the endpoint, the authentication credentials, the events to subscribe to, and how to track Recurly events as custom goals.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

# Definition

<div class="rp-definition">A Recurly webhook is an automatic HTTP POST notification that Recurly sends in real time to a specified URL, called the Ingestion Endpoint, when a subscription-related event occurs. Examples include a subscription being activated, updated, canceled, or expiring. The request payload is a JSON object with the details of the event, following the Recurly subscription notification format.</div>

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
</div>

# Key details

## Ingestion Endpoint

The designated Ingestion Endpoint for subscription change events is:

`https://conduit.redfast.com/ingest/APP_ID/update_user_subscription?source=recurly`

The `APP_ID` is a unique identifier (universally unique identifier, or UUID) for your application.

## Configure the webhook endpoint

These steps configure the webhook endpoint in your Recurly account.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Locate your authentication credentials</h4><p>You need two credentials for authentication, listed below.</p></div>
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
    <div><h4>Enable Recurly events as custom goals</h4><p>Engage supports using specific Recurly webhook events to increment custom goals for end users. A Recurly Subscription Management user can configure the webhook to fire on these events and track them as custom goal completions.</p></div>
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


<br />

<br />
