---
title: Payment failure
excerpt: >-
  Configuration guide for creating a payment failure flow. It details how to set
  up targeted in-app prompts to help users update their payment information and
  reduce involuntary churn.
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

Payment failures are a common issue for subscription businesses, often leading to involuntary churn. This guide will walk you through setting up a customer journey that gently prompts users to update their payment information, helping you recover failed charges and retain subscribers.

# Key benefits

* **Increased recovery**: Guide users directly to a page where they can update their payment info, increasing the likelihood of recovering failed charges.
* **Customer-friendly**: Remind customers about a failed payment through targeted prompts, which is more effective and user-friendly than silent, behind-the-scenes retries.
* **Actionable insights**: Test different messages and designs to see which ones are most effective at getting users to update their payment details.

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
