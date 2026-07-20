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

<Embed title="" typeOfEmbed="iframe" url="https://www.loom.com/embed/936c535cfaf74ba2afcd89474b8a9d9b?sid=faff98b4-6cde-49fb-b205-f1df5dac4075" height="480px" width="100%" href="https://www.loom.com/embed/936c535cfaf74ba2afcd89474b8a9d9b?sid=faff98b4-6cde-49fb-b205-f1df5dac4075" />

### Required plan

This feature **may not be included** in the all plans. If you are interested, please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) to discuss upgrade options.

export const PrerequisitesLimitations = ({ header }) => {
  return (
    <div className="flex justify-start">
      <div className="rounded-md p-6 m-4 max-w-lg shadow-md border border-gray-300 dark:bg-gray-800 dark:border-gray-600">
        <p className="text-lg font-bold">{header}</p>
        <p>
          <i className="fa-solid fa-check mr-2"></i>
          You must have <strong>Company</strong>, <strong>App Administrator</strong>, or <strong>App Member</strong> permissions in Recurly Engage.
        </p>
        <p>
          <i className="fa-solid fa-exclamation-triangle mr-4"></i>
          Guide type is fixed on creation and cannot be changed later.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

A **guide** binds multiple prompts into a controlled flow, enabling sequential, branched, or conditional delivery based on user behavior and scheduling.


<Image src="https://files.readme.io/bd78e59-image.png" align="center" width="80% " border={true} />


# Key benefits

- **Structured interactions**: Deliver step-by-step experiences to users.
- **Dynamic branching**: Use survey logic or conditions to tailor the flow.
- **Cross-device continuity**: Maintain guide state as users switch devices.

# Key details

## Guide

1. **Go** to **Guides > New Guide**.
2. **Select a Guide Type**
3. **See below for details on each guide type**

## Wizard

Supported on Web and HTML5-based smart TVs.

Wizard guides present prompts immediately in the defined order within a single session. Only the first prompt requires a trigger; subsequent prompts fire automatically upon interaction with the previous prompt.

Items within a guide inherit the guide’s configurations: [Limits](limits-1), [Segments](segments), [Schedule](schedule-1).


<Image src="https://files.readme.io/8a86d2f-image.png" align="center" width="80% " border={true} />


## Survey

Supported on Web and HTML5-based smart TVs.

Survey guides collect user input through branching prompts. Subsequent prompts are shown based on the user’s selection in earlier steps.


<Image src="https://files.readme.io/e09a8bd-image.png" align="center" width="80% " border={true} />


## Journey

Supported on all devices.

Journey guides onboard new users or deliver feature tours over time. You can configure them to show only unseen items or enforce a strict order, triggering based on visits, interactions, or time delays.


<Image src="https://files.readme.io/9a5b99e-image.png" align="center" width="80% " border={true} />


Items within a guide can be connected based on:

- **Interactions**: Show an item only if another guide item was seen, accepted, declined, or dismissed.
- **Next Visit**: Trigger the next item on the user’s subsequent session.
- **Days**: Delay the next item by a set number of days across sessions.
- **Minutes**: Delay the next item by minutes within the same session.

## Triggered

Supported on all devices.

Triggered guides reinforce messages by delivering one of several prompts based on user eligibility and predefined conditions. You can prevent users from receiving multiple similar items by setting exclusion rules across guide items.


<Image src="https://files.readme.io/831f597-image.png" align="center" border={true} />


## Tours

Supported on Web only.

Tour guides walk subscribers through your site with a sequence of floating tooltips, each anchored to a specific element on the page. Use them for onboarding, feature discovery, and guided navigation — configured natively in Pulse, with steps that can span multiple pages. [Learn how to build a Tour](/recurly-engage/docs/tours).


<Image src="https://files.readme.io/e1674c35bce8685ff830b9a209f8c9821aa3fa46cb207188d647b36445266bda-Screenshot_2026-07-20_at_1.23.50_PM.png" align="center" width="500px" />


***

##

<br />
