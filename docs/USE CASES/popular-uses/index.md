---
title: Popular use cases
excerpt: >-
  Overview of the most popular use cases for Recurly Engage prompts across the
  customer lifecycle.
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

From acquisition to churn prevention, Recurly Engage supports a variety of proven engagement patterns to drive conversions, increase retention, and maximize customer value.

export const PrerequisitesLimitations = ({ header }) => {
  return (
    <div className="flex justify-start">
      <div className="rounded-md p-6 m-4 max-w-lg shadow-md border border-gray-300 dark:bg-gray-800 dark:border-gray-600">
        <p className="text-lg font-bold">{header}</p>
        <p>
          <i className="fa-solid fa-check mr-2" />
          You must have <strong>Company</strong>, <strong>App Administrator</strong>, or <strong>App Member</strong> permissions in Recurly Engage.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

**Popular use cases** are turnkey prompt patterns and templates that address common business goals—such as cart recovery, feature adoption, upsells, and churn mitigation—allowing you to deploy best practices with minimal configuration.

# Key benefits

* **Accelerated outcomes**: Quickly launch battle-tested engagement patterns without trial and error.
* **Cross-lifecycle coverage**: Address key moments from acquisition through renewal in one unified tool.
* **Data-driven success**: Leverage built-in analytics and recommendations based on real customer behavior.

# Key details

The following outlines the most popular uses of Recurly Engage across the customer lifecycle. Churn-related use cases are often the starting point for many customers.

| Acquisition                                                                                                           | Engagement                                                                                                              | Upsell                                                                                                               | Churn                                                                                          |
| --------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| [**Abandon Cart**](abandon-cart)<br />Prompt exiting and return visitors who started signup to finish/resume checkout | [**Personalized Onboarding**](personalized-onboarding)<br />Onboard new users with prompts only showing unused features | [**Premium Plan Adoption**](premium-plan-upsell)<br />Prompt users with high engagement to upgrade with an incentive | **[Cancel Save](cancel-save)**<br />Reduce cancellations via survey-driven save offers         |
| **[1-Click Resubscribe](one-click-resubscribe)**<br />Customize flow for churned users to resubscribe with one click  | **Boost App Installs**<br />Use a survey to guide users to install and activate on other platforms                      | **Personalize Add-Ons**<br />Recommend one-time purchase items tailored to each user                                 | **[Involuntary Churn](failed-rebill)**<br />Remediate failed payments with active guides       |
| **Increase Registration**<br />Prompt engaged visitors to submit email or mobile info contextually                    | **Increase Feature Adoption**<br />Personalize feature discovery based on usage patterns                                | **Shorten Trials**<br />Target engaged trialists with an incentive to subscribe early                                | **Calm Renewal Anxiety**<br />Prompt users with declining usage ahead of renewals              |
| **Personalize by Source**<br />Tailor site experience for SEM, SEO, partner, or organic visitors                      | **Increase Editorial Impact**<br />Enable content team to surface recommendations in-app                                | **1-Click Upsell Paywalls**<br />Trigger prompts based on usage meters like concurrency or location                  | **Dynamic Downgrade**<br />Match users to a lower-tier plan based on churn risk or consumption |
| *—*                                                                                                                   | **Improve Error Experience**<br />Prompt users experiencing errors with acknowledgement or offer                        | *—*                                                                                                                  | **Win Back Guide**<br />Guide save-offer or dunning users back to engagement                   |