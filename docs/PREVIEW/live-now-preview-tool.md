---
title: Live Now - Preview tool
excerpt: >-
  Overview of the Preview Tool (Live Now) in Recurly Engage for visual editing
  and validation of prompts, segments, and trackers directly on your website.
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
          <i className="fa-solid fa-exclamation-triangle mr-4" />
          Ensure your site is loaded with the Recurly Engage JS snippet with Preview enabled.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

The **Preview Tool** is a point‑and‑click interface that overlays your live site, allowing you to manage and debug Recurly Engage elements—segments, trackers, prompts, and inline placements—in real time.

# Key benefits

* **Instant validation**: See segment membership, trait values, and inline prompt placements live.
* **No-code editing**: Add trackers or inline prompts by clicking elements on the page.
* **Deep inspection**: Use X‑Ray to highlight prompts, trackers, and view stats directly on the site.

# Key details

With Live Now, you can:

* Impersonate individual users to test personalized flows.
* View which segments a user matches.
* Preview any prompt or guide in context.
* Add usage trackers and triggers on the fly.
* Inspect inline prompts: check stats and placement with X‑Ray.
* Visualize and override user traits in real time.
* Seamlessly insert inline prompts without coding.

***

## Using the preview tool

Before you begin, ensure you have created at least one segment ([Create a segment](segments)) and one inline prompt ([Create an inline](inlines)). These assets will serve as the basis for your in-page testing.

The Preview Tool injects a toolbar into your site. Its core workflow enables you to add inline prompts anywhere on the page with a simple click-and-select action.

<Embed url="https://www.loom.com/embed/df4eeff2622046f7a939e3cf361513fb" href="https://www.loom.com/embed/df4eeff2622046f7a939e3cf361513fb" typeOfEmbed="iframe" height="480px" width="100%" iframe="true" />

### X‑Ray for inline prompts

When your page contains many Recurly Engage components, use **X‑Ray** mode to highlight all prompts and trackers. X‑Ray overlays outlines and metrics, helping you locate items and understand their live performance.

<Embed url="https://www.loom.com/embed/e49c3ffac05c478e9d82a01027fa5384" href="https://www.loom.com/embed/e49c3ffac05c478e9d82a01027fa5384" typeOfEmbed="iframe" height="480px" width="100%" iframe="true" />

Use these capabilities to test, validate, and fine‑tune your Recurly Engage setup before pushing changes live to your entire audience.