---
title: Live
excerpt: >-
  Guide for the Live view in Recurly Engage, which provides near-real-time
  monitoring of prompt interactions and errors.
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

The **Live** view displays near-real-time prompt interactions and exceptions for the prompts you currently have active. Use it to filter, search, and troubleshoot your live prompts.

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

### Prerequisites & limitations

* You must have **Company**, **App Administrator**, or **App Member** permissions in Recurly Engage.
* No additional prerequisites or limitations at this time.

# Definition

The **Live** feature streams prompt events—impressions, clicks, timeouts, etc.—and any action errors (External, API, or Website) as they occur, so you can validate behavior and resolve issues immediately.

# Key benefits

* **Instant validation**: Verify that newly launched prompts are firing correctly the moment they go live.
* **Comprehensive monitoring**: Filter interactions by device platform, prompt type, or user ID to pinpoint activity.
* **Error tracking**: Switch to **Errors** mode to surface and investigate any action failures in real time.

# Key details

The Live feature can be used to:

* **Ensure** that recently launched prompts are working properly.
* **Monitor** live prompts during critical events.
* **Debug** end user support issues.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/c308d679aa03b9f70862664b088bb55718dc605a0fedaa1202edac91d4fd5c9f-image.png" />

<Image align="center" className="border" border={true} width="40% " src="https://files.readme.io/c11da48e14ad0d0fdf7007f45bffdd246785856d3086a9656e8d222a9fb737a2-image.png" />

## Event types

| Type                        | Description                                                                                                         |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------- |
| Impression                  | User was shown the prompt.                                                                                          |
| Timeout                     | User did not respond before the prompt timer ran out.                                                               |
| Dismiss                     | User dismissed the prompt by clicking on the X or outside the window (as configured in the Recurly Engage console). |
| Decline                     | User clicked on the decline link.                                                                                   |
| Click                       | User accepted the prompt (this has been phased out in favor of Goal).                                               |
| Goal                        | User accepted the prompt.                                                                                           |
| CustomGoals\[Activity Type] | User completed the defined custom goal after previously performing the specified activity type on a prompt.         |
| Exclude                     | User is part of the holdout group or not eligible for a prompt after the specified User Limit has been exceeded.    |
| Holdout                     | User is part of the holdout group or not eligible for a prompt after the specified User Limit has been exceeded.    |
