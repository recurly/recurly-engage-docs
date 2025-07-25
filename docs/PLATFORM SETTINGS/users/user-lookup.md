---
title: User lookup
excerpt: >-
  Configuration guide for the User Lookup tool, which enables you to
  troubleshoot individual users by viewing their traits and eligible prompts.
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

The **Lookup** tool allows you to check a specific user's traits and view the prompts they are eligible to see, streamlining troubleshooting.

# Key benefits

* **Quick troubleshooting**: Instantly view a user’s attributes and active prompts to diagnose issues swiftly.
* **Live emulation**: Impersonate any user in your environment to replicate their experience in real time.
* **Improved support**: Provide targeted assistance by understanding exactly which prompts a user sees and why.

# Key details

The Lookup tool allows you to effectively troubleshoot your users' experience with the prompts by checking a specific user's traits and prompts they are eligible to see.

<Image align="center" className="border" border={true} src="https://files.readme.io/d111e0b-image.png" />

To look up a specific user, enter their user ID into the search field. User IDs can sometimes be a long alpha-numeric or hex string so make sure you copy the user ID correctly from your source reference before entering it here.

Then, hit **View** to load the user's data or **Impersonate** to open your site using our Live tool and emulate your selected user.

<Image align="center" className="border" border={true} src="https://files.readme.io/ff03aac-image.png" />

<Image align="center" className="border" border={true} src="https://files.readme.io/858e875-image.png" />

<Image align="center" className="border" border={true} src="https://files.readme.io/c24d259-image.png" />