---
title: ActiveCampaign
excerpt: >-
  Configuration guide for the ActiveCampaign connector in Recurly Engage—API
  setup and supported automation actions.
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

The **ActiveCampaign** integration lets you add or update contacts and manage lists and automations directly from Recurly Engage prompts, leveraging your ActiveCampaign marketing workflows.

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

### Prerequisites & limitations

* Company or App Administrator permissions in Recurly Engage.
* An ActiveCampaign account with API access enabled.
* Ensure your ActiveCampaign subscription allows API usage and automations.

# Definition

The **ActiveCampaign** connector synchronizes contact data and exposes actions—such as adding contacts, subscribing to lists, and triggering automations—from within your in-app or web prompts.

# Key benefits

* **Automated contact flows**: Enroll users into marketing lists and automations seamlessly.
* **Personalized engagement**: Trigger tailored email or SMS campaigns based on user interactions.
* **Unified interface**: Manage marketing workflows without leaving the Recurly Engage console.

# Key details

## Required settings

Under **Settings > Connectors > ActiveCampaign**, provide:

* **API Key**: Obtain from your ActiveCampaign account (see [Getting started with the API](https://help.activecampaign.com/hc/en-us/articles/207317590-Getting-started-with-the-API#getting-started-with-the-api-0-0)).
* **Subdomain**: Your ActiveCampaign account subdomain (e.g., `myaccount` in `myaccount.api-us1.com`).

## Supported actions

Use these actions within prompt configurations to drive marketing automations:

| Action                | Description                                                                                                                                           | Additional Instructions | Form Inputs                                         |
| :-------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------- | :---------------------- | :-------------------------------------------------- |
| **Add Contact**       | Add or update a user record in ActiveCampaign contacts.                                                                                               | None                    | Use Form Inputs to capture contact fields if needed |
| **Add to List**       | Subscribe the user to a specified contact [list](https://help.activecampaign.com/hc/en-us/articles/5772650812316-Where-can-I-find-my-lists).          | None                    | Select the desired List ID from dropdown            |
| **Add to Automation** | Enroll the user into an [automation](https://help.activecampaign.com/hc/en-us/articles/218788657-What-are-automations-in-ActiveCampaign-An-overview). | None                    | Select the Automation ID from dropdown              |

Attach these actions to prompt interactions (Accept, Secondary Accept, etc.) to automate your marketing campaigns directly from user prompts.