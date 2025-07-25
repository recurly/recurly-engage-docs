---
title: Naviga
excerpt: >-
  Configuration guide for the Naviga connector in Recurly Engage—setup and
  supported subscription actions for news and publishing platforms.
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

Naviga Subscribe is a common backend for news and publishing customers. With Naviga Subscribe version 3.13+ and NCS Circ 2018.5 SP1, Recurly Engage can utilize 1-Click actions to manage subscriptions directly from prompts.

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
          <i className="fa-solid fa-exclamation-triangle mr-4" />
          Your environment must run Naviga Subscribe v3.13 or later and NCS Circ 2018.5 SP1+.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

The **Naviga** connector integrates Recurly Engage with the Naviga Subscribe API to check subscription status, create, start, or end subscriptions via prompts.

# Key benefits

* **Streamlined workflows**: Trigger subscription checks and lifecycle actions without leaving your app.
* **Seamless integration**: Use Naviga’s existing subscription backend for real-time updates.
* **User-centric prompts**: Personalize prompts based on subscription state.

# Key details

## Supported actions

Use these actions within prompt configurations (accept, secondary accept, etc.) to drive Naviga workflows:

| Action              | Description                                 | API Method                                                  |
| ------------------- | ------------------------------------------- | ----------------------------------------------------------- |
| Check Subscription  | Verify if a user has an active subscription | `GET /subscribe/v1/subscription/status?userId=<USER_ID>`    |
| Create Subscription | Create a new subscription for a user        | `POST /subscribe/v1/subscription`                           |
| Start Subscription  | Activate a pending subscription             | `POST /subscribe/v1/subscription/{subscriptionId}/activate` |
| End Subscription    | Cancel or end an active subscription        | `POST /subscribe/v1/subscription/{subscriptionId}/cancel`   |

These actions leverage the [Naviga Subscribe API](https://docs.navigaglobal.com/naviga-subscribe/additional-resources/subscribe-apis/subscribe-api). Reach out to your Customer Success Manager for partnership details and advanced integration options.