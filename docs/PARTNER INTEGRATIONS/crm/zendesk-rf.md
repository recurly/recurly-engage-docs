---
title: Zendesk
excerpt: >-
  Configuration guide for the Recurly Engage Zendesk integration, enabling
  support workflows to be triggered directly from prompts.
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

### Prerequisites & limitations

* You must have **Company**, **App Administrator**, or **App Member** permissions in Recurly Engage.
* Your Zendesk account must support API token authentication and you must have an admin-generated token.

# Definition

The Zendesk integration allows Recurly Engage prompts to perform support actions—like creating tickets, assigning agents, and managing user status—directly in your Zendesk instance.

# Key benefits

* **Automate ticket creation**: Instantly log support tickets when users interact with prompts.
* **Streamline support workflows**: Assign, prioritize, or suspend users without leaving your app’s interface.
* **Improve response times**: Reduce manual hand-offs by handling common support tasks programmatically.

# Key details

## Required settings

* Domain (e.g., `yourcompany.zendesk.com`)
* API Key (aka API Token)
* Username (Zendesk account email)

## Supported actions

| Action                                                      | Description                                                         | User Dependencies               | Additional Instructions                                                                                     |
| ----------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| Create support ticket with notification of offer acceptance | Creates a support ticket with information about the user and prompt | n/a                             | —                                                                                                           |
| Set priority of all existing tickets                        | Sets priority attribute for all tickets created by the user         | `zendesk_id` or `email_address` | Select the priority level on the prompt screen                                                              |
| Assign all existing tickets to a specific agent             | Assigns all tickets created by the user to one agent                | `zendesk_id` or `email_address` | Select the agent on the prompt screen. Manage agents under **Admin > People > Agents** in Zendesk dashboard |
| Suspend user                                                | Sets the user to suspended state                                    | `zendesk_id` or `email_address` | —                                                                                                           |
| Restore suspended user                                      | Restores the user from suspended state                              | `zendesk_id` or `email_address` | —                                                                                                           |
| Assign all existing tickets to a group                      | Assigns all tickets created by the user to a group                  | `zendesk_id` or `email_address` | Select the group on the prompt screen. Manage groups under **Admin > People > Groups** in Zendesk dashboard |
| Delete all tickets                                          | Deletes all tickets created by the user                             | `zendesk_id` or `email_address` | —                                                                                                           |
| Set status of all existing tickets                          | Sets status of all tickets created by the user                      | `zendesk_id` or `email_address` | Select the status on the prompt screen                                                                      |
| Delete and spam all existing tickets                        | Marks all tickets created by the user as spam                       | `zendesk_id` or `email_address` | —                                                                                                           |

## Additional resources

[Zendesk API token](https://support.zendesk.com/hc/en-us/articles/226022787-Generating-a-new-API-token-)