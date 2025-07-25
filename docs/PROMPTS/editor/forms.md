---
title: Forms
excerpt: >-
  How to add input fields or survey options to your prompts and handle submitted
  values in actions.
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

Enhance your prompts with up to three input fields or five survey options to collect data from users directly within the in-app message.

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
          Maximum of three input fields per prompt, or up to five survey choices.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

**Forms** in Recurly Engage prompts allow you to gather user input—text entries or survey selections—raising engagement and capturing valuable feedback.

# Key benefits

* **Direct feedback**: Collect emails, names, or other details without redirecting users.
* **Quick surveys**: Gather opinions or preferences in-context.
* **Actionable data**: Pass form responses into API, connector, or website actions for immediate processing.

# Key details

## Adding form fields to a prompt

1. **Open** **Prompts** and **select** the prompt you wish to enhance.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/ce4a893-image.png" />

2. **Click** **Edit prompt design** to launch the editor.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/5477d38-image.png" />

### Adding input fields

1. In the **Forms** panel, **enable** **Inputs**.
2. **Configure** each input field (label, placeholder, validation). **Preview** updates live.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/70ea517-image.png" />

### Adding a survey

1. In the **Forms** panel, **enable** **Survey**.
2. **Define** up to five survey options with labels and values. Preview updates live.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/bb79ff4-image.png" />

## Handling form submissions

Form inputs and survey selections can trigger downstream actions:

* **Connector Actions**: Send data to services like SendGrid, Braze, Freshdesk, or Iterable.
* **API Actions**: Call your custom APIs with the form data.
* **Website Actions**: Execute custom JavaScript; submitted values are available in the `args` object. For example:

```javascript
// args example when user submits an email field
{
  promoInput1Value: "john@smith.com"
}
```

**Example use case**: Capture an email via an input field, then use a SendGrid connector action to send a templated email to that address. [SendGrid connector details](sendgrid)

When you’re done configuring fields, click **Save & Exit** to apply your changes and deploy the updated prompt.