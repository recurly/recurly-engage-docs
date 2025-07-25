---
title: Recurly Engage javascript tag
excerpt: >-
  Implementation details for adding the Recurly Engage tag to your site, via tag
  managers or direct script injection.
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
          You must have <strong>Company</strong>, <strong>App Administrator</strong>, or <strong>App Member</strong> permissions in Recurly Engage.
        </p>
        <p>
          <i className="fa-solid fa-check mr-2" />
          You need access to modify your site’s HTML or tag manager container.
        </p>
        <p>
          <i className="fa-solid fa-exclamation-triangle mr-4" />
          If using a tag manager, ensure you have publish permissions.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

The **Recurly Engage tag** is a lightweight JavaScript snippet that initializes Engage on your site. It enables tracking of user interactions and powers secure, branded checkout flows within your application.

# Key benefits

* **Easy integration**: Deploy via popular tag managers without editing page code.
* **Optimal performance**: Load asynchronously or deferred to avoid delaying page rendering.
* **Flexible deployment**: Choose from multiple tag managers or embed the script directly.

# Key details

The following tag managers are supported for convenience. You can also add the JS directly to your site if you prefer.

In most cases, we recommend using the `defer` or `async` script element attribute to ensure minimal impact on page rendering performance. The Recurly Engage tag will execute once the page has rendered. Please reach out to your customer success manager if you have questions on specific requirements.

* [Google tag manager](google-tag-manager)
* [Adobe dynamic tag manager](adobe-dynamic-tag-manager)
* [Tealium dynamic tag manager](tealium-iq-tag-manager)
* [Direct](direct)