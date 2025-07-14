---
title: Evergent
excerpt: >-
  Configuration guide for the Evergent connector in Recurly Engage—activation,
  data sync, and supported subscription actions.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

The **Evergent** integration lets you synchronize subscriber data and trigger subscription management actions from within Recurly Engage prompts by connecting to your Evergent REST API.

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

### Prerequisites & limitations

* Company or App Administrator permissions in Recurly Engage.
* Uses the Evergent REST API; legacy SOAP-only setups may require Customer Success assistance.

# Definition

Evergent Connector for Recurly Engage synchronizes subscriber traits from Evergent and enables prompt-driven subscription workflows (coupon redemption, service changes, pauses, resumes, etc.).

# Key benefits

* **Real-time subscriber data**: Import detailed subscription traits for precise segment targeting.
* **Seamless subscription control**: Execute subscription actions (pause, resume, change service) directly from prompts.
* **Customizable workflows**: Tailor actions to your Evergent instance and business logic.

# Key details

## Activation

To enable the Evergent connector under **Settings > Connectors**, provide:

* **Domain**: Your Evergent API domain.
* **apiKey**: Your Evergent REST API key.
* **channelPartnerID**: Your channel partner identifier.

## Data integration

Schedule a daily CSV export from Evergent into Recurly Engage via S3. The CSV should include the following subscriber traits for audience targeting:

| Trait Name                    | Description                                                                 |
| ----------------------------- | --------------------------------------------------------------------------- |
| `customer_id`                 | Customer/User ID                                                            |
| `business_unit`               | Business unit owning subscription                                           |
| `country`                     | Billing country                                                             |
| `current_payment_method`      | \[Google Wallet, App Store Billing, Credit Card, Roku Payment, Coupon, etc] |
| `pack_id`                     | Package ID                                                                  |
| `package`                     | Package Name                                                                |
| `pack_price`                  | Package Price                                                               |
| `pack_type`                   | Package Type                                                                |
| `currency_code`               | 3-character currency code                                                   |
| `valid_from_date`             | Billing period start                                                        |
| `valid_to_date`               | Billing period end                                                          |
| `payment_status`              | \[Declined, Posted]                                                         |
| `payment_type`                | \[Renewal, Purchase]                                                        |
| `payment_date`                | Date of most recent payment                                                 |
| `declined_reason`             | Reason for payment decline                                                  |
| `promotion_amount`            | Promotion amount (if applicable)                                            |
| `promotion_code`              | Promotion code (if applicable)                                              |
| `coupon_code`                 | Coupon code (if applicable)                                                 |
| `cancellation_requested_date` | Date of cancellation request (if applicable)                                |
| `classification`              | Subscription classification status (\[Paid, Free Trial, Retail, etc])       |

## Supported actions

> 📘 Important:
>
> Evergent configurations can vary; verify which APIs your instance supports.

| Action                  | Description                                                                  | API Method               |
| ----------------------- | ---------------------------------------------------------------------------- | ------------------------ |
| Redeem Coupon           | Apply a coupon code to an existing package/product                           | `redeemCoupon`           |
| Change Service          | Upgrade or downgrade an existing service (specify from and to services)      | `changeService`          |
| Pause Subscription      | Pause an active subscription for up to 90 days                               | `pauseSubscription`      |
| Resume Subscription     | Resume a previously paused subscription                                      | `resumeSubscription`     |
| Reactivate Subscription | Reactivate a subscription marked for cancellation (subject to package terms) | `reactivateSubscription` |
| Remove Subscription     | Remove (cancel) a subscription at period end                                 | `removeSubscription`     |