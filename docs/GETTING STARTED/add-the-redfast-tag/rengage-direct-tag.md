---
title: Direct tag management
excerpt: >-
  Instructions for embedding the Recurly Engage JavaScript SDK directly into
  your site’s HTML.
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

This page shows you how to add the Recurly Engage SDK to your application by inserting the script snippet into your HTML. Once complete, Recurly Engage will begin syncing customer data for personalized experiences.

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

export const PrerequisitesLimitations = ({ header }) => {
  return (
    <div className="flex justify-start">
      <div className="rounded-md p-6 m-4 max-w-lg shadow-md border border-gray-300 dark:bg-gray-800 dark:border-gray-600">
        <p className="text-lg font-bold">{header}</p>
        <p>
          <i className="fa-solid fa-check mr-2" />
          You need <strong>Administrator</strong> access to your Recurly Engage console.
        </p>
        <p>
          <i className="fa-solid fa-exclamation-triangle mr-4" />
          Ensure you can edit and redeploy your site’s HTML files.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

The **Direct tag integration** lets you manually paste the Recurly Engage JavaScript snippet into your site’s HTML, enabling Engage features without using a tag manager.

# Key benefits

* **Full control**: Embed the script exactly where you need it in your page lifecycle.
* **No external tools**: Skip tag managers and deploy directly in your codebase.
* **Performance-safe**: Use the `defer` attribute to prevent blocking page rendering.

# Key details

Follow these steps to add the Recurly Engage SDK directly:

1. **Log in to Recurly Engage and select your application**: **Make sure** you’re in the correct app context before retrieving your snippet.

2. **Retrieve the JavaScript snippet**: In the Engage console, **navigate** to **Settings > Usage Tracking**.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/2c35d83-Screenshot_2024-05-23_at_16.23.58.png" />

3. **Copy the code snippet**: **Select** and **copy** the entire `<script>` block provided.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/9e21b53-Screenshot_2024-05-23_at_16.25.30.png" />

4. **Locate your root HTML file**: Open your project and find the main HTML file (commonly named `index.html`) where other scripts load.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/3520de0-js-tag-direct-3.png" />

5. **Paste the snippet above the closing`</head>` tag**: **Insert** the `<script>` block right before `</head>`. You may add `defer` if desired; it won’t affect the SDK’s operation.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/5bffbbf-js-tag-direct-4.png" />

6. **Save and deploy your project**: **Commit** your changes, **deploy** your site, and **confirm** the SDK loads on page view.