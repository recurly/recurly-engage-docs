---
title: Chargify
excerpt: Configuration and usage guide for the Chargify connector in Recurly Engage.
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

The **Chargify** integration enables you to manage subscriptions and coupons directly from your prompts, leveraging your Chargify billing system to automate user plan changes and coupon applications.

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

export const PrerequisitesLimitations = ({ header }) => {
  return (
    <div className="flex justify-start">
      <div className="rounded-md p-6 m-4 max-w-lg shadow-md border border-gray-300 dark:bg-gray-800 dark:border-gray-600">
        <p className="text-lg font-bold">{header}</p>
        <p>
          <i className="fa-solid fa-check mr-2" />
          You must have <strong>Company</strong> or <strong>App Administrator</strong> permissions in Recurly Engage.
        </p>
        <p>
          <i className="fa-solid fa-check mr-2" />
          A valid Chargify account with API access.
        </p>
        <p>
          <i className="fa-solid fa-exclamation-triangle mr-4" />
          User records in Recurly Engage must include the <code>chargify_id</code> trait for action targeting.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

The **Chargify** connector synchronizes products, coupons, and subscription data from Chargify into Recurly Engage, allowing you to trigger billing-related actions from within prompts.

# Key benefits

* **Automated billing workflows**: Create or cancel subscriptions directly from prompts.
* **Coupon management**: Apply coupon codes in real time as users interact.
* **Seamless user experience**: Keep users in the flow without manual backend steps.

# Key details

## Required settings

Configure your Chargify connector under **Settings > Connectors**:

* **API Key**: Your Chargify API key.
* **Domain**: Your Chargify site domain (e.g., `your-site.chargify.com`).

## Data integration

* **Products and coupons** are synchronized on a scheduled basis to ensure availability in prompt configurations.
* **Chargify ID** must be mapped to the user’s `chargify_id` trait in Recurly Engage for action execution.

## Supported actions

Use these actions within your prompt configurations to perform billing operations:

| Action              | Description                                              | User Dependencies | Additional Instructions                              |
| ------------------- | -------------------------------------------------------- | ----------------- | ---------------------------------------------------- |
| Create subscription | Subscribes a user to a specified Chargify product plan   | `chargify_id`     | Select the desired plan from the connector dropdown. |
| Cancel subscription | Cancels a user’s existing subscription to a product plan | `chargify_id`     | Choose which plan to cancel on the prompt screen.    |
| Add coupon code     | Applies a coupon code to a user’s subscription           | `chargify_id`     | Select both the plan and coupon code on the prompt.  |