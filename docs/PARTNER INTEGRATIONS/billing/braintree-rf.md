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

export const PrerequisitesLimitations = ({ header }) => {
  return (
    <div className="flex justify-start">
      <div className="rounded-md p-6 m-4 max-w-lg shadow-md border border-gray-300 dark:bg-gray-800 dark:border-gray-600">
        <p className="text-lg font-bold">{header}</p>
        <p>
          <i className="fa-solid fa-check mr-2" />
          <strong>Company</strong> or <strong>App Administrator</strong> permissions in Recurly Engage.
        </p>
        <p>
          <i className="fa-solid fa-check mr-2" />
          Active Braintree account with access to the control panel to retrieve gateway credentials.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

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