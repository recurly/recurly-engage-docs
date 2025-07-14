---
title: Limits
excerpt: >-
  Guide to configuring prompt delivery limits—impression, frequency, budget,
  user, and delivery caps—in Recurly Engage.
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

Limits let you control how often and to how many users a prompt can be shown. Apply limits per prompt or use [Global limits](global-limits) for account-wide caps.

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

### Prerequisites & limitations

* You must have **Company**, **App Administrator**, **App Member** permissions in Recurly Engage in order to create or update Prompt limits.
* You must have **Company**, **App Administrator** permissions in Recurly Engage in order to update Global Limits.
* Global limits affect all prompts and require appropriate application-level configuration.

# Definition

A **limit** restricts prompt exposures based on impressions, user frequency, spendable budget, or user and delivery caps, ensuring controlled rollout and budget adherence.

# Key benefits

* **Cost control**: Prevent overspending by capping impressions or budget.
* **Audience management**: Avoid overexposure by limiting frequency per user or total deliveries.
* **Scalable governance**: Use global limits for consistent thresholds across all prompts.

# Key details

## Impression limit

Restricts the total number of times a prompt is shown to the targeted segment, regardless of user. Once the impression count is reached, the prompt stops displaying.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/a7d13f1-image.png" />

## Frequency cap

Limits how many times an individual user can see the prompt within a defined period. For example, 2 impressions over 30 days means each user can view the prompt twice in a rolling 30-day window starting from their first impression.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/fb6c9f7-image.png" />

## Budget limit

Sets a consumable budget that decreases each time a user takes the prompted action. Configure a total budget and decrement value—for instance, a $10,000 budget with a decrement of $10 charges $10 per user interaction until funds are exhausted.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/42214b6-image.png" />

## User limit

Caps the total number of unique users who can receive or act on the prompt. For example, a user limit of 1,000 ensures that only the first 1,000 eligible users see the prompt.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/b726d62-image.png" />

## Delivery limit

Restricts the number of unique deliveries—instances when a user meets trigger conditions and is eligible to see the prompt. A delivery limit of 1,000 delivers to the first 1,000 unique users matching the trigger, then stops.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/9a7bf89-image.png" />

Learn more about account-wide limits in [Global limits](global-limits).