---
title: Website
excerpt: >-
  How to configure and use Website Actions within Recurly Engage, including
  adding simple built-in actions and custom JavaScript code.
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

* You must have **Company** or **App Administrator** permissions in Recurly Engage.

# Definition

Custom API actions allow you to call external backend endpoints with dynamic user data and secure credentials directly from prompts.

# Key benefits

* **Leverage existing systems**: Integrate with your own APIs without additional development in Recurly Engage.
* **Secure and dynamic**: Store credentials securely and inject user-specific data into API calls.
* **Flexible configurations**: Define URLs, methods, headers, query strings, and payloads for diverse use cases.

# Key details

You may define custom API actions to leverage existing backend endpoints, specifying to send dynamic user data and secure credentials as required.

### Add credentials

Credentials data is stored in a secure, encrypted location that is only accessible to components tasked with performing the action. The most common credentials are API keys or client secrets.

Add a new credential and specify the name and the value.

<Image align="center" className="border" border={true} src="https://files.readme.io/faeced9-Screenshot_2024-05-02_at_15.50.02.png" />

### Add actions

Define a custom API action—specify the URL, HTTP Method, request headers, query string, and request payload (if necessary).

Static and dynamic values are supported. Use the special character (%) and placeholders to inject dynamic user data. Placeholders like `%provider.api_key%` or `%provider.client_secret%`, user traits ingested via Redcurly Engage, and [form inputs](forms) can be referenced. Dynamic values are supported in URLs, payloads, headers, and query strings.

**Note**: Payloads do not support complex JSON structures—only a single level of key–value pairs.

<Image align="center" className="border" border={true} src="https://files.readme.io/8a45296-Screenshot_2024-05-02_at_15.52.36.png" />