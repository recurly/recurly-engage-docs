---
title: Chargebee
excerpt: >-
  Configuration guide for the Chargebee connector in Recurly Engage, including
  activation, data sync, and 1-Click subscription actions.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

The Chargebee integration allows you to sync your subscription data and execute billing actions directly from prompts in Recurly Engage, leveraging your existing Chargebee account.  

# Definition

The Chargebee connector imports subscription traits nightly across three data sources — subscription info, payment/dunning status, and payment source details — and provides actions for managing subscriptions via prompts.

# Key benefits

* **Seamless billing workflows** — Manage subscriptions, trials, coupons, and payment recovery without leaving the prompt interface.
* **Comprehensive data sync** — Nightly imports pull subscription state, invoice/dunning status, and card expiration data to keep your segments and prompts accurate.
* **Flexible subscription actions** — Support for the full subscription lifecycle, from onboarding through cancellation and reactivation.

<br />

# Key steps

## Activation

1. Log in to your Chargebee account and generate an API key.
2. In Recurly Engage, navigate to **Settings > Integrations > Chargebee** and paste your API key.
3. Toggle Active to On.

## Subscription traits

| Trait Name                  | Description                                                             |
| :-------------------------- | :---------------------------------------------------------------------- |
| `state`                     | Current state of the subscription (pending, active, cancelled, expired) |
| `plan_code`                 | Plan the customer is subscribed to                                      |
| `currency`                  | Currency of the subscription                                            |
| `current_period_started_at` | Date/time when the current billing period started                       |
| `current_period_ends_at`    | Date/time when the current billing period ends                          |
| `trial_started_at`          | Date/time when the trial period began                                   |
| `trial_ends_at`             | Date/time when the trial period ends                                    |
| `activated_at`              | Date/time the subscription became active                                |
| `cancelled_at`              | Date/time the subscription was cancelled                                |
| `expires_at`                | Date/time when the subscription will churn                              |

## Dunning traits

| Trait Name | Description                                                          |
| :--------- | :------------------------------------------------------------------- |
| `status`   | Invoice status (pending, processing, past_due, paid, failed, voided) |

## Payment traits

| Trait Name          | Description                    |
| :------------------ | :----------------------------- |
| `card_expiry_month` | Month the payment card expires |
| `card_expiry_year`  | Year the payment card expires  |

## Supported actions

Once your connector is active and data is synced, you can attach these 1-Click actions to prompt interactions. The customer ID trait must be present on users.

| Action                    | Description                                                     |
| :------------------------ | :-------------------------------------------------------------- |
| Switch Subscription       | Changes a user's subscription to a new plan                     |
| Create Subscription       | Creates a subscription for an existing customer account         |
| Reactivate Subscription   | Reactivates a user's cancelled or expired subscription          |
| Cancel Subscription       | Cancels a user's subscription at period end or immediately      |
| Terminate Subscription    | Immediately deletes a subscription record                       |
| Update Auto Collection    | Toggles automatic card charging on or off                       |
| Pause Subscription        | Temporarily halts billing for a user                            |
| Resume Subscription       | Restarts billing for a paused user                              |
| Convert Trial             | Converts a trial to a paid subscription immediately             |
| Extend Trial Period       | Pushes the trial end date to a future date                      |
| Apply Coupon Code         | Applies a coupon or discount to a user's subscription           |
| Update Subscription Price | Manually overrides the price on a per-subscription basis        |
| Record Usage              | Logs a usage record for a subscription add-on (metered billing) |

<br />
