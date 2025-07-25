---
title: Amazon
excerpt: >-
  Setup guide for the Amazon Device Messaging (ADM) connector in Recurly Engage
  Push Prompts.
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
          App must integrate the Recurly Engage SDK on the target platform.
        </p>
        <p>
          <i className="fa-solid fa-exclamation-triangle mr-4" />
          Supported only on Fire OS devices with ADM support.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

ADM Connector imports your ADM credentials into Recurly Engage, allowing you to deliver push notifications via Amazon’s push infrastructure.

# Key benefits

* **Native device reach**: Send push notifications to Fire tablets and Fire TV devices.
* **Easy configuration**: Use existing ADM credentials without additional infrastructure.
* **Integrated workflows**: Include push prompts as part of your Recurly Engage campaigns.

# Key details

## Required information

Provide the following in **Settings > Push Credentials**:

* **ADM Client ID**
* **ADM Client Secret**

Follow Amazon’s guidelines to obtain these credentials: [Obtain ADM Credentials](https://developer.amazon.com/docs/adm/obtain-credentials.html).

Once configured, ADM push prompts become available under **Prompts > New Prompt > Push**.