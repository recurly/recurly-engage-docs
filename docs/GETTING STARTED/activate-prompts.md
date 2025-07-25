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

export const PrerequisitesLimitations = ({ header }) => {
  return (
    <div className="flex justify-start">
      <div className="rounded-md p-6 m-4 max-w-lg shadow-md border border-gray-300 dark:bg-gray-800 dark:border-gray-600">
        <p className="text-lg font-bold">{header}</p>
        <p>
          <i className="fa-solid fa-check mr-2" />
          You must have <strong>Company</strong>, <strong>App Administrator</strong>, or <strong>App Member</strong> permissions in Recurly Engage.
        </p>
        <p>
          <i className="fa-solid fa-check mr-2" />
          At least one prompt and the necessary segments must already exist.
        </p>
        <p>
          <i className="fa-solid fa-exclamation-triangle mr-4" />
          Prompt must have at least 1 trigger in order to run.
        </p>
        <p>
          <i className="fa-solid fa-exclamation-triangle mr-4" />
          Ended prompts cannot be restarted, but can be cloned.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

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