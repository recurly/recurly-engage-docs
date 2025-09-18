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

> 📘 Important
>
> Make sure you enable the **Sync events** option, if available for your billing platform under **Settings > Actions**. This ensures that dunning updates are synced with your Recurly Engage segments.

## Guide

1. Make sure you are an active user of Recurly Engage  with Company, App Administrator or App Member permissions.

   <a href="https://recurly.com/product/engage/">If not, book a demo today!</a>
2. **Login to Recurly Engage**

   Access the Recurly Engage Management console, known as **Pulse**, via <a href="https://pulsepp.redfast.com/login">Login</a>. This console serves as a central interface for configuring applications, user traits, segments, prompts, guides, and integrations.
3. **Create a New Payment Failure Guide**

   This guide will be a multi-step journey to re-engage customers who have a failed payment.
   * Go to **Guides** in the main navigation.
   * Select the pre-configured Payment Failure Guide

<Image align="center" src="https://files.readme.io/aa5de9cbe26b0249702e7ea116ccc71b3e11782bbf18f9c7336a3df51a0387b8-payment_1.png" />

<br />

4. **Payment Failure Guide Data**

   When you open up the pre-configured Guide, you’ll see a dashboard showing key data including, **Segments**, **Limits**, the **Status** of the guide, **Schedule** information and any **Daypart** settings. Edit this data based on the needs of your customized Guide.

   You’ll also see a chart displaying important **Users**, **Clicks** and **Conversion** **Rate** data.

<Image align="center" src="https://files.readme.io/04245a5220f32f7804ff6fdd33a76f762ae6f304e35ce0c23521a27ce9f1ca5d-payment_2.png" />

<br />

5. **Set up your prompt**

   Select an Item, or **Prompt** from the Guide.

<Image align="center" src="https://files.readme.io/658f135153cd166ff39b801d0fd5591ce56036abb83ed098100afac34e94e75f-payment_3.png" />

<br />

6. **Add your trigger**

   In the **Details** section, edit your trigger information. The trigger is a page or button on your website where the prompt will fire.

   We recommend showing the Payment Failure prompt on all pages except the Billing Information page. This ensures that users who click the prompt's primary call to action (CTA) and are directed to the billing information page will not encounter the same prompt they just interacted with.

   Remember to configure your Trigger for each prompt in the Guide.

<Image align="center" src="https://files.readme.io/cdb8097573495d76c17d7a998e5a9789fdfa14e27573b0789b39a88e2da8867f-payment_4.png" />

7. **Set your actions**

   In the **Actions** section, set your Action to trigger customized flows based on the user inputs.

   _For Example:_ Redirecting users to the billing information page where they can update their payment information

<Image align="center" src="https://files.readme.io/0e611e403c203beafd5a987d75b38bae5f8c117564d9d6fd9126839a447ff905-payment_5.png" />

8. **Edit your Design**

From the **Details** screen, click “Edit prompt design” to open the prompt customization window.

<Image align="center" src="https://files.readme.io/c1b27afc7ec5022d198cbc931970cbfa4bed25782c7fa789c64847a8f8649673-payment_6.png" />


**Edit the prompt** to customize the title, message, size, and styling to fit your messaging and styles. Make sure the message is clear and compelling. Be sure to configure your prompt on both **Desktop & Mobile.**

<br />

<Image align="center" src="https://files.readme.io/7971859af37136801020b042512f4c9acd387ffc520ad2a988407805513ba0df-payment_7.png" />

<br />

If desired, adjust the prompt visibility settings in the User Interaction section to display the prompt again after specific button clicks within your guide.

<Image align="center" src="https://files.readme.io/518db02ee2dbf6c59cddb4b6bfa77a9335b811ceea8e0be2c92d7bafcb50305a-payment_8.png" />

9. **Repeat steps 5 - 8 for all additional Prompts that are part of the Guide.**

Additional prompts may include the Actions that will appear based on a user's survey results.

For users to view the second step in the Payment Failure Guide, they must first interact with Step 1. Therefore, remember to set up a Trigger for each Prompt within the guide.

_For Example: _ If they select “Too Expensive” They would receive another prompt “Price - Save Offer” that Prompt would also need to be customized and configured.

Be sure to include criteria for when the guide should continue or exit.

For involuntary churn scenarios, a custom goal can be implemented where users are required to perform an additional action, such as updating their payment method, to recover their account. While the primary button click is recorded, the conversion event, which is the redirect, is the key metric tracked. An exit event can be configured to occur upon the achievement of this custom goal.

<Image align="center" src="https://files.readme.io/bb8587e348841c085a91364f95bc70a14136d9e06483f08988357a882b735e70-payment_9.png" />

<br />

10. **Live Preview, Testing and Launch**

* After customizing your prompt, click "Live Preview" to see how the design will appear on your website. Please note that Live Preview does not test the actual flows.
* You can test the flows on Live by adding your own user ID to the Test Users segment under **Settings > Users > Test Users**

<Image align="center" src="https://files.readme.io/6cb63648810bbe226e4c22531d78daee9310b2c26f8587a9ef5e3a39baff70a4-payment_10.png" />

<br />

* In the Cancel Survey guide, add the Test Users as the segment. This ensures that only test users will see the prompt.

<Image align="center" src="https://files.readme.io/81400e4e36f0ed1147b8df63f9ce9977959bc620e4249f12773b0a44ed7a4786-payment_11.png" />

* During testing, if needed, you can reset the user clicks to relaunch the guide for testing. This can be done under **Settings > Users > Test Users > Reset Clicks.**

<Image align="center" src="https://files.readme.io/02209e9972782a84e3327eed8d096416e5bf73f00f979148bdb8df6435727237-payment_12.png" />

* Alternatively, you can use the built in Preview Tool in the **Live Preview** section and set the userID to match the UserId you’re wanting to test.

<Image align="center" src="https://files.readme.io/96e9e17659e4a9969fed1cb81d8d6792e8e03ff3e80417a4fffd4732cabfe0e3-payment_13.png" />

* Once you’re satisfied with your flow, remember to update your segments to target live users instead of test users.
* Set your Guide **Live** in the Status section!

<br />

> 📘 Important
>
> If you connect Recurly Engage to Recurly, the **Failed Payment** segment is created automatically.
