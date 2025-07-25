---
title: Google tag manager
excerpt: >-
  Step-by-step instructions for deploying the Recurly Engage client SDK via
  Google Tag Manager.
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

<Embed url="https://www.loom.com/embed/9299487b721c4345a6326916ef68f287?sid=a721bfdd-f71a-431c-ae76-bd8f84bbbc82" href="https://www.loom.com/embed/9299487b721c4345a6326916ef68f287?sid=a721bfdd-f71a-431c-ae76-bd8f84bbbc82" typeOfEmbed="iframe" height="460px" width="100%" iframe="true" />

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

export const PrerequisitesLimitations = ({ header }) => {
  return (
    <div className="flex justify-start">
      <div className="rounded-md p-6 m-4 max-w-lg shadow-md border border-gray-300 dark:bg-gray-800 dark:border-gray-600">
        <p className="text-lg font-bold">{header}</p>
        <p>
          <i className="fa-solid fa-exclamation-triangle mr-4" />
          You must have publish permissions in the GTM container for your site.
        </p>
        <p>
          <i className="fa-solid fa-check mr-2" />
          Ensure you already created a Recurly Engage application and have its Application ID.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

The **Google Tag Manager integration** leverages a custom GTM template to inject the Recurly Engage SDK onto every page you specify, enabling tracking and branded checkout across your site.

# Key benefits

* **One-click setup**: Install the SDK entirely within GTM—no manual code edits.
* **Centralized management**: Control SDK triggers and updates from a single GTM interface.
* **Instant rollouts**: Publish changes immediately without redeploying your site.

# Key details

## Guide

1. **Log in to Google Tag Manager**: **Visit** [GTM](https://tagmanager.google.com/#/home) and open the container for your application.

2. **Select your container**: **Ensure** it matches the domain you registered in [app setup](setup-your-app).

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/2fe6657-Screenshot_2024-05-22_at_18.16.19.png" />

3. **Add a new tag**: In the left navigation, **click** **Tags** → **New**.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/ac79c42-Screenshot_2024-05-22_at_18.17.19.png" />

4. **Search for the Recurly Engage template**: In the **Choose tag type** pane, **use** the search bar (top right) and **enter** **Recurly Engage**.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/d98bcf3-image.png" />

5. **Get your Application ID**: Log in to your Recurly Engage console and navigate to **Settings > Application** to copy the ID.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/f048f16-Screenshot_2024-05-22_at_18.30.09.png" />

6. **Configure the tag**

* **Name** it **Recurly Engage Tag**
* **Paste** your **Application ID** into the template field
* Under **Triggering**, **choose** **All Pages**
* **Click** **Save**

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/1056d86-Screenshot_2024-05-22_at_18.33.53.png" />

7. **Publish your container**: **Click** **Submit** in the top right of GTM, **add** a descriptive version name (e.g., “Add Recurly Engage SDK”), and **hit** **Publish**.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/a0de186-Screenshot_2024-05-22_at_18.35.42.png" />

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/a0de186-Screenshot_2024-05-22_at_18.35.42.png" />