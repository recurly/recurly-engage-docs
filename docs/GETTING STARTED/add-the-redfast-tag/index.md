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

### Prerequisites & limitations

* You must have **Company**, **App Administrator** or **App member** permissions in Recurly Engage.
* You need access to modify your site’s HTML or tag manager container.
* If using a tag manager, ensure you have publish permissions.

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