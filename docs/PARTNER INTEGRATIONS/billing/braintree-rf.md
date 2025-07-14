---
title: Braintree
excerpt: Setup and action guide for the Braintree connector in Recurly Engage.
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
* Active Braintree account with access to the control panel to retrieve gateway credentials.

# Definition

The **Braintree** connector syncs with your Braintree gateway using merchant credentials to trigger subscription management actions directly from prompts.

# Key benefits

* **Seamless payment workflows**: Subscribe users to plans or apply discounts without redirecting them.
* **Secure integrations**: Use official Braintree API keys for authentication.
* **Customizable prompts**: Offer in-context subscription options and promotions.

# Key details

## Required settings

Under **Settings > Connectors**, provide:

* **Merchant ID**
* **Public key**
* **Secret key**

## Supported actions

Use these connector actions within your prompts to manage subscriptions:

| Action         | Description                               | User Dependencies                 | Additional Instructions                  |
| -------------- | ----------------------------------------- | --------------------------------- | ---------------------------------------- |
| Subscribe Plan | Subscribe the user to a specific plan     | `braintree_id` or `email_address` | Select a plan from the dropdown          |
| Add Discount   | Apply a discount to a user’s subscription | `braintree_id` or `email_address` | Select a discount code from the dropdown |

## Additional resources

**Learn more** about retrieving your Braintree credentials here: [Braintree API keys](https://developer.paypal.com/braintree/articles/control-panel/important-gateway-credentials).