---
title: Integrations
excerpt: >-
  How to activate and configure third-party connectors for billing, support,
  marketing, and analytics within Recurly Engage.
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

Recurly Engage supports dozens of prebuilt integrations—connectors that let you trigger actions in, or stream events to, your existing business systems.

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

### Prerequisites & limitations

* You must have **Company** or **App Administrator** permissions in Recurly Engage.
* Connector-specific credentials (API keys, client IDs/secrets, etc.)
* Appropriate permissions in both Recurly Engage and the target system

# Definition

An **integration** (or connector) links Recurly Engage prompts and user interactions with external platforms—enabling 1-click actions, event streaming, and data sync.

# Key benefits

* **Streamline workflows**: Automate subscription changes, support tickets, emails, and more directly from in-app prompts.
* **Unified user experience**: Keep your user’s context in sync across billing, CRM, support, and analytics systems.
* **Rapid time to value**: Prebuilt connectors mean you can be live in minutes, not weeks.

# Key details

## Configure external integrations

1. **Go to** Settings → Actions.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/3f60efa-image.png" />

2. **Select** a connector (e.g. Zuora).

<Image align="center" width="80% " src="https://files.readme.io/2bae331-image.png" />

3. **Fill in** the required credentials.

<Image align="center" width="80% " src="https://files.readme.io/5f1e9d9-image.png" />

4. **Toggle** to **Active** and **Save changes**

<Image align="center" width="80% " src="https://files.readme.io/dbee0b4-image.png" />

## Connector capabilities

### SendGrid

* Send dynamic template email to user’s email address
* Add user to contact list
* Send dynamic template email to a user-submitted address

### Salesforce.com

* Create a Case (Support Cloud)
* Post offer acceptance to feed on all existing Cases

### Zendesk

* Create support ticket with offer details
* Set priority on all tickets by that user
* Assign all existing tickets to a specific agent
* Suspend or restore a user
* Assign tickets to a group
* Delete or spam all existing tickets
* Update ticket status or source

### Stripe

* Subscribe the user to a specific plan
* Unsubscribe the user from a plan
* Add a coupon code at checkout
* Extend a user’s trial period
* Switch subscriptions immediately or at period end

### Zuora

* Subscribe user to a rate plan
* Cancel, suspend, or resume a subscription
* Change auto-renew settings

### Freshdesk

* Create support ticket upon offer acceptance
* Bulk-update ticket priority, status, group, responder, or source
* Soft-delete or restore contacts
* Delete all tickets for a contact

### Recurly

* Apply coupon codes
* Change, pause, resume, or create subscriptions
* Convert trials to paid
* Record usage

### Iterable

* Track custom events in Iterable
* Add users to lists or automations
* Send campaign emails to stored or inputted addresses

### Cleeng

* Switch subscription offers
* Apply coupon codes
* Reactivate subscriptions

### Braze

* Create or update a user record by email

### Apple (APNS)

* Trigger in-app purchase flows (Upgrade/Downgrade)
* Send push notifications via APNs

***

**Need another connector?**

Contact your Recurly Engage Customer Success team to request a custom integration or new connector.