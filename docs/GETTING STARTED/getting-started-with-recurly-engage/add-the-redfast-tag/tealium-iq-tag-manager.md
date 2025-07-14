---
title: Tealium iQ tag manager
excerpt: >-
  Step-by-step instructions for integrating the Recurly Engage JavaScript client
  via Tealium iQ Tag Manager.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

Use Tealium iQ Tag Manager to load the Recurly Engage SDK on your site without editing page code.

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

### Prerequisites & limitations

* You must have publish permissions in both your Recurly Engage and Tealium iQ accounts.
* Access to **Settings > Usage Tracking** in your Recurly Engage app.

# Definition

The **Tealium iQ Tag Manager integration** injects the Recurly Engage JS client via a generic script tag, enabling data collection and branded checkout flows.

# Key benefits

* **Rapid setup**: Deploy the client through Tealium’s UI—no code changes needed.
* **Unified tagging**: Manage Engage alongside all your marketing and analytics tags.
* **Instant rollouts**: Publish to Dev, QA, and Prod environments in one workflow.

# Key details

You can integrate the Recurly Engage JavaScript client into your web application via Tealium iQ Tag Manager by following the steps below. Once complete, Recurly Engage will begin syncing its data with your site to personalize customer experiences.

1. **Log in to Recurly Engage and select your application**: Ensure you’re in the correct app context.

2. **Retrieve the client URL**: Navigate to **Settings > Usage Tracking**.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/539dc52-Screenshot_2024-05-22_at_21.56.18.png" />

3. **Copy** the URL portion of the code snippet; you’ll need it in step 7.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/1e10450-Screenshot_2024-05-22_at_21.59.39.png" />

4. **Log in to Tealium iQ and select the correct profile**

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/7cde0a3-tealium-2a.png" />

5. **Add a new tag**: Go to the **Tags** tab and click **Add Tag**.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/daa497e-tealium-3.png" />

6. **Choose the Generic Tag template**: In the popup search for “Generic Tag” and click **Add**.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/af67285-tealium-4.png" />

7. **Configure the Recurly Engage tag**

* **Title**: Recurly Engage Tag
* **Type**: Script
* **Base URL**: Paste the URL from step 2
* **Request Script Once**: Enable

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/aaa8198-tealium-5a.png" />

<br />

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/93928cb-tealium-5.png" />

8. **Publish the tag**: Click **Dev**, **QA**, and **Prod** to push the tag through each environment.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/e8db19b-tealium-6.png" />