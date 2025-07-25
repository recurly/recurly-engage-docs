---
title: Users
excerpt: >-
  Overview of the Users settings section in Recurly Engage, covering account
  access and user management tools.
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

The **Users** settings section consolidates all tools for managing who can access your Pulse app, preview prompts in production, troubleshoot individual users, and enforce global exposure limits.

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

The **Users** section groups four core management tools—Pulse Users, Test Users, User Lookup, and Global Limits—into a single navigational area for streamlined configuration and support.

# Key benefits

* **Centralized access control**: Manage all user-related settings from one unified interface.
* **Efficient QA workflows**: Quickly whitelist, lookup, or emulate users without leaving the dashboard.
* **Consistent user experience**: Apply global limits and holdouts to ensure controlled prompt exposure across your entire audience.

# Key details

* Manage team permissions and invite new members with [Pulse Users](pulse-users).
* Whitelist specific accounts to preview prompts in production via [Test Users](test-users).
* Troubleshoot individual accounts by viewing traits, segments, and eligible prompts in [User Lookup](user-lookup).
* Control overall prompt exposure using global holdout percentage, impression limits, and frequency caps in [Global Limits](global-limits).