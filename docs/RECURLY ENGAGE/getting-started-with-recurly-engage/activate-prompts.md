---
title: Activate prompts
excerpt: >-
  How to move your prompts from draft to live in Recurly Engage, including QA
  review and full deployment.
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
* At least one prompt and the necessary segments must already exist.
* Prompt must have at least 1 trigger in order to run.
* Ended prompts cannot be restarted, but can be cloned.

# Definition

**Activating prompts** means enabling your designed prompts (pop-ups, interstitials, notifications, or video prompts) first for testing, then for full audience delivery.

# Key benefits

* **Safe QA**: Preview and tweak your prompt with a small group before broad release.
* **Phased rollout**: Control exactly when and to whom a prompt goes live.
* **Dynamic lifecycle**: Easily pause, restart, or end prompts without touching code.

# Key details

**Activation phases**

1. **Review phase**

   * Enable your prompt on an internal segment (for example, [Test Users](test-users)).
   * Perform final QA, preview live behavior, and refine settings.

2. **Active phase**

   * Attach all target segments to deploy the prompt at scale.
   * Monitor performance and engagement.

**Placement methods**

* **Recurly Engage Live tool**: Use the interactive point-and-click console tool (web only) with guidance from your support contact.
* **Class identifiers**: Work with your development team to add Recurly Engage IDs to specific elements for precise on-page placement.

**Managing prompt status**

* Once a prompt is live, you can **pause**, **restart**, or **end** it at any time—unless there’s an active experiment.
* If an experiment is running, end it before pausing the prompt to avoid conflicts.