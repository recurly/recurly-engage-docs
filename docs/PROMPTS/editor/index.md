---
title: Prompt editor
excerpt: >-
  Overview of the design editor for creating and customizing prompts in Recurly
  Engage.
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
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

The **Editor** is the interactive designer within the Prompts console that lets you customize the look, feel, and interactions of your in-app messages in real time.

<Image align="center" className="border" border={true} src="https://files.readme.io/38b466a-image.png" />

# Key benefits

* **Live preview**: See your design changes reflected immediately in the canvas above.
* **Rich interactivity**: Add buttons, forms, surveys, or custom HTML to create engaging experiences.
* **Cross-functional collaboration**: Fine-tune visuals, copy, and behaviors with designers, developers, and marketers all in one place.

# Key details

* Adjust styling options (colors, fonts, spacing) and upload background images or videos.
* Configure up to three CTA buttons with custom labels, actions, and deep links.
* Add input fields or survey questions to collect user feedback directly in-app.
* Toggle close icons, delay timers, and animation settings for optimal user experience.

Feel free to tinker with any setting in the sidebar and watch updates live in the preview panel. When ready, click **Save & Exit** to apply your changes.

<Image align="center" className="border" border={true} src="https://files.readme.io/d6c8f68-image.png" />

While creating prompts is intuitive, finalizing content and design often involves input from designers, copywriters, and product teams—use this editor as your single source of truth.