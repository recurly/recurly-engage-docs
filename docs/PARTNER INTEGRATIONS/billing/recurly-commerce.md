---
title: Recurly Commerce
excerpt: >-
  Documentation for connecting Recurly Commerce with Recurly Engage, enabling
  real-time, one-click actions (like pausing or applying discounts) within
  Engage prompts for active subscriptions.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

This guide details the process of creating a Connector Action to integrate your Recurly Commerce account with your Recurly Engage instance. This powerful connection gives your subscribers the ability to perform instant, one-click actions on their subscriptions directly within Engage prompts, all without requiring custom code.

Specifically, this integration unlocks out-of-the-box actions such as applying discounts or pausing a subscription, leveraging the robust subscription logic of Recurly Commerce to power seamless user experiences in Recurly Engage.

# Key benefits

* **Code-free User Experience:** Quickly deploy complex subscription actions within Engage prompts, allowing for an easy, no-code setup for your development and marketing teams.
* **Instant Subscription Management:** Enable subscribers to make real-time changes, such as pausing or applying discounts, with a single click, dramatically improving the user experience.
* **Crush Churn:** Deploy targeted save offers and win-back triggers using real-time Commerce actions in Engage, allowing you to maximize customer retention efforts.

# Key steps

## Step 1: Enable the Recurly Commerce integration

* **Contact your Recurly Account Manager** to request the enablement of the Recurly Commerce integration feature within Recurly Engage.
* Your Account Manager will confirm when the feature has been successfully provisioned.

## Step 2: Connect your accounts using the API key

* Once the feature is enabled, navigate to **Settings > Integrations** within Pulse, the Recurly Engage management console.
* Locate the **Recurly Commerce** connector setup page.
* Enter your unique **Recurly API Key** into the required field to instantly connect your accounts. This key establishes a secure, authenticated link between Commerce and Engage, granting the necessary permissions for executing subscription actions.

<Image align="center" border={true} width="80% " src="https://files.readme.io/b789cc94ee2b0a45d7a57d2c9709705b0516f82b29e35525e55a1538d3f59d9c-Screenshot_2025-12-02_at_10.03.06_AM.png" className="border" />

## Step 3: Configure your segments

A Segment is a distinct group of customers defined by shared financial or behavioral criteria (e.g., customers with a failed payment or an expiring card). Configuring segments allows you to target specific subsets of customers with highly relevant messages through Recurly Engage, maximizing the effectiveness of your campaigns. <a href="https://docs.recurly.com/recurly-engage/docs/segments#/">Learn more about segments</a>.

* Navigate to **Segments > + New Segment** to add a new segment group.
* **Name Your Segments:** Give your segment a clear and descriptive name.
* **Select the Appropriate Fields to Define Your Segments:** Use preset fields like user, location or interactions to build the specific logic for your targeted group.
* <a href="https://docs.recurly.com/recurly-engage/docs/segments#/">Learn more about segments</a>.

<Image align="center" border={true} width="80% " src="https://files.readme.io/eb7bef51535c897fdeefece5d27ec3f5a5a642055575358ead03dfeffd99ab85-Screenshot_2025-12-02_at_10.05.41_AM.png" className="border" />

## Step 4: Add one-click actions to your Recurly Engage prompts

* For detailed instructions on adding and configuring actions to your prompts, please refer to the <a href="https://docs.recurly.com/recurly-engage/docs/actions-1#/">Actions documentation</a>.
