---
title: Freshdesk
excerpt: >-
  Configuration guide for the Freshdesk connector in Recurly Engage—API setup
  and supported support ticket and contact management actions.
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
          A Freshdesk account with API access and valid API key.
        </p>
        <p>
          <i className="fa-solid fa-exclamation-triangle mr-4" />
          Freshdesk plan must support API-based ticket and contact management.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

The **Freshdesk** connector lets you automate customer support workflows—creating tickets upon promo acceptance, updating ticket fields in bulk, and managing contacts—through prompt-driven 1-Click actions.

# Key benefits

* **Automated support**: Instantly generate support tickets from user interactions without manual intervention.
* **Bulk ticket updates**: Adjust priority, status, group, or responder for all tickets tied to a user with one action.
* **Contact lifecycle management**: Soft-delete or restore contacts and purge related tickets on demand.

# Key details

## Required settings

Under **Settings > Connectors > Freshdesk**, provide:

* **Domain**: Your Freshdesk subdomain (e.g., `yourcompany.freshdesk.com`).
* **API Key**: Your Freshdesk API token (see [How to find your API key](https://support.freshdesk.com/support/solutions/articles/215517-how-to-find-your-api-key)).

## Supported actions

Use these actions in prompt configurations to handle tickets and contacts:

| Action                                                          | Description                                                   | User Dependencies                 | Additional Instructions                       |
| :-------------------------------------------------------------- | :------------------------------------------------------------ | :-------------------------------- | :-------------------------------------------- |
| **Create support ticket with notification of offer acceptance** | Creates a ticket including user details and promo information | None                              | n/a                                           |
| **Update existing tickets priority**                            | Bulk-update priority for all tickets created by the user      | `freshdesk_id` or `email_address` | Configure new priority level on prompt screen |
| **Update existing tickets status**                              | Bulk-update status for all user tickets                       | `freshdesk_id` or `email_address` | Configure new status on prompt screen         |
| **Update existing tickets responder**                           | Bulk-update ticket responder for all user tickets             | `freshdesk_id` or `email_address` | Select responder on prompt screen             |
| **Update existing tickets group**                               | Bulk-update group assignment for all user tickets             | `freshdesk_id` or `email_address` | Select group on prompt screen                 |
| **Update existing tickets source**                              | Bulk-update ticket source for all user tickets                | `freshdesk_id` or `email_address` | Select source on prompt screen                |
| **Soft delete a contact**                                       | Mark the contact as deleted in Freshdesk                      | `freshdesk_id` or `email_address` | n/a                                           |
| **Restore a contact**                                           | Restore a previously soft-deleted contact                     | `freshdesk_id` or `email_address` | n/a                                           |
| **Delete all tickets**                                          | Permanently delete all tickets associated with the contact    | `freshdesk_id` or `email_address` | n/a                                           |
| **Spam all existing tickets**                                   | Mark all tickets created by the user as spam                  | `freshdesk_id` or `email_address` | n/a                                           |

## Additional resources

* Retrieve your Freshdesk API Key: [How to find your API key](https://support.freshdesk.com/support/solutions/articles/215517-how-to-find-your-api-key)