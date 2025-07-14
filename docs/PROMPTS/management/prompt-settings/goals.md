---
title: Goals
excerpt: How to set up and use custom conversion goals for your Recurly Engage prompts.
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

Custom goals let you track conversions beyond Redfast’s built‑in “prompt accepted” metric, such as page visits, API events, or external system activities.

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

### Prerequisites & limitations

* You must have **Company**, **App Administrator** or **App member** permissions in Recurly Engage.
* At least one usage tracker must exist before adding a custom goal.

# Definition

A **custom goal** is a user-defined conversion event—tracked via a usage tracker—that you attach to a prompt to measure success based on your specific criteria.

# Key benefits

* **Flexible measurement**: Define conversions like page visits, payment completions, or external API events.
* **Accurate attribution**: Attribute custom goals to prompt interactions with configurable time windows.
* **Deeper insights**: Compare prompt acceptance versus actual business outcomes for better optimization.

# Key details

## What you can track

* Visit to a specific URL path (e.g., `/payment-updated`)
* Arrival on a particular app screen (mobile or TV)
* Backend events (payment processed, subscription changed)
* External system activities accessible via your usage tracker

To use a custom goal, first create a [Usage Tracker](usage-tracking-1). Then follow the steps below to attach it to a prompt.

## Guide

1. **Locate** the usage tracker you want to use. In this example, we track when a user updates their payment method and lands on `/payment-updated`.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/c80c651-image.png" />

2. **Open** the prompt you wish to measure and click **Edit prompt details**.
3. **Scroll** to the **Custom Goal** section and click **Add custom goal**.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/ea36176-image.png" />

2. In the popup, **select** your usage tracker, **set** the attribution window (e.g., 24 hours), and **click** **Save**.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/075d4bd-image.png" />

2. **Publish** your prompt to start recording custom goal completions.
3. Under **Performance**, a **Custom goal** bar displays the number of users who completed the tracked action after interacting with the prompt.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/f478e3a-image.png" />