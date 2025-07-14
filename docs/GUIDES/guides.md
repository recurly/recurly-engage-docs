---
title: 'Overview: Guides'
excerpt: >-
  Overview and how-to for multi-step Guides in Recurly Engage, including
  wizards, surveys, journeys, and triggered flows.
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

### Video

<Embed url="https://www.loom.com/embed/936c535cfaf74ba2afcd89474b8a9d9b?sid=faff98b4-6cde-49fb-b205-f1df5dac4075" href="https://www.loom.com/embed/936c535cfaf74ba2afcd89474b8a9d9b?sid=faff98b4-6cde-49fb-b205-f1df5dac4075" typeOfEmbed="iframe" height="480px" width="100%" iframe="true" />

### Required plan

This feature **may not be included** in the all plans. If you are interested, please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) to discuss upgrade options.

###

### Prerequisites & limitations

* You must have **Company**, **App Administrator** or **App member** permissions in Recurly Engage.
* Guide type is fixed on creation and cannot be changed later.

# Definition

A **guide** binds multiple prompts into a controlled flow, enabling sequential, branched, or conditional delivery based on user behavior and scheduling.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/bd78e59-image.png" />

# Key benefits

* **Structured interactions**: Deliver step-by-step experiences to users.
* **Dynamic branching**: Use survey logic or conditions to tailor the flow.
* **Cross-device continuity**: Maintain guide state as users switch devices.

# Key details

## Wizard

Supported on Web and HTML5-based smart TVs.

Wizard guides present prompts immediately in the defined order within a single session. Only the first prompt requires a trigger; subsequent prompts fire automatically upon interaction with the previous prompt.

Items within a guide inherit the guide’s configurations: [Limits](limits-1), [Segments](segments), [Schedule](schedule-1).

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/8a86d2f-image.png" />

## Survey

Supported on Web and HTML5-based smart TVs.

Survey guides collect user input through branching prompts. Subsequent prompts are shown based on the user’s selection in earlier steps.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/e09a8bd-image.png" />

## Journey

Supported on all devices.

Journey guides onboard new users or deliver feature tours over time. You can configure them to show only unseen items or enforce a strict order, triggering based on visits, interactions, or time delays.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/9a5b99e-image.png" />

Items within a guide can be connected based on:

* **Interactions**: Show an item only if another guide item was seen, accepted, declined, or dismissed.
* **Next Visit**: Trigger the next item on the user’s subsequent session.
* **Days**: Delay the next item by a set number of days across sessions.
* **Minutes**: Delay the next item by minutes within the same session.

## Triggered

Supported on all devices.

Triggered guides reinforce messages by delivering one of several prompts based on user eligibility and predefined conditions. You can prevent users from receiving multiple similar items by setting exclusion rules across guide items.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/831f597-image.png" />

***

## Guide

1. **Go** to **Guides > New Guide**.
2. **Enter** a **Name** and optional **Description**. **Select** the **Guide Type** and **Segments** (guide type cannot be changed later).
3. **Add** at least two prompts as guide items.
4. **Configure** **Continue** and **Exit** conditions for each item.
5. (Optional) **Set** **Limits** and a **Schedule** for the entire guide.
6. **Click** **Start** to make your guide live.

Your multi-prompt guide is now running—monitor performance and adjust as needed!