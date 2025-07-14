---
title: Amazon
excerpt: >-
  Setup guide for the Amazon Device Messaging (ADM) connector in Recurly Engage
  Push Prompts.
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

* Company or App Administrator permissions in Recurly Engage.
* App must integrate the Recurly Engage SDK on the target platform.
* Supported only on Fire OS devices with ADM support.

# Definition

ADM Connector imports your ADM credentials into Recurly Engage, allowing you to deliver push notifications via Amazon’s push infrastructure.

# Key benefits

* **Native device reach**: Send push notifications to Fire tablets and Fire TV devices.
* **Easy configuration**: Use existing ADM credentials without additional infrastructure.
* **Integrated workflows**: Include push prompts as part of your Recurly Engage campaigns.

# Key details

## Required information

Provide the following in **Settings > Push Credentials**:

* **ADM Client ID**
* **ADM Client Secret**

Follow Amazon’s guidelines to obtain these credentials: [Obtain ADM Credentials](https://developer.amazon.com/docs/adm/obtain-credentials.html).

Once configured, ADM push prompts become available under **Prompts > New Prompt > Push**.