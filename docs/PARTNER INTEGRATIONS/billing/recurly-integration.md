---
title: Recurly
excerpt: >-
  Configuration guide for the Recurly connector in Recurly Engage, including
  activation, data sync, and 1-Click subscription actions.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

The **Recurly** integration allows you to sync your subscription data and execute billing actions directly from prompts in Recurly Engage, leveraging your Recurly account.

### Video

<HTMLBlock>{`
<iframe width="712" height="400" src="https://www.loom.com/embed/46bc074c2ae84fcd8fd55d7b342859d2?sid=d12f25e0-c01d-4ce7-b63c-a6c26f28f83d" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe>
`}</HTMLBlock>

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.<br />

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
          A Recurly account with API access and valid API key.
        </p>
        <p>
          <i className="fa-solid fa-exclamation-triangle mr-4" />
          If your application uses custom User IDs (Account Codes), enable <strong>Use Account Code</strong> in the connector settings.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

The **Recurly** connector imports subscription traits nightly and provides actions for managing subscriptions—coupon application, plan changes, pauses, resumes—via prompts.<br />

# Key benefits

* **Seamless billing workflows**: Manage subscriptions without leaving the prompt interface.
* **Real-time data**: Keep segments and prompts in sync with nightly data imports.
* **Flexible configurations**: Support custom account codes and multiple subscription actions.

# Key details

## Activation

1. Generate an **API Key** in the Recurly console.
2. In Recurly Engage, navigate to **Settings > Integrations > Recurly** and paste your API Key.
3. Toggle **Use Account Code** to **On** if you map your own user IDs to Recurly Account Codes.
4. Toggle **Active** to **On**.

**API Key ([Instructions](https://docs.recurly.com/docs/api-keys) )**

## Data integration

to enable the automated sync.

Once enabled, the following traits are imported nightly:

| Trait Name                  | Description                                                                      |
| --------------------------- | -------------------------------------------------------------------------------- |
| `state`                     | Current state of subscription (`pending`, `active`, `canceled`, `expired`)       |
| `plan_code`                 | Plan code the customer is subscribed to                                          |
| `currency`                  | Currency of the subscription                                                     |
| `current_period_started_at` | Date/time when the current billing period starts                                 |
| `current_period_ends_at`    | Date/time when the current billing period ends                                   |
| `trial_started_at`          | Date/time when the trial period began                                            |
| `trial_ends_at`             | Date/time when the trial period ends                                             |
| `activated_at`              | Date/time the subscription became active                                         |
| `canceled_at`               | Date/time the subscription was canceled                                          |
| `expires_at`                | Date/time when the subscription will churn                                       |
| `status`                    | Invoice status (`pending`, `processing`, `past_due`, `paid`, `failed`, `voided`) |
| `maintenance_url`           | Link to the customer’s hosted account maintenance page (if enabled)              |

## Supported actions

Once your connector is active and data is synced, you can attach these 1-Click actions to prompt interactions. The **account\_code** or **account\_number** trait must be present on users.

| Action                    | Description                                                 | API Integration         | Additional Instructions                     |
| ------------------------- | ----------------------------------------------------------- | ----------------------- | ------------------------------------------- |
| Apply Coupon Code         | Applies a coupon code to the user's account or subscription | Coupon Redemption       | Select the coupon code                      |
| Pause Subscription        | Pauses a user's subscription                                | Pause Subscription      | Select how many billing cycles to pause for |
| Resume Subscription       | Resumes a paused subscription                               | Resume Subscription     |                                             |
| Switch Subscription       | Switches the user to a new plan                             | Subscription Change     | Select the plan                             |
| Create Subscription       | Creates a subscription for an existing account              | Create Subscription     | Select the plan and enter the currency      |
| Reactivate Subscription   | Reactivate a cancelled subscription                         | Reactivate Subscription |                                             |
| Update Subscription Price | Update price of an active subscription                      | Subscription Change     |                                             |
| Convert Trial             | Convert trial to paid subscription                          | Convert Trial           |                                             |
| Record Usage              | Logs a usage record for a subscription add-on               | Log Usage Record        | Select the add-on and amount                |
| Cancel Subscription       | Stops auto-renewal for an active subscription               | Cancel Subscription     | Select refund option                        |