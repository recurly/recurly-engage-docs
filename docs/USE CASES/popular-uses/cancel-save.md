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

<Image align="center" src="https://files.readme.io/e0bed59ebb84babc996bc9e52d8eb3837dd727eb90fd60cc7075232757f7aa60-cancel_2.png" />

<br />

5. **Cancel Survey with Offers Guide Data**

   When you open up the pre-configured Guide, you’ll see a dashboard showing key data including, **Segments, Limits**, the **Status** of the guide, **Schedule** information and any **Daypart** settings. Edit this data based on the needs of your customized Guide.

   You’ll also see a chart displaying important **Users**, **Clicks** and **Conversion** **Rate** data.

<Image align="center" src="https://files.readme.io/72ff000242fba0e849f8ee007d999355e3cec86f408113a1e4eace2db2555cd4-cancel_3.png" />

<br />

6. **Set Up Your Prompt**

   Select the Cancellation Reasons Survey from the Guide.

<Image align="center" src="https://files.readme.io/64154c89c1a4b56224c397100eadc53648d4b09ef28626614a8a1fb5c1da4a1d-cancel_4.png" />

<br />

7. **Add your Trigger**

   In the Details section, edit your trigger information. The trigger is the css selector on your website that when clicked, triggers the prompt to fire.

   Because the Cancel Survey guide flow is based on the user interactions, you only need to apply a trigger to the first prompt.

   _For example: _The Cancellation survey prompt would fire when the user clicks the “Cancel Subscription” button.

<Image align="center" src="https://files.readme.io/44709757aef931a087945318a4063a6161b5c682448f7174ef6e9b716ace2da4-cancel_5.png" />

<br />

8. **Set your Actions**

   In the **Actions** section, set your Action and Values to trigger customized flows based on the user inputs.

   _For example:_

<ol type="a">
  <li>Too expensive → CTA to a <strong>save</strong> offer</li>
  <li>Not enough content → CTA to latest content or <strong>save</strong> offer</li>
  <li>Technical issues → CTA to support</li>
</ol>

<Image align="center" src="https://files.readme.io/5a8d386476cd5d74a59ced1fd99863a1e8ce6b26ee73536cf36a6605b810daff-cancel_7.png" />

<br />

9. **Edit your Design**

   From the **Details** section, click “Edit prompt design” to open the prompt customization window.

   <br />

<Image align="center" src="https://files.readme.io/b3336790a31fd879577c7cfedd6af3abdfd4093a9b5058995803abadffca8ea7-cancel_8.png" />

**Edit the prompt** to customize the title, message, size, and styling to fit your messaging and styles. Make sure the message is clear and compelling. Be sure to configure your prompt on both **Desktop & Mobile.**

<br />

<Image align="center" src="https://files.readme.io/8f3c527f5f7c120bb9aab711eddc2272fef33f2025ba9a02b5f4a9b2effb9ac5-cancel_9.png" />

<br />

If desired, adjust the prompt visibility settings in the User Interaction section to display the prompt again after specific button clicks within your guide.

<Image align="center" src="https://files.readme.io/2f15699bf2836225d4d37ec21024cf7302638069154069364cc399a66d4431f5-cancel_10.png" />

In the Form section, configure the form to hide and show your survey options. Ensure the value matches the action in the details screen.

<br />

<Image align="center" src="https://files.readme.io/673d29073865432f7332848a74a1b9e1662d7c631c38a53d0247b38206748d36-cancel_11.png" />

<br />

10. **Repeat step 6, 8 & 9 for all additional Prompts**

* Additional prompts may include the Actions that will appear based on a user's survey results.

  _For Example:_ If they select “Too Expensive” They would receive another prompt “Price - Save Offer” that would also need to be customized and configured.
* Be sure to include criteria for when the guide should continue or exit, if necessary.

<Image align="center" src="https://files.readme.io/60fbea1fc41413091b7ddb4a48159f91dddec9f4f84ed4465ba88a649a513483-cancel_12.png" />

<br />

11. **Live Preview, Testing and Launch**
    * After customizing your prompt, click "Live Preview" to see how the design will appear on your website. Please note that Live Preview does not test the actual flows.
    * You can test the flows on Live by adding your own user ID to the **Test Users** segment under **Settings > Users > Test Users.**

      <Image align="center" src="https://files.readme.io/ab10db3a14f319a92e4be5bdd3ee5821901de56112578c9efddfe8f98e2d6182-cancel_13.png" />
    * In the Cancel Survey guide, add the Test Users as the segment. This ensures that only test users will see the prompt.

      <Image align="center" src="https://files.readme.io/4c47b6b47683b920a6319001ac9e876830a24fe910415bc60c49f86442c7f6d9-cancel_14.png" />

* During testing, if needed, you can reset the user clicks to relaunch the guide for testing. This can be done under **Settings > Users > Test Users > Reset Clicks.**

<Image align="center" src="https://files.readme.io/4947bd8af0dbdcaf25f72ab3bb855071ac04963189b70a1b879647acbb1d1a21-cancel_15.png" />

* Alternatively, you can use the built in Preview Tool in the **Live Preview** section and set the userID to match the UserId you’re wanting to test.

  <Image align="center" src="https://files.readme.io/0210d22d8974405a35c6db572d1200ce32909f262385cab2f09963b5da976df1-cancel_16.png" />
* Once you’re satisfied with your flow, **remember to update your segments** to target live users instead of test users.
* Set your Guide **Live** in the Status section!

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

<br />

## Estimate your savings

Every Churn is Lost Revenue. We Can Help You Get It Back.

Losing users isn't just a number- it's a direct hit to your bottom line. If you're losing 1,000 users a month, each worth $10, that’s **$10,000 in lost revenue** every single month.

Imagine what recovering even a fraction of that could do for your business. By proactively re-engaging users, you can recover significant revenue and build a more sustainable future.

Want to see how we can turn your churned users into recovered revenue?

<a href="https://recurly.com/product/engage/">Book a quick demo today.</a>

<br />
