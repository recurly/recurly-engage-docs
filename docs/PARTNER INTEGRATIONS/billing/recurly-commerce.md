---
title: Recurly Commerce
excerpt: >-
  Learn how to create a Recurly Commerce connector action so subscribers can
  pause a subscription or apply a discount with one click from a Recurly Engage
  prompt.
deprecated: false
hidden: false
metadata:
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">This guide explains how to create a Connector Action that integrates your Recurly Commerce account with Recurly Engage. Subscribers can then perform instant, one-click actions on their subscriptions, such as applying a discount or pausing a subscription, directly within Engage prompts and without custom code.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

# Definition

<div class="rp-definition">The Recurly Commerce connector action lets subscribers manage their subscriptions with one click from a Recurly Engage prompt. It runs on the subscription logic of Recurly Commerce and authenticates with your Recurly API key.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-code" aria-hidden="true"></i></div>
    <strong>Code-free user experience</strong>
    <span>Deploy complex subscription actions in Engage prompts with a no-code setup for your development and marketing teams.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-bolt" aria-hidden="true"></i></div>
    <strong>Instant subscription management</strong>
    <span>Let subscribers make real-time changes, such as pausing a subscription or applying a discount, with a single click.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-user-check" aria-hidden="true"></i></div>
    <strong>Reduced churn</strong>
    <span>Deploy targeted save offers and win-back triggers using real-time Commerce actions in Engage to maximize customer retention.</span>
  </div>
</div>

# Key details

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Enable the Recurly Commerce integration</h4><p>Contact your Recurly Account Manager to request that the Recurly Commerce integration feature be enabled in Recurly Engage. Your Account Manager confirms when the feature has been provisioned.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Connect your accounts with your API key</h4><p>Once the feature is enabled, connect your accounts using the steps below.</p></div>
  </div>
</div>

1. Navigate to **Settings > Integrations** in Pulse, the Recurly Engage management console.
2. Locate the **Recurly Commerce** connector setup page.
3. Enter your unique **Recurly API key** in the required field to connect your accounts.

This key establishes a secure, authenticated link between Commerce and Engage and grants the permissions needed to run subscription actions.


<Image src="https://files.readme.io/b789cc94ee2b0a45d7a57d2c9709705b0516f82b29e35525e55a1538d3f59d9c-Screenshot_2025-12-02_at_10.03.06_AM.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Configure your segments</h4><p>Segments let you target specific groups of customers with relevant messages through Recurly Engage.</p></div>
  </div>
</div>

A segment is a distinct group of customers defined by shared financial or behavioral criteria (for example, customers with a failed payment or an expiring card). Targeting these subsets with highly relevant messages maximizes the effectiveness of your campaigns. <a href="https://docs.recurly.com/recurly-engage/docs/segments#/" target="_blank">Learn more about segments</a>.

1. Navigate to **Segments > + New Segment** to add a new segment group.
2. **Name your segment**: Give it a clear, descriptive name.
3. **Select the fields that define your segment**: Use preset fields like user, location, or interactions to build the logic for your targeted group.


<Image src="https://files.readme.io/eb7bef51535c897fdeefece5d27ec3f5a5a642055575358ead03dfeffd99ab85-Screenshot_2025-12-02_at_10.05.41_AM.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Add one-click actions to your prompts</h4><p>For detailed instructions on adding and configuring actions on your prompts, see the <a href="https://docs.recurly.com/recurly-engage/docs/actions-1#/" target="_blank">Actions documentation</a>.</p></div>
  </div>
</div>
