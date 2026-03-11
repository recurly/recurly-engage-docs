---
title: Segment
excerpt: >-
  Configuration guide for syncing Segment traits into Recurly Engage via Segment
  Unify or Amazon Lambda
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
          Access to your Segment workspace with permission to add destinations.
        </p>
        <p>
          <i className="fa-solid fa-check mr-2" />
          Access to your Segment Unify space with permission to retrieve Unify Access Token and Space ID.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

By setting up an integration to Segment Unify or by routing Segment events to an AWS Lambda Destination, Recurly Engage syncs each user's traits as they arrive on you site, enabling you to target prompts based on all profile data available within your Segment account.

# Key benefits

* **No additional instrumentation**: Leverage your existing Segment calls—no new SDKs or code changes required.
* **Real-time targeting**: Segment events can be available in Recurly Engage within minutes for immediate prompt personalization.
* **Flexible trait mapping**: Sync any profile trait without rebuilding your analytics stack.

# Key details

## Setup Segment Unify Sync

If you utilize Segment Unify (formerly known as Profiles), Recurly Engage can automatically sync traits when a user starts a new session on your site or app.

Within your Segment console:

1. Click on the **Unify** tab in the left nav
2. Select the space that should be synced (i.e. production or staging)
3. Click on **Unify Settings** in the subnav
4. Select **API Access**
5. Note the **Space ID**
6. If an access token has not yet been created, click on **Generate Token** and assign a name (i.e. Recurly Engage Token). Save the token as it will be displayed only once
7. Copy over the  **Unify Access Token** and **Unify Space ID** within the Pulse Settings > Integrations > Segment modal and reach out to your CSM to activate this functionality.

Newly synced traits will appear on the Settings > User Traits screen 5-10 minutes after syncing has commenced.

## Setup Amazon Lambda Destination

As an alternative to integrating with Segment Unify, you may setup an Amazon Lambda destination for events processed by Segment. "Identify" events will trigger a real-time sync of the associated user traits to Recurly Engage.

Setup instructions:

1. **Login** to Segment.

2. **Go** to the correct app workspace.

   <Image align="center" border={true} width="80% " src="https://files.readme.io/f5c742b-Segment_configure.png" className="border" />

3. **Add** a new destination.

   <Image align="center" border={true} width="80% " src="https://files.readme.io/125929e-Segment_configure_2.png" className="border" />

4. **Type** lambda in the search box and click the found tile.

   <Image align="center" border={true} width="80% " src="https://files.readme.io/cfe1f2f-Segment_configure_3.png" className="border" />

5. **Click** "Configure Amazon Lambda".

   <Image align="center" border={true} width="80% " src="https://files.readme.io/8baf8c6-Segment_configure_4.png" className="border" />

6. **Select** your app and **click** "Confirm Source".

   <Image align="center" border={true} width="80% " src="https://files.readme.io/ffd3c94-Segment_configure_5.png" className="border" />

7. Now **go** to **Usage Tracking** and locate the credentials to enter.

   <Image align="center" border={true} width="80% " src="https://files.readme.io/58f7707-Segment_Configure_6.png" className="border" />

8. **Copy over** the `Region`, `Role Address` and `Lambda ARN` values. Make sure to provide the read-only `External ID` to your customer success manager as the final step. **Note that** `Client Context` and `Log Type` do not need any special configuration.

   <Image align="center" border={true} width="80% " src="https://files.readme.io/a036acc-Segment_configure_7.png" className="border" />

   <Image align="center" border={true} width="80% " src="https://files.readme.io/a6f4a75-Segment_Configure_8.png" className="border" />

> **Note:** New traits may take up to 10 minutes before they appear in Recurly Engage.

<br />
