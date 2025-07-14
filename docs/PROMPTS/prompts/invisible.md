---
title: Invisible prompts
excerpt: >-
  Configure and trigger background behaviors in your application without any
  user-facing UI using Invisible Prompts.
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

* You must have **Company**, **App Administrator** or **App member** permissions in Recurly Engage.

# Definition

An **Invisible Prompt** is a hidden rule that executes server-side or client-side actions automatically upon matching a trigger. Unlike other prompts, it presents no UI to the user.

# Key benefits

* **Automate background tasks**: Launch API calls, hide or show UI elements, or apply discounts without user clicks.
* **Seamless user experience**: Modify behavior or content without interrupting the user.
* **Flexible triggers**: Fire on page load, custom events, or segment entry to suit any workflow.

# Key details

This prompt type shares its configuration flow with a [popup](overlays#how-to-video) but with no visual component. All actions run immediately when the trigger fires.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/c386e48-image.png" />

**Example use cases**

* Automatically add a show to a user’s watchlist on page load
* Hide competing ads for premium subscribers
* Trigger a fulfillment API or apply a discount coupon

## Configuring metadata

Use metadata tags to pass custom key-value pairs into your Invisible Prompt for advanced behaviors:

1. Click the **Edit** (pencil) icon on your Invisible Prompt to open the Metadata modal.

<Image align="center" width="80% " src="https://files.readme.io/e45aa27-image.png" />

2. Add one or more key-value pairs to tailor your action logic.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/7db1c7e-image.png" />

### Retrieving metadata in code

```javascript
Redfast.getMetas()
// returns { 'meta1': 'val1', 'meta2': 'val2' }
```

## Test the prompt

Validate your trigger and actions before full deployment by assigning the **Test Users** segment. Learn how in the [test user guide](test-users).