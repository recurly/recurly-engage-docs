---
title: Google Analytics
excerpt: >-
  Configuration guide for integrating Recurly Engage with Google Analytics
  Measurement Protocol via API actions.
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
* A valid Google Analytics property with Measurement Protocol enabled.

# Definition

The **Google Analytics** integration allows you to send prompt and experience events from Recurly Engage to Google Analytics using API actions configured as POST requests to the Measurement Protocol endpoint.

# Key benefits

* **Enhanced analytics**: Track prompt interactions alongside other site events in Google Analytics.
* **Custom reporting**: Leverage dynamic parameters to slice and dice user engagement data.
* **Seamless setup**: Configure actions within the Recurly Engage console without additional middleware.

# Key details

## Create an action

Follow the steps to create an API action. This action must be a POST request to the Google Analytics Measurement Protocol endpoint: `https://www.google-analytics.com/collect`.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/ebf7cc4-Google_Analytics_Custom_Action.png" />

## Specify the payload

Add parameters to the payload—static or dynamic—using Measurement Protocol fields. Required parameters include:

* `v`: protocol version
* `tid`: web property ID (Tracking ID)
* `t`: hit type (e.g., `event`)

Optional parameters include:

* `cid`: client ID
* `ea`: event action
* `el`: event label

For a full list of supported parameters, see the [Measurement Protocol Parameter Reference](https://developers.google.com/analytics/devguides/collection/protocol/v1/parameters).

## Add action to prompt or experience

Once the action is defined, attach it to a prompt or experience:

Follow the steps here to [add the action](actions-1) to a prompt or experience.