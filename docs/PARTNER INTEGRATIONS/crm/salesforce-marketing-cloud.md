---
title: Salesforce
excerpt: >-
  Configuration guide for the Salesforce connector in Recurly Engage—setup,
  credentials, and supported actions for Support Cloud and Marketing Cloud.
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

This feature is an add on and can be purchased for any Recurly Engage subscription plan.

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
          Active Salesforce Support Cloud and/or Marketing Cloud licenses.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

The **Salesforce** connector streams Recurly Engage prompt events and actions into Salesforce, allowing you to create cases, post feed items, send Marketing Cloud emails, and manage subscriber lists directly from prompts.

# Key benefits

* **Real-time case creation**: Automatically generate support cases from user interactions.
* **Feed updates**: Log offer acceptances to existing case feeds for full context.
* **Marketing Cloud sends**: Trigger personalized email sends and list subscriptions without leaving the prompt UI.

# Key details

## Support cloud credentials

Under **Settings → Connectors → Salesforce**, provide:

* **Username**
* **Password**
* **Security Token**
* **Client ID**
* **Client Secret**

## Marketing cloud credentials

Provide:

* **Client ID**
* **Client Secret**
* **From Email Address**
* **Base URL**
* **Auth Base URL**
* **SOAP Base URL**

## Supported actions

Use these actions in your prompt configurations to drive Salesforce workflows:

| Action                                                        | Description                                                                        | User Dependencies                  | Additional Instructions                                                                        | Form Inputs |
| ------------------------------------------------------------- | ---------------------------------------------------------------------------------- | ---------------------------------- | ---------------------------------------------------------------------------------------------- | ----------- |
| **Create a Case (Support)**                                   | Creates a support case in Salesforce with user and prompt details                  | n/a                                | n/a                                                                                            | n/a         |
| **Post offer acceptance to feed of existing cases (Support)** | Adds a feed item to all cases associated with the user, detailing offer acceptance | `salesforce_id` or `email_address` | n/a                                                                                            | n/a         |
| **Triggered Send (Marketing Cloud)**                          | Sends a templated email to the user via Marketing Cloud                            | `email_address` (optional)         | Select an email template in the prompt editor; configure dynamic templates in Marketing Cloud. | optional    |
| **Add Subscriber to List (Marketing Cloud)**                  | Adds an existing subscriber to a specified list                                    | n/a                                | Select the list in the prompt editor; ensure lists exist in Marketing Cloud dashboard.         | n/a         |
| **Add User to List with Form Input (Marketing Cloud)**        | Creates a subscriber based on prompt input and adds them to a specified list       | n/a                                | Select the list in the prompt editor; configure form input field for email address.            | required    |

## Installing Journey Builder Activity

1. In Marketing Cloud Setup, navigate to **Apps → Installed Packages**, then click **New**.
2. Enter **Name**: `Recurly Engage`, then click **Save**.
3. Under **Components**, click **Add Component**, choose **Journey Builder Activity**, and click **Next**.
4. Provide:

   * **Name**: `Recurly Engage`
   * **Category**: `Messages`
   * **Endpoint URL**: `https://jbuilder.recurlyengage.com/<appid>/` (find App ID under **Settings → Application**).
5. Save the activity. Recurly Engage will now appear as a Message activity in Journey Builder.

## Additional Information

* [Salesforce Credentials reference](https://developer.salesforce.com/forums/?id=906F0000000AfcgIAC)
* [Finding Client ID and Secret](https://salesforce.stackexchange.com/questions/40346/where-do-i-find-the-client-id-and-client-secret-of-an-existing-connected-app/224659#224659)