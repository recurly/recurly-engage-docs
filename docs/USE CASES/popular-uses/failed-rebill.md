---
title: Failed rebill
excerpt: >-
  How to use Configuration guide for the Failed Rebill use case, which reduces
  involuntary churn by prompting users to update their payment information after
  a failed billing attempt.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  pages:
    - slug: popular-uses
      title: Popular Uses
      type: basic
---
# Overview

### Video

Here is a video tutorial that shows how to set this up for your website and app.

<Embed url="https://www.loom.com/embed/d1c5c4f59f7a4b23a5e99e92c1381b8b?sid=2ea41637-d7ec-4f32-b722-0c1bceb4d91b" href="https://www.loom.com/embed/d1c5c4f59f7a4b23a5e99e92c1381b8b?sid=2ea41637-d7ec-4f32-b722-0c1bceb4d91b" typeOfEmbed="iframe" height="480px" width="100%" iframe="true" />

<br />

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

A common problem for subscription businesses is when an attempt to bill the customer fails—due to expired cards, fraud flags, or spending limits. While your payment processor may offer automated retries, only a small percentage of failed charges succeed this way. Recurly Engage provides a guide to gently prompt users—over one or more visits—to update their payment details and recover revenue.

# Key benefits

* **Increased recovery**: Guide users to update payment info and recover failed charges.
* **Customer-friendly**: Offer contextual reminders rather than silent retries.
* **Actionable insights**: Track which prompts and copy drive the highest update rates.

# Key details

A common problem with subscription businesses is when an attempt to bill the customer fails. This can happen due to various reasons such as expired cards, fraud, or spending limits. While your payment processor may offer some black-box processes to remedy this issue, only a tiny percentage are recovered this way.

Recurly Engage provides an additional tool to reduce involuntary churn by using a guide to prompt the user—over one or more visits—to update their payment information.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/0d72e3a-image.png" />

> 📘 Important
>
> Make sure you enable the **Sync events** option, if available for your billing platform under **Settings > Actions**. This ensures that dunning updates are synced with your Recurly Engage segments.

## Guide

1. **Follow** these instructions to [Create a Guide](guides) and **choose** the **Journey** type.
2. **Configure** the first prompt as a **Notification** that triggers when the first rebill attempt fails.
3. **Set** the CTA to redirect users to your payment update screen.
4. **Create** an A/B experiment on any prompt in the guide to test different messages or designs.
5. **Target** the segment to **Test Users**.
6. **Set** the trigger to **Any Page** (refine later as needed).
7. **Start** the Guide.
8. **Add** your user ID to the Test Users segment (**Settings > Users > Test Users**).
9. **Confirm** the Guide launches as configured.
10. **Adjust** targeting to the **Failed Payment** segment once you’ve synced events.

> 📘 Important
>
> If you connect Recurly Engage to Recurly, the **Failed Payment** segment is created automatically.