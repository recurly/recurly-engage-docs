---
title: App Stores
excerpt: >-
  Guidance for configuring in-app purchase flows in Recurly Engage prompts
  across Roku, Apple, and Google platforms.
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

* App must integrate the Recurly Engage SDK on the target platform.
* Company or App Administrator permissions in Recurly Engage.
* In‑app products must be configured in the respective platform stores (Roku Channel Store, App Store Connect, Google Play Console).

# Definition

The **In-App Purchase** feature enables direct purchase or upgrade/downgrade flows from within prompts, leveraging native store dialogs and validation.

# Key benefits

* **Streamlined UX**: Let users complete purchases without leaving your app or prompt.
* **Consistent integration**: Use the same prompt UI across platforms while invoking native purchase flows.
* **Flexibility**: Support upgrades, downgrades, and one-time purchases natively.

# Key details

Configure your prompt’s main CTA to trigger the in‑app purchase flow for a specific product identifier. Steps vary by platform below.

## Roku App Store

1. **Open** the **Prompt Edit** screen in Pulse.
2. In the **In‑App Purchase** section, **enter** the **Product ID** matching your Roku In‑Channel Product Identifier.
3. **Choose** **Upgrade** or **Downgrade** from the dropdown to specify the purchase type.

<Image align="center" className="border" border={true} width="50% " src="https://files.readme.io/a4de93b-roku-inapp.png" />

4. When the user taps the CTA, the Roku SDK will initiate the appropriate purchase flow.

## Apple App Store

### Add In‑App Product IDs

1. **Navigate** to **Settings → Actions → Apple** in Pulse.
2. **Define** one or more **Product IDs** matching those in App Store Connect.

<Image align="center" className="border" border={true} width="600px" src="https://files.readme.io/d01be52-apple-add-inapp-product.png" />

### Attach to Prompt

1. **Open** the **Prompt Edit** screen and **select** the desired **Product ID** under **In‑App Purchase**.

<Image align="center" className="border" border={true} width="500px" src="https://files.readme.io/f500c36-appstore-select-inapp.png" />

4. The Recurly Engage SDK will handle the native purchase dialog when the CTA is clicked.

## Google Play Store

1. **Open** the **Prompt Edit** screen in Pulse.
2. **Enter** your **Product ID** under **In‑App Purchase**.
3. **User** clicks the CTA and the SDK triggers the Google Play purchase flow.

Use these settings to seamlessly integrate native in-app purchase experiences into your Recurly Engage prompts across Roku, iOS, and Android platforms.