---
title: Actions
excerpt: >-
  Overview of prompt actions—triggered events tied to user interactions,
  built-in connectors, and custom integrations in Recurly Engage.
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
          For connector actions, you must supply third-party credentials.
        </p>
        <p>
          <i className="fa-solid fa-exclamation-triangle mr-4" />
          Website actions require custom JavaScript knowledge.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

An **action** is a task executed when a user interacts with a prompt (Accept, Decline, Secondary Accept, Dismiss, or Timeout), enabling personalized flows and integrations.

# Key benefits

* **Custom workflows**: Chain multiple actions—redirects, emails, API calls—on a single interaction.
* **Seamless integrations**: Connect to billing, marketing, or support systems with prebuilt connectors.
* **Immediate responses**: Trigger website JS actions for in-app behavior without page reloads.

# Key details

## User interactions

Actions can be tied to any of these five prompt events:

1. **Accept**: User clicks the primary button.
2. **Secondary Accept**: User clicks the secondary button (if configured).
3. **Decline**: User clicks a Decline option.
4. **Dismiss**: User closes the prompt via the X icon.
5. **Timeout**: Prompt auto-closes after a timer.

Use the two buttons (Accept/Decline) for complementary actions, such as “Sign me up” on Accept and “Add to watchlist” on Decline.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/dbba980-image.png" />

<br />

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/ae7b5ec-image.png" />

***

## Configure actions on a prompt

One or more actions can be attached to each interaction. For example, you might apply a discount via API and then send a confirmation email upon Accept.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/48dd9f9-image.png" />

### Built-in actions

Available by default on every prompt:

* **Send an email**: Dispatch an email to a specified address on Accept.
* **Send an SMS**: Send an SMS to a specified number on Accept.
* **Redirect the user**: Navigate the user to a URL when they accept.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/48dd9f9-image.png" />

### Connector actions

Integrate with external systems—billing, CRM, support—using prebuilt connectors. Supply credentials in **Settings > Connectors** before use.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/87d7647-image.png" />

#### Step-by-step: Adding a connector action

1. **Open** your prompt under **Prompts**.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/aace646-image.png" />

2. **Click** **Add action** next to the desired interaction (e.g., Accept).

<Image align="center" width="80% " src="https://files.readme.io/d186553-image.png" />

3. In the action modal, **select** **Connector Actions**, **choose** a connector (e.g., Zuora) and action (e.g., Subscribe a user to a plan), **set** **Error Behavior** (Stop or Continue), then **click** **Add Action**.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/4b6e880-image.png" />

4. **Reorder** actions by dragging; **configure** multiple actions per interaction as needed.

<Image align="center" width="80% " src="https://files.readme.io/09969e8-image.png" />

> **Error behavior**:
>
> * **Stop**: Halt downstream actions if this action fails.
> * **Continue**: Proceed to next actions even if this one errors.

***

## Custom actions

Build your own actions for advanced scenarios:

1. **Connector Actions**: Integrate additional business systems. [More info](connector-actions)
2. **API Actions**: Call your custom endpoints. [More info](api-actions)
3. **Website Actions**: Run custom JavaScript in the user’s browser. [More info](website-actions)

For complex setups—like “1-click save offers”—our technical team can assist. Reach out on Slack for hands-on support.