---
title: Recurly Engage setup
excerpt: >-
  Guidance on configuring your application in Recurly Engage: name, domain, and
  alias setup for a branded, secure integration.
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

This page walks you through setting up your application in the Recurly Engage console. You’ll learn how to give your app a clear name, register the domain where it’s hosted, and—if needed—manage multiple domain aliases for unified control.

export const PrerequisitesLimitations = ({ header }) => {
  return (
    <div className="flex justify-start">
      <div className="rounded-md p-6 m-4 max-w-lg shadow-md border border-gray-300 dark:bg-gray-800 dark:border-gray-600">
        <p className="text-lg font-bold">{header}</p>
        <p>
          <i className="fa-solid fa-check mr-2" />
          You need <strong>Administrator</strong> access to configure your Recurly Engage account.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

An **application** in Recurly Engage is the container for your integration: it holds your app’s name, its primary domain, and any additional domains you want to manage under one console.

# Key benefits

* **Centralized management**: Define and update your app’s settings from a single, intuitive console.
* **Flexible branding**: Use domain aliases to serve multiple brands or environments without repeating setup steps.
* **Consistent user experience**: Guarantee that every domain you control delivers the same secure, branded checkout flow.

# Key details

1. **Application name**

   * Enter a friendly name for your app or website (for example, `Demo`).

2. **Primary domain**

   * Provide the domain where your app lives (for example, `demo.recurlyengage.com`).
   * You don’t need to include subdomains like `www` unless you plan to host multiple applications under the same root domain.

3. **Domain aliases**

   * Aliases let you run multiple domains through one Recurly Engage configuration.
   * Perfect when you have several brands or testing environments pointing to the same backend.

   <br />

   <Image align="center" className="border" border={true} src="https://files.readme.io/172cd70-Screenshot_2024-05-24_at_6.21.22_PM.png" />

Learn more about application settings <a href="http://docs.recurly.com/recurly-engage/docs/application#/" target="_blank" rel="noopener">here</a>.