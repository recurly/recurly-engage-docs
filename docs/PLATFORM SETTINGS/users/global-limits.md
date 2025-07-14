---
title: Global limits
excerpt: >-
  Configuration guide for the Global Limits tab, which allows you to apply
  account-wide holdout, frequency cap, impression limits, and overlay interval
  settings in Recurly Engage.
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

* You must have **Company**, **App Administrator**, or **App Member** permissions in Recurly Engage.
* add additional prerequisites or limitations if any

# Definition

The **Global Limits** tab enables you to set account-wide constraints—such as holdout percentage, frequency cap, impression limit, and overlay interval—to control prompt exposure across your Pulse account.

# Key benefits

* **Consistent experimentation**: Ensure a controlled percentage of users never see prompts.
* **User-friendly experience**: Prevent overexposure by capping how often a user encounters prompts.
* **Resource management**: Limit total prompt impressions to manage system load and budgets.

# Key details

This tab allows you to apply limits to your Pulse account globally and set a holdout percentage, frequency cap, and/or impressions limit.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/f4f061d7ef9fb6a4431a7729f086f644fc8e4be964a70e48329b84af7d870f63-image.png" />

**Global Holdout** allows you to set up a percentage of users who will never experience any of the Recurly Engage prompts.\
For example, with the settings below, only 90% of your users across all segments will be presented with prompts.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/d4d64b2-image.png" />

**Global Frequency Cap** allows you to set the maximum number of prompts a user can be shown within a specified time range. For example, with the settings below, a single user can see no more than 10 prompts within 30 days. After 30 days, the cap is reset.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/50c0908-image.png" />

**Global Impression limit** allows you to restrict the total number of times prompts are shown to your users. For example, setting it to 100,000 impressions will limit the system to only show prompts the first 100,000 times they're triggered, and once the limit is reached, the prompts will be paused automatically. You can also configure a warning to notify you that the global impressions limit is approaching.

<Image align="center" className="border" border={true} src="https://files.readme.io/ad648f7-image.png" />

**Overlay Interval** allows you to set a minimum interval between overlay prompt impressions on web (page triggers only). For example, if you set the interval to 5 minutes, your users won't be shown page-triggered overlay prompts on web more often than every 5 minutes. Note that the interval resets if the browser tab is closed.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/e9f0c59531668b8b7da64d915c0cc155e828c69edc4c1106ff079f8456972c88-image.png" />

Once you've set the limits, make sure to hit the **Save changes** button to apply them to your account.