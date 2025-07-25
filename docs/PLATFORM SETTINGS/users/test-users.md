---
title: Test users
excerpt: >-
  Configuration guide for the Test Users feature, which allows whitelisted users
  to preview active prompts in a production environment.
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
          You must have <strong>Company</strong> or <strong>App Administrator</strong> permissions in Recurly Engage.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

The **Test Users** segment is an automatically provisioned group that enables you to restrict prompt visibility to a curated list of user IDs for QA and preview purposes.

# Key benefits

* **Safe testing environment**: Preview prompts in production without impacting all users.
* **Rapid iteration**: Validate creative, triggers, and actions with a controlled audience.
* **Granular control**: Whitelist or remove specific test accounts on demand.

# Key details

## Setup Test Users

Recurly Engage automatically creates a **Test Users** segment for each app upon creation. To configure which users belong to this segment:

* **Go** to **Settings > Users > Test Users**.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/9c4e603-Screenshot_2024-05-22_at_15.20.44.png" />

* **Enter** the **User ID** of a test account. User IDs can be long alphanumeric or GUID strings—ensure you copy the exact value from your source system.

* Click **Add**.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/85a7cff-Screenshot_2024-05-22_at_15.22.28.png" />

Once added, this user will see all active prompts targeted to **Test Users** when they log in.

## Preview via Live tool

You can also simulate a Test User using the Live Preview feature:

* Click the **Live Preview** button in the console. This opens your site and impersonates the selected Test User.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/2714f17-Screenshot_2024-05-22_at_15.23.56.png" />

* Open the **Recurly Engage Preview** tool on your site.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/0543e15-Screenshot_2024-05-22_at_15.25.01.png" />

* The **User ID** field will auto-populate with your Test User’s ID.
* If the prompt status is **Inactive**, navigate to the page where the prompt should appear.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/5deb9c6-Screenshot_2024-05-22_at_15.35.23.png" />

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/a7583fa-Screenshot_2024-05-22_at_15.39.40.png" />

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/0eb2ab1-Screenshot_2024-05-22_at_15.40.24.png" />