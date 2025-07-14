---
title: Pipelines
excerpt: >-
  Overview of Recurly Engage Pipelines for lifecycle staging and behavior-based
  user segmentation.
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

Recurly Engage Pipelines provide a unique way to manage users across various lifecycle stages or custom behavior loops. Use pipelines to visualize where users are and to trigger targeted prompts that move them to the next stage.

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

### Prerequisites & limitations

* You must have **Company**, **App Administrator** or **App member** permissions in Recurly Engage.
* Pipelines update automatically based on incoming trait and usage data; allow time for data refresh.

# Definition

A **pipeline** is a multi-stage user lane—either lifecycle-based or custom—that organizes users by progression and allows you to attach prompts to drive movement between stages.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/effdb79-Screenshot_2024-04-30_at_6.53.20_PM.png" />

# Key benefits

* **Holistic user view**: See where users reside in their journey—from anonymous visitors to loyal customers.
* **Behavioral reinforcement**: Create custom pipelines to reward and reinforce desired usage patterns.
* **Prompt orchestration**: Attach prompts at each stage to guide users forward in the funnel.

# Key details

## Lifecycle pipelines

Recurly Engage includes three out‑of‑the‑box pipelines:

### Member Pipeline

1. **Anonymous**: Visitors to marketing pages.
2. **Trial**: Users in their trial period.
3. **Monthly**: Subscribers on a monthly plan.
4. **Premium**: Subscribers on a premium plan.
5. **Pending Cancel**: Canceled subscribers with continued access.
6. **Cancelled**: Users who have fully churned.

### Engagement Pipeline

1. **New users**
2. **Repeat users**
3. **Regular users**
4. **Frequent users**
5. **Heavy users**

> Each stage can be further segmented into **Engaged** (increasing activity), **At Risk** (decreasing activity), or **Everyone Else** based on visits and minutes trends.

### E‑commerce Pipeline

1. **Visitor**: Has not started checkout.
2. **Shopper**: Added items to cart.
3. **Checkout**: In the checkout process.
4. **Customer**: Completed purchase.

## Behavior pipelines

Create custom, behavior‑driven pipelines to reinforce lifetime value patterns. For example, a “Watch More” pipeline:

1. Watched one episode
2. Watched two episodes
3. Watched three or more episodes

## Moving users between stages

You can attach prompts directly to any pipeline stage. For example, to convert **Engaged Trial** users into paying members before trial expiry:

1. Click **Add Prompt** on the **Trial** stage.
2. Select a prompt style and target the sub‑segment (“Engaged Trial”).
3. Define a custom goal and continue configuring the prompt as usual.

The remaining setup steps follow the same flow as [creating a prompt](prompts). Once live, prompts will fire when users enter that pipeline stage, driving them toward the next segment.

<Image align="center" className="border" border={true} width="60% " src="https://files.readme.io/05d43d1-Screenshot_2024-04-30_at_7.00.32_PM.png" />