---
title: Personalized onboarding
excerpt: '  A guide to setting up a personalized onboarding experience. It explains how to create multi-visit, contextual prompts that guide new users without using disruptive, traditional tours.'
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: See more popular uses
  pages:
    - type: basic
      slug: popular-uses
      title: Popular Uses
---
# Overview

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

A well-designed onboarding experience is crucial for user retention and engagement. This guide will show you how to set up a personalized, multi-visit onboarding journey that educates users contextually, without disrupting their flow. Unlike traditional tours, this approach delivers prompts only for features the user hasn’t yet seen.

Traditional approaches to onboarding new users include a step-by-step homepage tour with highlighted callouts to various features. This method may work for B2B, but B2C users often find it disruptive.

Recurly Engage’s Journey guide lets you predefine a sequence of prompts linked to key site elements. Each prompt fires only if the user hasn’t completed the associated action, and you can schedule them over multiple visits—resulting in a more user-friendly onboarding flow.

# Key benefits

* **Contextual guidance**: Prompts appear only when a user interacts with a new feature, providing relevant guidance at the right moment.
* **Multi-visit flexibility**: Onboarding steps are spread across multiple sessions, preventing user overload and respecting their learning pace.
* **Higher engagement**: A streamlined, non-disruptive experience leads to higher engagement with your key features.

# Key details

> 📘 Important
>
> Create usage trackers for your key features and content, then reference those trackers in your onboarding guide to target only first-time interactions.

## Guide

1. Make sure you are an active user of Recurly Engage  with Company, App Administrator or App Member permissions.

   <a href="https://recurly.com/product/engage/">If not, book a demo today!</a>
2. **Login to Recurly Engage**

   Access the Recurly Engage Management console, known as **Pulse**, via <a href="https://pulsepp.redfast.com/login">Login</a>. This console serves as a central interface for configuring applications, user traits, segments, prompts, guides, and integrations.
3. **Create a New Default Personalized Onboarding Guide**
   * Go to **Guides** in the main navigation.
   * Select the pre-configured Default Personalized Onboarding Guide

<Image align="center" src="https://files.readme.io/9b8b2dca341ae321013408e8ddea3069aeb07cc75046c43280c17b9580e5fa0e-personalized_1.png" />

<br />

4. **Default Personalized Onboarding Guide Data**

   When you open up the pre-configured Guide, you’ll see a dashboard showing key data including, **Segments**, **Limits**, the **Status** of the guide, **Schedule** information and any **Daypart** settings. Edit this data based on the needs of your customized Guide.

   You’ll also see a chart displaying important **Users**, **Clicks** and **Conversion Rate** data.

<Image align="center" src="https://files.readme.io/ff4212545cfcd3ad1522f8546c8cd9bc69431a5dac00f26225369cbb77fdbefc-personalized_2.png" />

<br />

5. **Set up your prompt**

   Select an Item, or **Prompt** from the Guide.

   <Image align="center" src="https://files.readme.io/12f91dd5b9c010cb9fd4b0246a59b210184e6e45d915fd026ec03560d1336943-personalized_3.png" />

<br />

6. **Add your trigger**

   In the **Details** section, edit your trigger information. The trigger is the page on your website that when visited, triggers the prompt to fire.

   _For Example:_ Step 1 would fire if the user clicks a button on your website.

<Image align="center" src="https://files.readme.io/83aa4092a448512127e5d0404e1529535ce85700b8696235c00bfd865cad0394-personalized_4.png" />

<br />

7. **Set your actions**

   In the **Actions** section, set your Action and Values to trigger customized flows based on the user inputs.

   _For Example:_ If the user clicks the primary button on the Prompt, direct them to a specific page or serve then another customized Save prompt.

<Image align="center" src="https://files.readme.io/948784a0bae3cc40bd2e3c26a0074681c3fab42e8b84d1b71c94800e44dfe41d-payment_5.png" />

<br />

8. **Edit your design**

   From the **Details** section, click “Edit prompt design” to open the prompt customization window.

<Image align="center" src="https://files.readme.io/10350322980f593844f3294a88964af5cfd844a8d144be9ded363589c5a0e0b2-personalized_6.png" />

<br />

**Edit the prompt** to customize the title, message, size, and styling to fit your messaging and styles. Make sure the message is clear and compelling. Be sure to configure your prompt on **Desktop & Mobile.**

<Image align="center" src="https://files.readme.io/3d85386b117cbed7fd6850b9bfc4300c1eb2279b0604f3a3c69a0872b0120911-personalized_7.png" />


If desired, adjust the prompt visibility settings in the User Interaction section to display the prompt again after specific button clicks within your guide.

<Image align="center" src="https://files.readme.io/41d42f9ca37606cfaef0a09727dbcdcb2eb2f67f87d170164bc6dd94445dc468-personalized_8.png" />

<br />

<br />

9. **Repeat steps 5 - 8 for all additional Prompts that are part of the Guide.**

Additional prompts may include the Actions that will appear based on a users survey results.

For Example: If they select “Too Expensive” They would receive another prompt “Price - Save Offer” that would also need to be customized and configured.

Be sure to include criteria for when the guide should continue or exit.

For involuntary churn scenarios, a custom goal can be implemented where users are required to perform an additional action, such as updating their payment method, to recover their account. While the primary button click is recorded, the conversion event, which is the redirect, is the key metric tracked. An exit event can be configured to occur upon the achievement of this custom goal.

<Image align="center" src="https://files.readme.io/2f791cf37a4478d51c31e03dbf2c491563a5258cfd41f9097e7276ba4db92db3-personalized_9.png" />

<br />

10. **Live Preview, Testing and Launch**

* After customizing your prompt, click "Live Preview" to see how the design will appear on your website. Please note that Live Preview does not test the actual flows.
* You can test the flows on Live by adding your own user ID to the Test Users segment under **Settings > Users > Test Users**.

<Image align="center" src="https://files.readme.io/6c0a17189e2557485c7b70e28ee18c8602d9a65fcd1c6a1ef628f2fc6d33a91c-personalized_10.png" />

* In the Cancel Survey guide, add the Test Users as the segment. This ensures that only test users will see the prompt.

<Image align="center" src="https://files.readme.io/b31c255ddbeb2b24237e67432f8b9318d288c9d930de1e3b4e8c7ccf8bd201e0-personalized_11.png" />

* During testing, if needed, you can reset the user clicks to relaunch the guide for testing. This can be done under **Settings > Users > Test Users > Reset Clicks.**

<Image align="center" src="https://files.readme.io/a175319ab01b0e7209d0dcc8aa737e4d79ee8794b8c9ba3cab754a55c6fd394c-personalized_12.png" />

<br />

* Alternatively, you can use the built in Preview Tool in the Live Preview section and set the userID to match the UserId you’re wanting to test.

<Image align="center" src="https://files.readme.io/d77463969c9c9a85460dc89a625f6c9f9647e853378830d17eb27ab07b8a2604-personalized_13.png" />

* Once you’re satisfied with your flow, **remember to update your segments** to target live users instead of test users.
* Set your Guide **Live** in the Status section!

<br />

<br />

<br />

<br />

> 📘 Important
>
> To experiment with different onboarding sequences, run an A/B test on your guide prompts.

<br />
