---
title: Push prompts
excerpt: >-
  Details on creating and managing push notifications (Push Prompts) in Recurly
  Engage.
deprecated: false
hidden: false
metadata:
  title: ''
  description: >
    A guide to Recurly Engage's push notifications feature. It explains how to
    set up, configure, and send scheduled push prompts to users' devices through
    various channels.
  robots: index
next:
  description: ''
---
# Overview

### Required plan

This feature **may not be included** in the all plans. If you are interested, please contact [Recurly Sales](https://recurly.com/demo/contact-sales/) to discuss upgrade options.

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

Push Prompts send scheduled notifications directly to your users' devices, even when they aren't actively using your app. These messages are delivered via supported channels like Amazon Device Messaging (ADM), Apple Push Notifications service (APNs), and Firebase Cloud Messaging (FCM).

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/1cba839-Screenshot_2024-05-29_at_12.32.25_PM.png" />

# Key benefits

* **Direct engagement:** Reach users on their devices with timely messages, increasing re‑engagement.
* **Scheduled delivery:** Plan notifications in advance to hit optimal send times.
* **Multi‑channel support:** Send via Amazon Device Messaging, Apple Push Notifications service, or Firebase Cloud Messaging.

# Key details

Follow these steps to configure and send push prompts:

### Steps to enable push notifications

1. Ensure you’re an active member of Recurly Engage with a plan that includes Push Prompts. If not, [book a demo today](https://recurly.com/product/engage/) !
2. Setup credentials: 
   1. In the Recurly Engage management console, Pulse, navigate to **Settings → Integrations → Push Notifications**
   2. Enter credentials for the desired [Push channels](https://docs.recurly.com/recurly-engage/docs/push).

<Image align="center" src="https://files.readme.io/681e77099fc338612636e14d772a2eb93216ddac1bf90e5af3dc07c2a613adce-Push_1.png" />

3. Sync device tokens:
   1. Configure and upload device tokens to allow Recurly Engage to target your users' registered devices.
4. Create a [custom device](https://docs.recurly.com/recurly-engage/docs/custom-devices) :
   1. In Pulse, navigate to **Settings → Custom Devices**
   2. Select a **+ New Custom Device** profile for push targeting.
5. Create a [Push Segment](https://docs.recurly.com/recurly-engage/docs/segments) :
   1. In **Pulse** navigate to the **Segments** section and create a **+ New Segment**.
   2. Select Push notification as the device type.
   3. Configure your Segment with the appropriate settings, be sure to configure channel type.

<Image align="center" src="https://files.readme.io/e6d0bd51758f313b517af9c708b667b1e90e2b44737178f8d7c1952f80d6a5e3-Push_2.png" />

6. Create a Push prompt:
   1. In **Pulse**, navigate to the [Prompts](https://docs.recurly.com/recurly-engage/docs/prompts)  section.
   2. Select **+ New Prompt**
   3. First, select **Custom** for the Device Type and **Push Device** for the device type. Then, choose the **Push** prompt style.

<Image align="center" src="https://files.readme.io/b7baff81edc13a1eccf215d64894cb6ff4743a64a5d45f388bc9f8daeca6ab95-Push_3.png" />

7. Configure the prompt:
   1. **Segment:** Choose the Push Notification segment to target specific users.
   2. **Schedule:** Customize the start and end dates and times, frequency, trigger event, and time sensitivities.
   3. **Design:** Edit the prompt design to customize messaging, imagery and actions.

<Image align="center" src="https://files.readme.io/3240e7cf7e9fc9d27b5b10c7301fdcfcf7a1a3df6f11ea11144115478ce95e86-Push_4.png" />

7. Once configured, save and schedule to deliver your push notifications to your audience.

<br />
