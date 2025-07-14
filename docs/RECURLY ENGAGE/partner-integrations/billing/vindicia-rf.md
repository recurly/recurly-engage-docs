---
title: Vindicia
excerpt: >-
  Guide to configuring the Vindicia connector in Recurly Engage—setup, data
  sync, and subscription actions.
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

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

### Prerequisites & limitations

* Company or App Administrator permissions in Recurly Engage.
* A Vindicia account with REST API credentials.

# Definition

The **Vindicia** connector imports subscription and account traits from Vindicia and provides 1-Click actions—replace products, add campaigns, and add products—within your prompts.

# Key benefits

* **Seamless subscription updates**: Swap or add products in user subscriptions without backend calls.
* **Promotional management**: Attach campaigns (e.g., free trials, discounts) to active subscriptions.
* **Automated data sync**: Keep Recurly Engage updated with the latest billing and campaign data.

# Key details

## Required settings

Under **Settings > Connectors**, enter your Vindicia API credentials:

* **API Username**
* **API Password**

## Data integration

* Vindicia billing traits and account data ingest automatically upon connector activation.
* Products and campaigns synchronize periodically to remain current.
* User records in Recurly Engage must include `vindicia_subscription_id` or `vindicia_account_id` traits to enable action targeting.

## Supported actions

Use these actions within your prompt configurations to manage Vindicia subscriptions:

| Action          | Description                                                  | User Dependencies                                   | Additional Instructions                     |
| --------------- | ------------------------------------------------------------ | --------------------------------------------------- | ------------------------------------------- |
| Replace product | Replace a product in the user’s subscription with another    | `vindicia_subscription_id` or `vindicia_account_id` | Select the new Product(s) from the dropdown |
| Add campaign    | Attach a campaign (promo/trial) to the existing subscription | `vindicia_subscription_id` or `vindicia_account_id` | Select the Campaign from the dropdown       |
| Add product     | Add an additional product to the user’s subscription         | `vindicia_subscription_id` or `vindicia_account_id` | Select the Product from the dropdown        |