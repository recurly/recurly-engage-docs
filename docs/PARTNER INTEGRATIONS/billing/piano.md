---
title: Piano
excerpt: >-
  How to connect and sync subscriber data from Piano to Recurly Engage, plus
  configure 1‑Click subscription actions.
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
          Access to your Piano account with permissions to export subscription reports or use the Piano Export API.
        </p>
        <p>
          <i className="fa-solid fa-exclamation-triangle mr-4" />
          Recurly Engage users must have the <code>subscription_id</code> trait set from Piano for action targeting.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

**Piano integration** synchronizes subscriber logs and traits into Recurly Engage and enables 1‑Click subscription actions via Piano’s Publisher APIs.

# Key benefits

* **Automated data sync**: Periodically import subscription logs for real‑time segment targeting.
* **In‑prompt workflows**: Use 1‑Click actions to resume or upgrade subscriptions without leaving the UI.
* **Flexible integrations**: Leverage both Piano Console exports and Piano’s REST APIs for custom sync schedules.

# Key details

## Sync subscriber info

### Using piano console

1. **Log in** to your Piano account.
2. **Navigate** to **Reports → Logs → Subscriptions**.
3. **Click** **Export**.
4. **Download** the completed file from the **Download Center**.

> **Note:** Steps may vary by Piano version. **See** Piano’s docs for details: [Subscription Log Report](https://docs.piano.io/subscription-log-report/).

### Using piano API

Use the **Piano Export API** to schedule subscription log exports programmatically.

See the API spec here: [Subscription Log Export API](https://docs.piano.io/api/?endpoint=post~2F~2Fexport~2Fschedule~2Fvx~2FsubscriptionLog).

Coordinate with your Customer Success Manager for automation assistance.

### Information synced

Include these traits in your CSV export for targeting in Recurly Engage:

```
Subscription ID
Create date
Start date
End date
Days subscribed
Subscription status
Upgrade status
Trial status
Trial period end date
Auto-renew
Auto-renew disablement date
Billing period
Total charged
Next billing date
Renewed
Currently in grace period
Grace period start date
Grace period extended to
User ID (UID)
Access expiration date
Resource ID (RID)
Resource name
Term ID
Term name
Term type
Template ID
Template name
Offer ID
Offer name
Promo code
```

## 1‑click actions

Configure these actions under your Piano connector settings in Recurly Engage (provide the Publisher API Token and `aid` Application ID).

### Resubscribe

Invokes Piano’s **Resume Subscription API** to cancel a pending cancellation and resume service. If `subscription_id` isn’t provided, Recurly Engage will discover it via the List Subscriptions API.

### Upgrade subscription

Calls Piano’s **Upgrade Subscription API** to change the subscription term. You must select the “from” and “to” term IDs in the prompt editor. The API will return availability status before proceeding; include messaging to indicate processing time to users.

## Promo codes

Although Piano lacks a direct API for coupon redemption, you can support promo workflows by:

* Listing and selecting available promo codes in prompt configurations
* Creating segments for promo‑eligible audiences
* Auto‑filling the promo code during your checkout process
* Tracking conversion post‑checkout
* A/B testing different promo codes for performance analysis

Use these capabilities together to deliver seamless subscription management experiences within your in‑app or in‑site prompts.