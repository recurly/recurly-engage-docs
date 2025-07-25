---
title: Braze
excerpt: >-
  Configuration guide for the Braze connector in Recurly Engage—API setup and
  supported user management actions.
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
          <strong>Company</strong> or <strong>App Administrator</strong> permissions in Recurly Engage.
        </p>
        <p>
          <i className="fa-solid fa-check mr-2" />
          A Braze account with REST API access enabled (App Group REST API Key).
        </p>
        <p>
          <i className="fa-solid fa-exclamation-triangle mr-4" />
          Ensure your Braze instance’s Base URL and API Key are available.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

The **Braze** connector uses your Braze REST API credentials to add or update user records—mapping email addresses and optional aliases—when users interact with prompts.

# Key benefits

* **Synchronized user profiles**: Automatically enroll or update users in Braze for downstream messaging.
* **Personalized engagement**: Use prompt events to trigger Braze campaigns and segmentation.
* **Centralized setup**: Manage Braze credentials and actions within the Recurly Engage console.

# Key details

## Required settings

Under **Settings → Connectors → Braze**, provide:

* **Base URL**: Your Braze REST API endpoint (e.g., `https://rest.iad-01.braze.com`).
* **API Key**: Your App Group REST API Key (see [Braze API Reference](https://www.braze.com/docs/api/basics/#app-group-rest-api-keys)).

## Supported actions

Use these actions within prompt configurations to manage Braze user profiles:

| Action                            | Description                                                          | User Dependencies | Additional Instructions                    | Form Inputs |
| --------------------------------- | -------------------------------------------------------------------- | ----------------- | ------------------------------------------ | ----------- |
| **Add a user with email address** | Adds a user record with an email address and optional alias to Braze | None              | Enter the alias label in the prompt editor | required    |

Attach this action to a prompt interaction (e.g., Accept) to automatically push the user’s email and alias to Braze when they engage with your message.