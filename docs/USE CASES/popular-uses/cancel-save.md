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

1. Make sure you are an active user of Recurly Engage with Company, App Administrator or App Member permissions.

   <a href="https://recurly.com/product/engage/">If not, book a demo today!</a>
2. **Login to Recurly Engage**

   Access the Recurly Engage management console, known as Pulse, via <a href="https://pulsepp.redfast.com/login">Login</a>. This console serves as a central interface for configuring applications, user traits, segments, prompts, guides, and integrations.
3. **Activate 1-Click Actions**

   To use features like applying a coupon automatically, you need to enable the connector for your <a href="https://docs.recurly.com/recurly-engage/docs/billing">billing platform</a> (e.g. Recurly, Stripe)

   Activate the connector to enable <a href="https://docs.recurly.com/recurly-engage/docs/actions-1">1-Click Actions.</a>

   Alternatively, if you prefer to redirect users to an existing cancellation page on your site, you can specify that URL instead.

   If your billing platform isn’t one of our out-of-the-box options, you can still integrate it with API actions. <a href="https://docs.recurly.com/recurly-engage/docs/billing">More details on platform integration are available.</a>

<Image align="center" src="https://files.readme.io/0c70fd88cadbe4ded00ad4b2510717b33ad88f030081518231a48647520188e8-cancel_1.png" />

4. **Create a new Cancel Survey with Offers**

   This guide will be a multi-step journey to re-engage customers who are attempting to cancel their subscription.

* Go to Guides in the main navigation
* Select the pre-configured Cancel Survey with Offers.

<br />

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
