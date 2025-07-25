---
title: Create an experiment
excerpt: >-
  Step-by-step guide to creating and running A/B experiments on your prompts in
  Recurly Engage.
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

This feature or setting is available to all customers on any Recurly Engage subscription plans.

-export const PrerequisitesLimitations = (\{ header }) => \{
&#x20; return (
&#x20;   \<div className="flex justify-start">
&#x20;     \<div className="rounded-md p-6 m-4 max-w-lg shadow-md border border-gray-300 dark:bg-gray-800 dark:border-gray-600">
&#x20;       \<p className="text-lg font-bold">\{header}\</p>
&#x20;       \<p>
&#x20;         \<i className="fa-solid fa-check mr-2" />
&#x20;         You must have \<strong>Company\</strong> or \<strong>App Administrator\</strong> permissions in Recurly Engage.
&#x20;       \</p>
&#x20;       \<p>
&#x20;         \<i className="fa-solid fa-exclamation-triangle mr-4" />
&#x20;         At least one prompt must exist in \<strong>draft\</strong> or \<strong>review\</strong> status before creating an experiment.
&#x20;       \</p>
&#x20;     \</div>
&#x20;   \</div>
&#x20; );
};

\<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

An **experiment** runs multiple versions (variations) of a prompt against each other—optionally including a control group—to measure performance based on custom goals and decide which version to deploy.

# Key benefits

* **Data-driven decisions**: Use real user interactions to choose the most effective prompt variant.
* **Controlled testing**: Isolate single changes (copy, design, trigger) to understand their impact.
* **Seamless rollout**: Promote the winning variation automatically when the experiment completes.

# Key details

## Guide

Experiments follow these steps:

### (Optional) Add a custom goal

Define what success looks like—e.g., a click or purchase—before creating variations.

1. In Recurly Engage, **go** to **Settings > Usage Tracker** and **add** a new tracker.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/92f9bc4-image.png" />

<br />

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/0aa0cf3-image.png" />

2. Return to your prompt and attach the custom goal under **Goals**.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/b7ac98d-image.png" />

<br />

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/ae3bdf1-image.png" />

<br />

### Create the experiment

1. Open your prompt and click **+ New experiment**.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/26772c2-image.png" />

2. Give your experiment a clear name—see the [overview on experiments](experiments-1) for best practices.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/d785a04-Screenshot_2024-04-24_at_19.03.27.png" />

### Configure variations

**Default setup**: By default, your experiment contains the **Original** prompt. If you added a custom goal, you may also include a **Control** group to measure the impact of showing vs. hiding the prompt.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/743630a-image.png" />

**Add a variation**: Click **Add variation**, name it to reflect the change (e.g., “New headline”), and modify one or more aspects—text, design, triggers, or actions.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/bc5027f-Screenshot_2024-04-24_at_19.17.57.png" />

**Use** the editor to scroll down and adjust settings as needed:

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/c7be6b1-image.png" />

### Allocate traffic

Set the percentage of users who see each variation—ensure that total equals 100%.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/f175e0f-image.png" />

### Launch and monitor

1. Click **Start experiment** and confirm.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/db1802e-image.png" />

2. Monitor performance in real time—click-through and conversion rates update within minutes, depending on traffic.

3. When ready, click **Use This** on the winning variation to replace the control and end the experiment.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/5f30ea5-image.png" />

That’s it—your experiment is live, and you can review results to make data-driven optimizations to your prompts.