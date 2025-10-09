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

`https://conduit.redfast.com/ingest/${APP_ID}/update_user_subscription?source=recurly&action=update_traits`

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

<Image align="center" border={false} src="https://files.readme.io/0d5580995d67cf630f9151f8ad0acb1e69bd4fb1fe9a7b3062c2f93e5772182f-webhooks1.png" />

## Step 2: Configure the Recurly webhooks endpoint

**Navigate** to the Webhook Endpoint configuration screen within your Recurly application's settings and **perform** the following actions:

1. **Enter** the Ingestion Endpoint URL: Input the complete URL, replacing APP_ID with your specific application UUID: `https://conduit.redfast.com/ingest/$\{APP_ID}/update_user_subscription?source=recurly&action=update_traits}`.
2. **Configure** Authentication: **Enable** HTTP Basic Authentication for the endpoint.
   1. **Enter** your **Application ID** as the Username.
   2. **Enter** your **Application API Key** as the Password.
3. **Subscribe** to Events: **Select** the specific subscription-related events you wish to track in real-time. For a comprehensive update, it is recommended to subscribe to all relevant subscription change events, such as:
   1. `subscription.created`
   2. `subscription.updated`
   3. `subscription.cancelled`
   4. `subscription.renewed`
   5. `subscription.paused`
   6. `subscription.resumed`