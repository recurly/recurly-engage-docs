---
title: Dynamic variables
excerpt: >-
  Configure and use dynamic variables (custom traits) within your prompts to
  deliver personalized messaging.
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
          <i className="fa-solid fa-exclamation-triangle mr-4" />
          Ensure custom traits are configured in <a className="text-blue-500! dark:text-blue-300!" href="user-traits">User Traits</a>.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

**Dynamic variables** pull values from your configured custom traits and insert them into prompt copy, allowing per-user personalization without creating separate prompts.

# Key benefits

* **Personalized greetings**: Address customers by name or status (e.g., “Hello Steve”).
* **Contextual details**: Show member tenure or plan info (e.g., “Member since January 2018”).
* **Flexible use**: Insert any trait multiple times in titles or messages for maximum relevance.

# Key details

1. Dynamic variables use your custom traits to fill prompt fields at render time.
2. Add variables via the **+ Insert Variable** link when designing a prompt.
3. Supported in both **Title** and **Message** fields—use as many as needed.

## Guide

1. **Navigate** to **Prompts** and select the prompt you wish to personalize.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/309a30e-image.png" />

2. **Click** **Edit prompt design** to open the editor.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/f2e4389-image.png" />

3. **Click** the **Insert variable** link near the Title or Message field.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/7915a13-image.png" />

4. **Choose** **Dynamic variables** from the options.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/9f84933-image.png" />

5. **Open** the dropdown and select the desired trait variable.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/f845d05-image.png" />

6. **Click** **Insert variable** to add it to your copy.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/69cd32e-image.png" />

7. **Verify** placement in the Title or Message, then **click** **Save** to apply your changes.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/3e79ce8-image.png" />