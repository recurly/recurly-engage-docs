---
title: Cancel save
excerpt: >-
  Configuration guide for implementing a "Cancel/Save" flow to prevent customer
  churn. It outlines the process of creating and deploying a multi-step survey
  with tailored offers to retain users.
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

<Callout icon="🚧" theme="warn">
  **Important:**

  Conversions are significantly lower when using a redirect URL instead of 1-Click Actions
</Callout>

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

This guide outlines the implementation of a "Cancel/Save" flow, a highly effective strategy for mitigating customer churn. You can **save up to 40%** of your cancelled users with just this one flow. The fundamental principle involves intercepting a customer's attempt to cancel their subscription and subsequently presenting a tailored offer or resolution designed to retain their subscription. This application can range from a singular offer to a comprehensive exit survey that delivers varied solutions contingent upon the customer's stated reason for cancellation.

# Key benefits

* **Reduced churn**: Present targeted offers at the exact moment a customer intends to cancel.
* **Improved satisfaction**: Give customers alternatives, like a different plan or a temporary discount, instead of just forcing them to cancel.
* **Data-driven insights**: Capture valuable feedback on why customers are leaving, which you can use to optimize your retention strategies.

# Key details

Follow these steps to create a simple yet powerful Cancel/Save prompt.

> 📘 When combined with [1-Click Actions](actions-1), you can expect significant reductions in cancellations with improved customer satisfaction.

## Step-by-step guide

1. **Enable** [1-Click Actions](actions-1) by activating the connector to your [Billing](billing) platform.
2. Alternatively, **specify** a redirect URL to an existing cancellation confirmation screen.
3. **Create** a Guide (Settings > Guides) and set the type to **survey**.
4. **Define** the cancellation reasons options with corresponding CTAs:

* Too expensive → CTA to a save offer
* Not enough content → CTA to latest content or save offer
* Technical issues → CTA to support

5. **Create** an A/B experiment on any prompt variation to test different offers or designs.
6. **Set** the segment to **Test Users**.
7. **Set** the trigger to fire on the cancel button click:

* Use the Live Preview tool to detect and capture the cancel click event.
* Or have your developers specify the click event via regex or custom JavaScript.

8. **Start** the **Guide**.
9. **Add** your User ID to the Test Users segment (Settings > Users > Test Users).
10. **Confirm** that the **Guide** launches when you click the cancel button.

## Example

<HTMLBlock>{`
<div style="position: relative; padding-bottom: 62.5%; height: 0;">
  <iframe  
    src="https://www.loom.com/embed/3a55570da3084432bf8516b442ab5590?sid=80617f1e-c3be-4bc3-b322-99d6ad886dee"  
    frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen  
    style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;">
  </iframe>
</div>
`}</HTMLBlock>
