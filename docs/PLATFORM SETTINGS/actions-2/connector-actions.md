---
title: External
excerpt: >-
  How to configure and use connector actions in Recurly Engage to interact with
  third‑party services.
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

This feature or setting is available to all customers on any Recurly Engage subscription plan. Adobe and Salesforce integrations can be purchased for an add-on fee.

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
          <i className="fa-solid fa-exclamation-triangle mr-4" />
          Relevant third‑party accounts and API credentials must be provisioned before configuring connectors.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

Connector actions are predefined integrations that let you execute operations in external systems when users interact with your in‑app prompts (e.g., clicking a CTA). These actions are configured in the Recurly Engage console and invoked automatically at runtime.

# Key benefits

* **Automate workflows**: Trigger downstream processes like billing updates or CRM entries without manual intervention.
* **Unified interface**: Manage all third‑party integrations from a single console.
* **Flexible triggers**: Actions can run on accept, secondary accept, decline, dismiss, or timeout events.

# Key details

Connector actions require that certain user attributes (e.g., account IDs, email addresses, device tokens) be synced into Recurly Engage beforehand. See each connector’s documentation for specific data dependencies.

## Connector categories and links

* **Billing**

  * [Recurly](recurly)
  * [Stripe](stripe)
  * [Zuora](zuora)
  * [Braintree](braintree)
  * [Chargify](chargify)
  * [Vindicia](vindicia)
  * [In‑App Purchases](app-stores) (Apple, Google, Amazon, Roku)
  * [Shopify](shopify)
  * [Cleeng](cleeng)

* **CRM & Marketing**

  * [Salesforce Marketing Cloud](salesforce-marketing-cloud)
  * [Segment](segmentio-twilio)
  * [Braze](braze)
  * [SendGrid](sendgrid)
  * [ActiveCampaign](activecampaign)
  * [Freshdesk](freshdesk)
  * [Zendesk](zendesk)
  * [Adobe (AEP & AJO)](adobe-aep-ajo)

* **Analytics & Events**

  * [Google Analytics](google-analytics)
  * [Mixpanel](mixpanel)
  * [mParticle](mparticle)
  * [Heap](heap)

***

## Configuring a connector

1. Navigate to **Settings > Actions** in the Recurly Engage console.
2. Select the desired connector from the list.
3. Enter the required API credentials and configuration fields.
4. Toggle **Active** and click **Save**.

<Image align="center" className="border" border={true} src="https://files.readme.io/3f60efa-image.png" />

After activation, connector actions will appear in each prompt’s **Actions** configuration panel, where you can assign them to specific user interaction events.