---
title: Stripe
excerpt: >-
  Configuration guide for the Stripe connector in Recurly Engage—activation,
  data sync, 1-Click actions, and subscription management.
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

The **Stripe** integration lets you manage subscriptions, trials, coupons, and usage-based workflows directly from Recurly Engage prompts by connecting to your Stripe account.

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

### Prerequisites & limitations

* Company or App Administrator permissions in Recurly Engage.
* A Stripe account with API access credentials and webhook capability.
* Users in Recurly Engage must have `stripe_id` or `email_address` traits for action targeting and webhook syncing.

# Definition

The **Stripe** connector offers two activation methods—Stripe Connect or API Key—and supports real-time and nightly data syncs, plus 1-Click billing actions from prompts.

# Key benefits

* **Flexible activation**: Choose OAuth-based Stripe Connect or API Key authentication.
* **Real-time updates**: Webhook-driven trait sync for subscription status and billing events.
* **Comprehensive actions**: Upgrade, extend trials, apply coupons, and manage subscriptions without leaving prompts.

# Key details

## Activation

You may activate the Stripe connector utilizing one of two methods: Stripe Connect or API Key. Stripe Connect allows integration with Recurly Engage by authenticating with an existing Stripe user account. Alternatively, you may opt to generate a new API Key.

### Option 1: Stripe Connect

**Visit** **Settings → Actions → Stripe** and click the following button to authenticate via Stripe.com.

<Image align="center" className="border" border={true} src="https://files.readme.io/c2a06fc-Stripe_Connect.png" />

<br />

### Option 2: API Key

In the Stripe Dashboard, navigate to **Developers → API Keys**. Create a new **Restricted Key** and grant these permissions:

<Image align="center" className="border" border={true} src="https://files.readme.io/3020621-Stripe_key.png" />

| Resource Type   | Permissions | Connect Permissions |
| --------------- | ----------- | ------------------- |
| Customers       | Write       | None                |
| Subscriptions   | Write       | None                |
| Products        | Read        | None                |
| Prices          | Read        | None                |
| Coupons         | Read        | None                |
| Promotion Codes | Read        | None                |

Finally, copy the generated API key into the **Settings → Actions → Stripe** form in Recurly Engage.

## Data integration

### 1-click actions

After activation, available Plans and Coupons sync periodically for use in prompts. Ensure each user record includes `stripe_id` or `email_address`.

### Automated data sync

When using Stripe Connect, a webhook is created to sync subscription events in real time. Traits imported include:

| Trait Name                 | Values                                                                                                         |
| :------------------------- | :------------------------------------------------------------------------------------------------------------- |
| `subscription_status`      | `incomplete`, `incomplete_expired`, `trialing`, `active`, `past_due`, `canceled`, `unpaid`, `paused` or `NONE` |
| `delinquent`               | `true`, `false` (set to `true` when a payment fails)                                                           |
| `current_period_start`     | \<Start date of current billing period>                                                                        |
| `current_period_end`       | \<End date of current billing period>                                                                          |
| `canceled_at`              | \<Date of cancellation>                                                                                        |
| `cancel_at_period_end`     | `true`, `false`                                                                                                |
| `trial_start`              | \<Start date of trial>                                                                                         |
| `trial_end`                | \<End date of trial>                                                                                           |
| `subscription_plan`        | \<Name of current or most recent subscription plan>                                                            |
| `recurring_interval`       | `day`, `week`, `month`, `year`                                                                                 |
| `coupon`                   | \<Coupon name>                                                                                                 |
| `payment_card_brand`       | `<card brand>` (e.g., `visa`, `mastercard`, `amex`, `unknown`)                                                 |
| `payment_card_country`     | `<country code>` (2-character ISO)                                                                             |
| `payment_card_expiration`  | \<Payment card expiration date>                                                                                |
| `payment_card_wallet_type` | `<wallet type>` (e.g., `apple_pay`, `google_pay`, etc.)                                                        |

> **Note:** You must also perform a nightly CSV sync mapping your internal user IDs to Stripe Customer IDs.

## Supported actions

Attach these 1-Click actions to prompt interactions once your data sync is active:

| Action                       | Description                        | User Dependencies              | Additional Instructions                  |
| ---------------------------- | ---------------------------------- | ------------------------------ | ---------------------------------------- |
| Update existing subscription | Switch user to a different product | `stripe_id` or `email_address` | Multiple proration options available—see |

## Additional resources

* [Stripe API Key Setup](https://docs.stripe.com/keys)
* [Stripe Proration Guide](https://stripe.com/docs/billing/subscriptions/upgrade-downgrade#proration)