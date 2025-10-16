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
# Overview

A Recurly Webhook is an automatic HTTP POST notification sent by Recurly to a specified URL (Ingestion Endpoint) in real-time when a subscription-related event occurs (e.g., a subscription is activated, updated, canceled, or expires). The payload of this request is a JSON object containing the details of the event, adhering to the Recurly subscription notification format.

The designated Ingestion Endpoint for subscription change events is:

`https://conduit.redfast.com/ingest/${APP_ID}/update_user_subscription?source=recurly`

The `APP_ID` is a unique identifier (UUID) for your application.

# Key benefits

Integrating with Recurly Webhooks offers several advantages for maintaining accurate, up-to-date user subscription data:

1. **Real-time data sync:** Provides immediate notification of subscription status changes, ensuring that your system's user traits are updated promptly.
2. **Enhanced user experience:** Enables timely actions based on subscription events, such as adjusting service access, triggering tailored communication, or managing lifecycle campaigns.
3. **Data consistency:** Helps maintain synchronization between your Recurly billing data and your internal user management system.

# Key steps

The following steps detail the process for configuring the webhook endpoint within your Recurly account.

## Step 1: Locate authentication credentials

You will need the following credentials for authentication:

* **Username:** Your Application ID (APP_ID), which is the UUID found in the Ingestion Endpoint URL.
* **Password:** Your Application API Key, accessible in the Pulse system under Settings → Application.

<Image align="center" border={false} src="https://files.readme.io/a706f0863987825de8a1601eaceaf60f424d87555296f3ee3690a918d9ccc086-Screenshot_2025-10-03_at_11.21.59_AM.png" />

## Step 2: Configure the Recurly webhooks endpoint

**Navigate** to the Webhook Endpoint configuration screen within your Recurly application's settings and **perform** the following actions:

1. **Enter** the Ingestion Endpoint URL: Input the complete URL, replacing APP_ID with your specific application UUID: `https://conduit.redfast.com/ingest/$\{APP_ID}/update_user_subscription?source=recurly`.
2. **Configure** Authentication: **Enable** HTTP Basic Authentication for the endpoint.
   1. **Enter** your **Application ID** as the Username.
   2. **Enter** your **Application API Key** as the Password.
3. **Subscribe** to Events: **Select** the specific subscription-related events you wish to track in real-time. For a comprehensive update, it is recommended to subscribe to all relevant subscription change events, such as:
   1. `subscription.created`
   2. `subscription.updated`
   3. `subscription.canceled`
   4. `subscription.renewed`
   5. `subscription.paused`
   6. `subscription.resumed`

## Step 3: Enabling Recurly events as custom goals

Engage supports the use of specific Recurly Webhook events to increment Custom Goals for end users. A Recurly Subscription Management user can configure the webhook to fire on these events and track them as custom goal completions.

Engage is configured to automatically support the following two Recurly webhook events as Custom Goals:

* `subscription.canceled`
* `billing_info.updated`

To enable tracking for these custom goals: Ensure that you have subscribed to the relevant events (`subscription.canceled` and `billing_info.updated`) in the Recurly Webhook Endpoint configuration (Step 2.3).

### Advanced usage and custom goals

If you wish to implement additional Recurly events as custom goals beyond the default two, you will need to create useage trackers within Engage with the proper label attributes. These labels must match the Recurly webhook payload using the convention `object_type.event_type`. Learn more about <a href="https://docs.recurly.com/recurly-engage/docs/usage-tracking-1#/">usage tracking</a>.

1. Navigate to Settings > Usage Tracking > **+Add New Tracker**
2. Create a new Custom Tracker by adding the name, label (be sure to match the Recurly Webhook Payload), and description of the tracker. Ensure the tracker type is set to "Custom" 

<Image align="center" border={false} src="https://files.readme.io/c0a9d08cc7a0f407ce69c81b6426b05956a2fd8d6485bc1398aab980c28564c6-Screenshot_2025-10-16_at_9.45.37_AM.png" />
