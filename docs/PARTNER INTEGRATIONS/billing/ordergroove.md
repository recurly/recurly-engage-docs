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
# Overview

The Recurly Engage integration with Ordergroove empowers Merchants to use their subscription data for advanced customer engagement and automated one-click subscription management.  

This combination allows for a unified view of the subscriber lifecycle by syncing essential subscription and order information from Ordergroove into Recurly Engage.  

Furthermore, it enables Recurly Engage to trigger key subscription actions back into Ordergroove, providing a proactive and streamlined experience for both Merchants and their Subscribers.

The integration is built around two core capabilities:

1. **Data Ingestion:** Syncing comprehensive user subscription and order data (traits) from Ordergroove into Recurly Engage. This includes using webhooks for real-time data ingestion for events like day 1 cancellations and other critical subscription or order changes.
2. **1-Click Actions:** Enabling top-supported subscription actions to be executed from Recurly Engage, directly updating the customer's subscription in Ordergroove.

<br />

# Key benefits

Integrating Recurly Engage and Ordergroove provides significant advantages for managing and growing your subscription business:

* **Unified subscriber data:** Automatically sync subscription information like status, frequency, product, and next order date from Ordergroove to Recurly Engage, creating a single source of truth for all subscriber data.
* **Proactive engagement:** Utilize Ordergroove Webhooks to instantly track critical subscription and order changes (e.g., billing or subscription changes) in Recurly Engage, allowing for immediate, targeted communication to prevent churn or encourage re-engagement.
* **Seamless 1-Click Management:** Empower customers with 1-click actions directly from Recurly Engage prompts, enabling them to manage, delay, or skip their Ordergroove subscriptions with a seamless experience.

<br />

# Key steps

The integration primarily involves configuring data ingestion and setting up the 1-Click Actions within Recurly Engage and Ordergroove.

## Step 1: Data Ingestion Subscription reporting (traits sync)

To ensure Recurly Engage has the most up-to-date subscriber information, you'll need to configure Automating Subscription Reports from Ordergroove. This method is used to sync core subscription traits.

1. **Ensure access to automated reports**
2. **Specify fields:** Ensure the report includes the key fields (traits) necessary for Recurly Engage, such as:
   `Ordergroove User ID`
   `Merchant User ID`
   `Subscription ID`
   `Status (Active, Canceled, etc.)`
   `Frequency`
   `Quantity`
   `SKU`
   `Price`
   `Cancel Date`
   `Next Order Date`  
   <br />
   For a full list of available fields please refer to <a href="https://help.ordergroove.com/hc/en-us/articles/360050746374-Automating-Subscription-Reports">Ordergrooves Automating Subscription Reports</a> documentation.
3. **Configure delivery:** Recurly Engage provides a seamless way to upload your file within the management console.
4. **Recurly Engage configuration:** Recurly Engage will map the delivered data fields (e.g., `Subscription ID`, `Next Order Date`) to the corresponding subscriber traits within the Engage platform.

## Step 2: Event sync - Webhooks configuration

To enable real-time tracking of critical events like churn, cancellations, and order issues, you must configure <a href="https://developer.ordergroove.com/reference/webhooks-overview">Ordergroove Webhooks</a> to notify Recurly Engage of changes.

1. **Configure Endpoint:** Enter the specific endpoint URL provided by Recurly Engage for receiving Ordergroove webhooks.
2. **Select Events:** Select the events for which you want to receive notifications. The most critical events for Recurly Engage are:
   * Subscription changes
   * Subscriber changes
   * Order changes (especially `order.reject`)
3. **Authentication:** Utilize the Verification Key provided in the Ordergroove Admin to secure the webhook. This key is used by Recurly Engage to verify that the requests are genuinely issued by Ordergroove.

## Step 3: 1-Click actions configuration (API integration)

Recurly Engage uses the Ordergroove 1-Click APIs to enable real-time subscription management.  

The following **1-Click Actions** are supported by the integration and can be triggered via Recurly Engage:

<br />

| 1-Click Action             | Ordergroove API Action                                                                                      | Description                                                        |
| -------------------------- | ----------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| Cancel subscription        | [Cancel subscription](https://developer.ordergroove.com/reference/subscriptions-cancel)                     | Terminates an active subscription.                                 |
| Change quantity            | [Change quantity](https://developer.ordergroove.com/reference/subscriptions-change-quantity)                | Increases or decreases the number of units in a subscription.      |
| Change frequency           | [Change frequency](https://developer.ordergroove.com/reference/subscriptions-change-frequency)              | Modifies the order placement frequency (e.g., from 30 to 60 days). |
| Reactivate                 | [Reactivate](https://developer.ordergroove.com/reference/subscriptions-reactivate)                          | Turns on an existing, inactive subscription.                       |
| Change product             | [Change product](https://developer.ordergroove.com/reference/subscriptions-change-product)                  | Swaps the current product for a different one.                     |
| Delay next order date      | [Change next order date](https://developer.ordergroove.com/reference/change-next-order-date)                | Pushes the next scheduled order date further out.                  |
| Accelerate next order date | [Change next order date](https://developer.ordergroove.com/reference/change-next-order-date)                | Moves the next scheduled order date closer.                        |
| Skip order                 | [Skip subscription](https://developer.ordergroove.com/reference/skip-subscription)                          | Skips the next recurring order placement.                          |
| Enable auto renew          | [Change prepaid renewal behavior](https://developer.ordergroove.com/reference/subscriptions-change-payment) | Changes the prepaid subscription renewal setting.                  |
| Apply coupon (offer)       | [Subscriptions update](https://developer.ordergroove.com/reference/subscriptions-update)                    | Apply any discounts to the subscription.                           |

<br />

**Configuration:** Recurly Engage will require your Ordergroove **API credentials** to authenticate and execute these 1-Click Actions against your subscriber data. Consult your Recurly Engage implementation team for the secure exchange and configuration of these credentials.
