---
title: Data sources
excerpt: >-
  Use CSV uploads as data sources for dynamic prompt content and enrich in-app
  messages.
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

**Data sources** let you upload structured CSV content into Recurly Engage and reference those values within prompt copy via dynamic content insertion.

# Key benefits

* **Always up-to-date content**: Update external CSV and have prompts reflect new values without manual edits.
* **Eliminate errors**: Maintain a single source of truth for variable content (e.g., coupon details).
* **Flexible targeting**: Combine data source values with segmentation and dynamic variables for highly personalized messaging.

# Key details

Any user information synced to Recurly Engage can be used not only for segmentation but also as dynamic content within a prompt’s title or message body using [Dynamic Variables](doc:dynamic-variables).

Data source variables are another way to expand the content that can be shown. By uploading a CSV, you can import structured content to use within prompts.

For example, say you want to tell the user “Get 1 month off” but the actual discount may vary by the marketing department based on time of year, so it becomes “Get 2 weeks off.” One way is to manually edit the prompt each time there is a change, but a better way is to use a coupon data source.

In this example, you can upload a CSV with various coupon attributes.

<Image align="center" className="border" border={true} width="60% " src="https://files.readme.io/6a1c972-Capture-2024-05-20-182307.png" />

And reference just the value in the prompt by inserting dynamic content. This eliminates errors and allows you to import structured data from external sources into the system.

<Image align="center" className="border" border={true} width="60% " src="https://files.readme.io/cbfa10c-Capture-2024-05-20-182358.png" />

<br />

<Image align="center" className="border" border={true} width="60% " src="https://files.readme.io/cbfa10c-Capture-2024-05-20-182358.png" />