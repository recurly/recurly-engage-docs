---
title: Application
excerpt: >-
  Configure your application settings—ID, API Key, domain, aliases, and
  timezone—to ensure Recurly Engage functions correctly on your site or app.
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

This section lets you set up or update your application configuration in Recurly Engage.

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

The **Application** settings define the core identity and access credentials for your Recurly Engage instance, including tag installation and API usage.

# Key benefits

* **Secure access**: Manage your API Key with the ability to regenerate as needed.
* **Multi-domain support**: Use domain aliases to serve prompts across multiple brands or subdomains.
* **Accurate scheduling**: Set your application timezone for prompt scheduling and performance reporting.

# Key details

* **ID** — Your application’s unique identifier. Use this to [add the Recurly Engage tag](google-tag-manager) on your site via Google Tag Manager.
* **API Key** — Your application’s API key. The **ID** and **API Key** fields are pre-filled. Click the rotate icon to regenerate the key, which invalidates the previous one.
* **Name** (Required) — The friendly name of your site or application. Change this at any time.
* **Domain** (Required) — The primary domain where your application is accessed. No need to include subdomains like `www` unless you manage multiple apps under one domain.
* **Domain Aliases** — Additional domains that can use the same Recurly Engage configuration. Useful for multi-brand or regional deployments.
* **Timezone** — The application’s timezone. Used for prompt scheduling (unless user timezone is selected) and for displaying performance metrics.

<Image align="center" className="border" border={true} src="https://files.readme.io/46e455b-image.png" />