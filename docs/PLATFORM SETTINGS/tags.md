---
title: Tags
excerpt: >-
  Manage and report on groups of prompts using tags, with combined analytics and
  frequency controls.
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

Tags let you categorize prompts by campaigns, use cases, markets, or any custom criteria. They enable better organization, consolidated reporting, and the ability to cap how often related prompts are shown.

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

export const PrerequisitesLimitations = ({ header }) => {
  return (
    <div className="flex justify-start">
      <div className="rounded-md p-6 m-4 max-w-lg shadow-md border border-gray-300 dark:bg-gray-800 dark:border-gray-600">
        <p className="text-lg font-bold">{header}</p>
        <p>
          <i className="fa-solid fa-check mr-2" />
          You must have <strong>Company</strong> or <strong>App Administrator</strong> permissions in Recurly Engage.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

A **tag** is a label you assign to one or more prompts to group them for filtering, reporting, and frequency capping.

# Key benefits

* **Organize prompts**: Group prompts by use case, campaign, or market for easier management.
* **Unified analytics**: View combined performance metrics (impressions, conversions, CTR) across all prompts sharing a tag.
* **Frequency control**: Set per-tag frequency caps to limit how often users see any prompts with that tag.

# Key details

## Create and manage tags

App admins can create default tags at the application level under **Settings → Tags**, or add new tags on the fly when editing a prompt.

<Image align="center" className="border" border={true} src="https://files.readme.io/4a443a46f12b41134aed1a8ccdb932aba86cbf2b20f37945c75d01712dd475da-image.png" />

## Assign tags to prompts

When creating or editing a prompt, select existing tags or type to add a new one under **Details → Tags**.

<Image align="center" className="border" border={true} src="https://files.readme.io/a248fe5e233d5c15ec140885651bc2a1ef2e0e33dceee6cbb084ce3cc6a5ae9c-image.png" />

## Filter and report by tag

Go to **Prompts**, click the filter icon in the **Tags** column, and choose a tag to see all associated prompts and their combined metrics.

<Image align="center" className="border" border={true} src="https://files.readme.io/ffa89a2acdc30406f18ce2a9655dac93d26eda3ca5e15a6e29ab57bf48213ba2-image.png" />

## Frequency capping by tag

To limit how often prompts with a specific tag appear to users:

1. Navigate to **Settings → Tags**.
2. Click the edit (pencil) icon for your tag.
3. Under **Frequency Cap**, select **Custom**, configure the limit, and submit.

<Image align="center" className="border" border={true} src="https://files.readme.io/dced510deb4e280058e63236c304795fd959ffb8f7c6a5fafd01bdb7a55f9636-Frequency_cap_by_tag.png" />