---
title: Iterable
excerpt: >-
  Configuration guide for the Iterable connector in Recurly Engage—setup and
  supported messaging and lifecycle actions for cross-channel marketing.
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

Iterable is a powerful customer engagement platform that helps you segment audiences and automate personalized messaging. By integrating with Recurly Engage, you can trigger real-time lifecycle events, manage list memberships, and deploy targeted email campaigns directly through your recovery and engagement prompts.

# Definition

The Iterable connector integrates Recurly Engage with the Iterable API to track custom user behavior, manage audience segmentation via lists, and trigger immediate email communications during the customer journey.

# Key benefits

* **Behavioral Automation:** Post events to Iterable to trigger complex journeys or "Workflows" based on subscription status changes.
* **Dynamic Segmentation:** Automatically add users to specific "Win-back" or "Retention" lists when they interact with a prompt.
* **Instant Communication:** Send targeted campaign emails immediately to users (or specified alternative emails) to improve recovery rates.

# Key details

## Supported actions

Use these actions within prompt configurations (accept, secondary accept, etc.) to drive Iterable workflows:

<br />

<Table align={["left","left","left"]}>
  <thead>
    <tr>
      <th>
        Action
      </th>

      <th>
        Description
      </th>

      <th>
        API Method
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Post an event to Iterable
      </td>

      <td>
        Record a custom action (e.g., "Prompt Viewed") to a user's profile.
      </td>

      <td>
        `POST /api/events/track`
      </td>
    </tr>

    <tr>
      <td>
        Add user to Iterable list
      </td>

      <td>
        Subscribe the current user to a specific static list ID.
      </td>

      <td>
        `POST /api/lists/subscribe
                `
      </td>
    </tr>

    <tr>
      <td>
        Send campaign email to user
      </td>

      <td>
        Trigger a specific email campaign to the user's primary email.
      </td>

      <td>
        `POST /api/email/target`
      </td>
    </tr>

    <tr>
      <td>
        Send email to inputted email
      </td>

      <td>
        Send a campaign to an email address provided via a form input.
      </td>

      <td>
        `POST /api/email/target`
      </td>
    </tr>

    <tr>
      <td>
        Add user to list by email
      </td>

      <td>
        Add a user to a list using a manually mapped email address.
      </td>

      <td>
        `POST /api/lists/subscribe`
      </td>
    </tr>
  </tbody>
</Table>

## Integration 

To integrate Recurly Engage to Iterable, navigate to Settings > Integrations > Iterable. Use your iterable API key to connect to Recurly Engage. 

![](https://files.readme.io/779767b48a8ef353dfd317d14e6d942971ce1a19b769f97024bee940ada28cc9-image.png)

<br />
