---
title: Tours
excerpt: >-
  Build a Tour in Recurly Engage — a multi-step, element-anchored tooltip
  walkthrough that guides subscribers through your site.
deprecated: false
hidden: true
metadata:
  robots: index
---

<Image src="https://files.readme.io/1f6d86df9a58a93612e0d46b33ca98cc46e98855de121e98038d753085013a40-Screenshot_2026-07-20_at_1.23.50_PM.png" align="center" width="500px" />


# Overview

## Prerequisites

You must have Company, App Administrator, or App Member permissions in Recurly Engage.

## Limitations

Tours run in standard web browsers only. They are not currently supported on connected TV (CTV), mobile, or other device platforms.


Guide type is fixed on creation and cannot be changed later — confirm you want a Tour before you build.
Element anchoring (pinning) is available on steps within a Tour, not on standalone notifications.

# Definition

A Tour is a guide type that walks subscribers through your site with a sequence of floating tooltips, each anchored to a specific element on the page. It's built for onboarding, feature discovery, and guided navigation — helping new subscribers find value quickly, without a third-party onboarding tool.

A Tour progresses like a Wizard: the subscriber moves through steps in a fixed, sequential order and can move backward to revisit a step they've already seen. Because steps can span multiple pages, you can guide a subscriber from, say, a homepage to an account page within a single flow. Everything is configured natively in Engage.

# Key benefits

- **Native onboarding:** Guide subscribers through your product without adding a separate onboarding tool or contract.
- **Element-anchored guidance:&#x20;**&#x41;ttach each tooltip to the exact element it describes, so guidance lands in context.
- **One place for data:** Tour impressions, step completions, and exits flow into your existing Engage analytics alongside your other prompts.

# Key details

## How a Tour works

Each Tour step is a web notification prompt with two capabilities specific to Tours:

- **Pin to element:&#x20;**&#x41;nchor the notification to a page element using a CSS selector, then choose whether it appears to the top, bottom, left, or right of that element. Pinning overrides the size and position set in the prompt's standard size and position settings.
- **Scroll into view:** If the anchored element is off-screen, the page auto-scrolls until the notification is visible. Position it at the top, center, or bottom of the viewport, or turn auto-scroll off.

Navigation follows a fixed model: button one advances to the next step, button two is the **Back** button, and dismissing any step (the X) exits the entire Tour. Subscribers move through steps sequentially — they can't skip from step 1 to step 3 — but can move freely backward and forward through steps they've reached.

Items within a guide inherit the guide's configurations: Limits, Segments, Schedule.

## Build a Tour

1. **Go** to **Guides** > **New Guide.**
2. **Enter** a **Name** and optional **Description**. **Select** the **Tour** guide type and your **Segments** (guide type cannot be changed later).
3. **Add** your Tour steps in the order subscribers should see them. Each step is a web notification prompt with its own content, targeting, and placement.
4. For each step, **configure** the **Pin to** section:
   1. **Enter** the **CSS selector** of the element you want to anchor the tooltip to.
   2. **Choose** the placement relative to that element: top, bottom, left, or right.
5. (Optional)**&#x20;Set&#x20;**&#x74;he **scroll into view** behavior so the page scrolls the anchored element into view — top, center, or bottom of the viewport — when the step triggers.
6. **Configure&#x20;**&#x74;he step's navigation so it displays again after button one or button two is clicked. This lets subscribers see a step again when they navigate backward or forward to it.
7. **Set** the **transition URL** for any step that moves the subscriber to a different page. This tells Engage where to navigate next as the subscriber moves forward or backward through the Tour.
8. **Configure** the guide's trigger conditions (audience segment, page URL, event, and schedule) using the standard Engage targeting options.
9. (Optional) **Set Limits** and a **Schedule** for the entire Tour.
10. **Preview** the Tour against your site to confirm positioning and copy, then click Start to make it live.

Your Tour is now running — monitor step completions and exits in your Engage analytics, and adjust copy or placement for any step where subscribers drop off.

<br />
