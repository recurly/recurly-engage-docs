---
title: Invite users
excerpt: >-
  Steps to invite team members and manage their access within your Recurly
  Engage application.
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

Learn how to invite users to your Recurly Engage app, assign permission levels, and ensure your team has the right access.

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
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

Inviting users lets administrators grant team members access to specific applications in Recurly Engage and control what actions they can perform based on their permission level.

# Key benefits

* **Granular access control**: Assign precise permissions per user and per app to maintain security and accountability.
* **Streamlined onboarding**: Send invitations directly from the console for fast user setup.
* **Flexible team management**: Easily grant or revoke access across multiple apps without additional accounts.

# Key details

Administrators can invite users to individual apps in Recurly Engage. To grant a user access to multiple apps, send a separate invitation for each one. Only company or app administrators have the ability to modify settings and invite users.

To add a user:

1. In the Recurly Engage console, **go** to **Settings > Users** and **click** **Add user**.

<Image align="center" className="border" border={true} width="70% " src="https://files.readme.io/8080696-image.png" />

2. **Enter** the user’s name, email, and select a permission level. For details on each level, see [User permissions](pulse-users).

<Image align="center" className="border" border={true} width="70% " src="https://files.readme.io/9bca05b-image.png" />

3. **Click** **Send invitation**. The invitee will receive an email to create their login credentials.

<Image align="center" className="border" border={true} width="70% " src="https://files.readme.io/2af7842-image.png" />