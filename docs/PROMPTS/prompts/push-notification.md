---
title: Push prompts
excerpt: >-
  Details on creating and managing push notifications (Push Prompts) in Recurly
  Engage.
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

A **Push Prompt** sends a scheduled notification to users’ devices via supported channels (ADM, APNs, or FCM), even when they are not actively using your app or site.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/1cba839-Screenshot_2024-05-29_at_12.32.25_PM.png" />

# Key benefits

* **Direct engagement**: Reach users on their devices with timely messages, increasing re‑engagement.
* **Scheduled delivery**: Plan notifications in advance to hit optimal send times.
* **Multi‑channel support**: Send via Amazon Device Messaging, Apple Push Notifications service, or Firebase Cloud Messaging.

# Key details

Follow these steps to configure and send push prompts:

### Steps to send push notifications

1. **Setup** credentials: Enter credentials for the desired push channels. Recurly Engage supports Amazon Device Messaging (ADM), Apple Push Notifications service (APNs), and Firebase Cloud Messaging (FCM). [Push](doc:push)
2. **Sync** device tokens: Configure and upload device tokens so Recurly Engage can target registered devices. [Push](doc:push)
3. **Create** a custom device: Label a device profile for push targeting: [Custom devices](doc:custom-devices)
4. **Create** a push segment:

* **Create** a segment in the console. [Segments](doc:segments)
* **Select** **Push notification** as the device type.

5. **Create** a Push prompt:

* Create a new prompt. [Prompts](doc:prompts)
* Select the **push\_notification** Device Type, then choose the **Push** prompt style.
* Configure the segment, schedule, and notification creative.

Once configured, **save** and **schedule** to deliver your push notifications to your audience.