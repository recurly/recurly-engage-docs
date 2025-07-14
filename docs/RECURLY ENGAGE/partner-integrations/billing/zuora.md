---
title: Zuora
excerpt: >-
  Configuration guide for the Zuora connector in Recurly Engage, including
  setup, data sync, and 1-Click subscription actions.
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

* Company or App Administrator permissions in Recurly Engage.
* A Zuora tenant with API access credentials (Client ID and Client Secret).

# Definition

The Zuora connector synchronizes subscription traits and product rate plans from Zuora into Recurly Engage, allowing you to attach 1-Click actions to prompt interactions for seamless subscription management.

# Key benefits

* **Real-time subscription control**: Add, remove, or modify rate plans within your prompts.
* **Lifecycle management**: Suspend, resume, or cancel subscriptions via in-app actions.
* **Automated data flows**: Keep Recurly Engage updated with the latest account and subscription balances.

# Key details

## Required settings

Under **Settings > Connectors**, configure your Zuora connector by providing:

* **API URL**: Your Zuora REST API endpoint.
* **Client ID** and **Client Secret**: OAuth credentials for API authentication.

## Data integration

### Automated data sync

Coordinate with Customer Success to schedule daily imports of the following Zuora account and subscription traits into Recurly Engage via AWS S3 or your preferred CSV pipeline:

| Trait Name                | Values                                                                               |
| ------------------------- | ------------------------------------------------------------------------------------ |
| `account_number`          | Zuora account number                                                                 |
| `status`                  | `Active`, `Canceled`, `Draft`                                                        |
| `payment_term`            | Configured payment term (e.g., Net 30)                                               |
| `balance`                 | Outstanding account balance                                                          |
| `total_invoice_balance`   | Total invoiced balance                                                               |
| `credit_balance`          | Available credit balance                                                             |
| `contracted_mrr`          | Contracted monthly recurring revenue                                                 |
| `term_type`               | `TERMED`, `EVERGREEN`                                                                |
| `subscription_start_date` | Date the subscription term starts                                                    |
| `subscription_end_date`   | Date the subscription term ends                                                      |
| `term_start_date`         | Start date of the current term (may differ from subscription start if renewed)       |
| `term_end_date`           | End date of the current term (null or cancellation date for evergreen subscriptions) |
| `auto_renew`              | `true` or `false`                                                                    |
| `rate_plan_name`          | Name of the most recent rate plan                                                    |

## 1-click actions

Once your connector is activated and rate plans have synchronized, you can configure these 1-Click actions within your prompt editor. The **account\_number** trait must be present on user records to target actions.

| Action                   | Description                                        | Additional Instructions                                                                                                     |
| ------------------------ | -------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| **Add Plan**             | Add a specified rate plan to an account            | Select the desired **Product Rate Plan** from the dropdown                                                                  |
| **Remove Plan**          | Remove a specified rate plan from an account       | Select the **Product Rate Plan** to remove from the dropdown                                                                |
| **Cancel Subscription**  | Cancel the active subscription                     | Choose a **Cancellation Policy** (EndOfCurrentTerm, EndOfLastInvoicePeriod, SpecificDate) and **Apply Credit** (true/false) |
| **Suspend Subscription** | Pause an active subscription                       | Specify **Suspend Policy** (Today, EndOfLastInvoicePeriod, SpecificDate, FixedPeriodsFromToday)                             |
| **Resume Subscription**  | Reactivate a suspended subscription                | Select **Resume Policy** (Today, FixedPeriodsFromSuspendDate, FixedPeriodsFromToday, SpecificDate)                          |
| **Change Auto Renewal**  | Toggle auto-renewal setting                        | Choose **AutoRenew** (`true` or `false`)                                                                                    |
| **Create Subscription**  | Create a new subscription with specified rate plan | Provide **contractEffectiveDate**, **renewalTerm**, **Rate Plan**, and **Term Type**                                        |

## Guide: Configuring a 1-click Zuora action

1. In your prompt editor, **click** **Add Action**.
2. **Choose** **Zuora** as the connector and select the desired action (e.g., **Add Plan**).
3. **Pick** the **Product Rate Plan** or policy settings from the dropdown.
4. **Save** and **publish** your prompt.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/f6b632e-Zuora_action.png" />

## Additional references

* [Zuora API Reference](https://www.zuora.com/developer/api-reference/)