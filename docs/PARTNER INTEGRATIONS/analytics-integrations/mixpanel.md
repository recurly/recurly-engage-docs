---
title: Mixpanel
excerpt: >-
  Integration guide for the Mixpanel connector in Recurly Engage—setup and
  required credentials for event and user trait sync.
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

The **Mixpanel** integration streams Recurly Engage prompt events and user traits into your Mixpanel project, enabling advanced analytics and segmentation based on in-app messaging interactions.

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
          A Mixpanel account with Service Account credentials and project access.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

The **Mixpanel** connector authenticates via service account credentials and uses your project token to send prompt events and mapped user traits to Mixpanel in real time.

# Key benefits

* **Unified analytics**: Combine prompt interactions with existing Mixpanel event streams for comprehensive user behavior insights.
* **Segmentation**: Leverage Mixpanel’s powerful cohort and segmentation tools based on prompt engagement.
* **Real-time sync**: Forward events and user traits immediately upon prompt interactions.

# Key details

## Information

Once activated, Recurly Engage will send both prompt interaction events (impression, click, dismiss, etc.) and configured user trait properties to Mixpanel.

* [Mixpanel Service Accounts](https://developer.mixpanel.com/reference/service-accounts)
* [Mixpanel Project Token](https://developer.mixpanel.com/reference/project-token)

## Required settings

Under **Settings → Integrations → External → Mixpanel**, provide:

* **Service Account Username**
* **Service Account Password**
* **Project Token**
* **Project ID**