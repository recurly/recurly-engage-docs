---
title: APIs
excerpt: >-
  How to configure custom API actions within Recurly Engage, including setting
  up credentials and defining action details.
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
          You must have <strong>Company</strong> or <strong>App Administrator</strong> permissions in Recurly Engage.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

Custom API actions allow you to call external backend endpoints with dynamic user data and secure credentials directly from prompts.

# Key benefits

* **Leverage existing systems**: Integrate with your own APIs without additional development in Recurly Engage.
* **Secure and dynamic**: Store credentials securely and inject user-specific data into API calls.
* **Flexible configurations**: Define URLs, methods, headers, query strings, and payloads for diverse use cases.

# Key details

You may define custom API actions to leverage existing backend endpoints, specifying to send dynamic user data and secure credentials as required.

### Add Credentials

Credentials data is stored in a secure, encrypted location that is only accessible to components tasked with performing the action. The most common credentials are API keys or client secrets.

Add a new credential and specify the name and the value.

<Image align="center" className="border" border={true} src="https://files.readme.io/faeced9-Screenshot_2024-05-02_at_15.50.02.png" />

### Add Actions

Define a custom API action—specify the URL, HTTP Method, request headers, query string, and request payload (if necessary).

Static and dynamic values are supported. Use the special character (%) and placeholders to inject dynamic user data. Placeholders like `%provider.api_key%` or `%provider.client_secret%`, user traits ingested via Recurly Engage, and [form inputs](forms) can be referenced. Dynamic values are supported in URLs, payloads, headers, and query strings.

**Note**: Payloads do not support complex JSON structures—only a single level of key–value pairs.

<Image align="center" className="border" border={true} src="https://files.readme.io/8a45296-Screenshot_2024-05-02_at_15.52.36.png" />