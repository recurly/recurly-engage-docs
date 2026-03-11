---
title: Segment
excerpt: >-
  Configuration guide for ingesting Segment.com events into Recurly Engage via
  AWS Lambda or via the Segment Unify
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

By routing Segment events through an AWS Lambda function, Recurly Engage ingests those events as custom usage traits (e.g., page views, button clicks), enabling you to target prompts based on real user behavior tracked in Segment.

# Key benefits

* **No additional instrumentation**: Leverage your existing Segment calls—no new SDKs or code changes required.
* **Real-time targeting**: Segment events can be available in Recurly Engage within minutes for immediate prompt personalization.
* **Flexible event mapping**: Track any Page, Screen, or custom Track call as a usage trait without rebuilding your analytics stack.

# Key details

## Setup Amazon Lambda Destination

Recurly Engage allows you to ingest Segment.com events and target your users according to your existing Page (web), Screen (mobile), and Track calls. This article explains how to add us as a destination via Amazon Lambda.

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

> **Note:** Segment data can take up to one hour before it appears in Recurly Engage.

## Setup Segment Unify Sync

If you utilize Segment Unify (formerly known as Profiles), Recurly Engage can automatically sync traits when a user starts a new session on your site or app. Make sure to configure the **Unify Access Token** and **Unify Space ID** within the Pulse Settings > Integrations > Segment modal and reach out to support to activate this functionality.

Newly synced traits will appear on the Settings > User Traits screen 5-10 minutes after syncing has commenced.

## Adding a new tracker

1. **Go** to **Settings > Usage Tracking > Segment > Add New Tracker**.

   <Image align="center" border={true} width="80% " src="https://files.readme.io/47e233c-Segment_configure_9.png" className="border" />

2. **Select** a Segment event.

   <Image align="center" border={true} width="80% " src="https://files.readme.io/0caf0ba-Segment_configure_10.png" className="border" />

3. **Click** **Submit**.

   <Image align="center" border={true} width="80% " src="https://files.readme.io/8c96b24-Segment_Configure_11.png" className="border" />

   <Image align="center" border={true} width="80% " src="https://files.readme.io/f74c2d1-Segment_Configure_12.png" className="border" />

4. **Go** to **Segments > New Segment** and **choose** the **Usage** tab.

   <Image align="center" border={true} width="80% " src="https://files.readme.io/8ec2610-Segment_Configure_13.png" className="border" />

5. Under **Usage**, **select** your newly ingested Segment trait to target prompts based on those events.

   <Image align="center" border={true} width="80% " src="https://files.readme.io/0af69fd-Redfast_usage_4.png" className="border" />
