---
title: Sendgrid
excerpt: Connect Recurly Engage to SendGrid for dynamic emails and list management
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

The **SendGrid** integration lets you send dynamic template emails and manage subscriber lists directly from Recurly Engage prompts—no custom code required.

### Required plan

This feature is available to all customers on any Recurly Engage subscription plan.

# Definition

The SendGrid connector uses your SendGrid API key to perform two core actions—sending dynamic template emails to users and adding users to SendGrid contact lists—whenever they interact with a prompt in Recurly Engage.

# Key benefits

* **On-brand communications**: Leverage your SendGrid dynamic templates for polished, consistent emails.
* **Automated list management**: Instantly add engaged users to segmented SendGrid lists.
* **Single-pane setup**: Configure credentials and actions entirely within the Recurly Engage console.

# Key details

## Required settings

Under **Settings → Connectors → SendGrid**, provide:

* **API Key**: Generate and copy from the <a href="https://sendgrid.com/docs/ui/account-and-settings/api-keys/" target="_blank">SendGrid API Keys</a> page.

## Supported actions

Use these actions within prompt configurations to drive SendGrid workflows:

| Action                          | Description                                   | User Dependencies          | Additional Instructions                                                                                   | Form Inputs |
| ------------------------------- | --------------------------------------------- | -------------------------- | --------------------------------------------------------------------------------------------------------- | ----------- |
| **Send dynamic template email** | Sends a selected dynamic template to the user | `email_address` (optional) | Select your SendGrid dynamic template on the prompt editor. Templates must be pre-configured in SendGrid. | optional    |
| **Add user to list**            | Adds the user to a specified SendGrid list    | `email_address`            | Choose the target SendGrid list on the prompt editor. Lists must be created in SendGrid ahead of time.    | n/a         |

## Additional information

Learn more about SendGrid lists in the official docs: <a href="https://www.twilio.com/docs/sendgrid/api-reference/lists/create-list" target="_blank">SendGrid Lists API Reference</a>

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/b2d12bf-sendgrid-lists-1.png" />

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/ea49a4a-sendgrid-dynamic-templates-2.png" />