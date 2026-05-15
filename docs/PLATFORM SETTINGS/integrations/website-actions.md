---
title: Website
excerpt: >-
  How to configure and use Website Actions within Recurly Engage, including
  adding simple built-in actions and custom JavaScript code.
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
          You must have <strong>Company</strong> or <strong>App Administrator</strong> permissions in Recurly Engage.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

Website actions allow the Redfast tool to call custom client side code, optionally passing information from form inputs. This page describes how to set up and use website actions.

### Add a simple action

Several simple actions such as redirecting to a new URL or opening a URL in a new tab are readily available. For example, to add a website action that opens a new tab with the specified URL:

1. From the prompt detail page, add a new website action
2. Select ‘Open URL on New Tab’
3. Click Add action
4. Click on the edit / pencil icon
5. Add a new argument with key=url and value equal to the link you want to take the user to

### Add custom Javascript code

1. Visit Settings → Actions → Website Actions

<Image align="center" border={true} width="% " src="https://files.readme.io/9e361b2-Screenshot_2024-04-30_at_22.47.54.png" className="border" />

2. Create a website action. Specify the name of the action and write the code. See [form inputs](https://dash.readme.com/project/redfast/v100.7/docs/forms) for more information on accessing user input.

<Image align="center" border={true} src="https://files.readme.io/2272dcc-Screenshot_2024-04-30_at_22.51.56.png" className="border" />

3. Save the changes

<Image align="center" border={true} src="https://files.readme.io/a30b0cb-Screenshot_2024-04-30_at_22.53.42.png" className="border" />

4. Go to Prompts and select your prompt

<Image align="center" border={true} src="https://files.readme.io/6354038-Screenshot_2024-04-30_at_22.55.04.png" className="border" />

5. Add the website action

<Image align="center" border={true} src="https://files.readme.io/1928bd0-Screenshot_2024-05-01_at_21.30.27.png" className="border" />

<Image align="center" border={true} src="https://files.readme.io/921f4c4-Screenshot_2024-05-01_at_21.31.29.png" className="border" />
