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
<div class="rp-page">
  <div class="rp-overview">Payment failures are a common cause of involuntary churn. This guide walks you through building a customer journey that gently prompts users to update their payment information, so you can recover failed charges and retain subscribers.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
    <a class="rp-toc-pill" href="#estimate-your-savings"><span class="rp-toc-num">4</span>Estimate your savings</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have <strong>Company</strong>, <strong>App Administrator</strong>, or <strong>App Member</strong> permissions in Recurly Engage.</li>
</ul>

# Definition

<div class="rp-definition">Payment failures are a common issue for subscription businesses, and often lead to involuntary churn. This guide walks you through setting up a customer journey that gently prompts users to update their payment information, helping you recover failed charges and retain subscribers.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-arrow-trend-up" aria-hidden="true"></i></div>
    <strong>Increased recovery</strong>
    <span>Guide users directly to where they can update their payment info, increasing the odds of recovering failed charges.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-face-smile" aria-hidden="true"></i></div>
    <strong>Customer-friendly</strong>
    <span>Remind customers about a failed payment through targeted prompts — more effective and more user-friendly than silent, behind-the-scenes retries.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-chart-line" aria-hidden="true"></i></div>
    <strong>Actionable insights</strong>
    <span>Test different messages and designs to see which ones are most effective at getting users to update their payment details.</span>
  </div>
</div>

# Key details

A common problem for subscription businesses is a failed billing attempt — often caused by expired cards, fraud checks, or spending limits. Your payment processor may run some black-box recovery processes of its own, but only a small percentage of failures get resolved that way.

Recurly Engage adds another layer of protection against involuntary churn: a guide that prompts the user, over one or more visits, to update their payment information.

<div class="rp-callout rp-callout-important">
  <div><strong><i class="fa-solid fa-circle-exclamation" aria-hidden="true"></i> Important</strong>Enable the <strong>Sync events</strong> option, if your billing platform supports it, under <strong>Settings > Actions</strong>. This keeps dunning updates synced with your Recurly Engage segments.</div>
</div>

## Guide

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Confirm your access</h4><p>Make sure you're an active Recurly Engage user with Company, App Administrator, or App Member permissions.</p></div>
  </div>
</div>

<a class="rp-btn-secondary" href="https://recurly.com/product/engage/" target="_blank">Book a demo →</a>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Log in to Recurly Engage</h4><p>Access the Recurly Engage management console — known as Pulse — via <a href="https://pulsepp.redfast.com/login" target="_blank">Login</a>. Pulse is your central interface for configuring applications, user traits, segments, prompts, guides, and integrations.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Create a Payment Failure Guide</h4><p>This guide is a multi-step journey to re-engage customers with a failed payment.</p></div>
  </div>
</div>

<ol>
  <li>Go to <strong>Guides</strong> in the main navigation.</li>
  <li>Select the pre-configured <strong>Payment Failure Guide</strong>.</li>
</ol>


<Image src="https://files.readme.io/aa5de9cbe26b0249702e7ea116ccc71b3e11782bbf18f9c7336a3df51a0387b8-payment_1.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Review the guide data</h4><p>The pre-configured guide opens to a dashboard showing its <strong>Segments</strong>, <strong>Limits</strong>, <strong>Status</strong>, <strong>Schedule</strong>, and any <strong>Daypart</strong> settings, plus a chart of <strong>Users</strong>, <strong>Clicks</strong>, and <strong>Conversion Rate</strong>. Edit these to fit your customized guide.</p></div>
  </div>
</div>

<div class="rp-callout rp-callout-important">
  <div><strong><i class="fa-solid fa-circle-exclamation" aria-hidden="true"></i> Important</strong>If you connect Recurly Engage to Recurly, the <strong>Failed Payment</strong> segment is created automatically.</div>
</div>


<Image src="https://files.readme.io/04245a5220f32f7804ff6fdd33a76f762ae6f304e35ce0c23521a27ce9f1ca5d-payment_2.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Set up your prompt</h4><p>Select a prompt from the guide.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/658f135153cd166ff39b801d0fd5591ce56036abb83ed098100afac34e94e75f-payment_3.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">6</div>
    <div><h4>Add your trigger</h4><p>In the <strong>Details</strong> section, set your trigger — the page or button on your site where the prompt fires. We recommend showing the Payment Failure prompt on every page except Billing Information, so users who click the prompt's CTA and land on Billing Information don't see the same prompt again. Configure a trigger for each prompt in the guide.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/cdb8097573495d76c17d7a998e5a9789fdfa14e27573b0789b39a88e2da8867f-payment_4.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">7</div>
    <div><h4>Set your actions</h4><p>In the <strong>Actions</strong> section, set an action to trigger a customized flow based on the user's input — for example, redirecting users to the billing information page to update their payment.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/0e611e403c203beafd5a987d75b38bae5f8c117564d9d6fd9126839a447ff905-payment_5.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">8</div>
    <div><h4>Edit your design</h4><p>From the <strong>Details</strong> screen, click <strong>Edit prompt design</strong> to open the prompt customization window.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/c1b27afc7ec5022d198cbc931970cbfa4bed25782c7fa789c64847a8f8649673-payment_6.png" align="center" width="75%" border={true} />


Customize the title, message, size, and styling to fit your messaging — make sure the message is clear and compelling, and configure the prompt for both **Desktop & Mobile**.


<Image src="https://files.readme.io/7971859af37136801020b042512f4c9acd387ffc520ad2a988407805513ba0df-payment_7.png" align="center" width="75%" border={true} />


If you'd like, adjust the prompt's visibility settings in the **User Interaction** section to show it again after specific button clicks within your guide.


<Image src="https://files.readme.io/518db02ee2dbf6c59cddb4b6bfa77a9335b811ceea8e0be2c92d7bafcb50305a-payment_8.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">9</div>
    <div><h4>Repeat steps 5–8 for additional prompts</h4><p>Additional prompts might present the actions tied to a user's response. Users need to interact with step 1 before they see step 2, so set up a trigger for each prompt in the guide — for example, selecting "Too expensive" could surface a follow-up "Price - Save offer" prompt that needs its own design and configuration. Be sure to set criteria for when the guide should continue or exit.</p></div>
  </div>
</div>

For involuntary churn, you can set a custom goal that requires the user to take an additional action — like updating their payment method — to recover their account. The primary button click gets recorded, but the conversion event (the redirect) is the metric that matters. You can configure an exit event to fire once that custom goal is met.


<Image src="https://files.readme.io/bb8587e348841c085a91364f95bc70a14136d9e06483f08988357a882b735e70-payment_9.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">10</div>
    <div><h4>Preview, test, and launch</h4><p>After customizing your prompt, click <strong>Live Preview</strong> to see how the design appears on your site. Live Preview doesn't test the actual flows.</p></div>
  </div>
</div>

**Test the flow on Live**: add your own user ID to the **Test Users** segment under **Settings > Users > Test Users**.


<Image src="https://files.readme.io/6cb63648810bbe226e4c22531d78daee9310b2c26f8587a9ef5e3a39baff70a4-payment_10.png" align="center" width="75%" border={true} />


**Add Test Users to the guide**: add Test Users as the segment so only test users see the prompt.


<Image src="https://files.readme.io/81400e4e36f0ed1147b8df63f9ce9977959bc620e4249f12773b0a44ed7a4786-payment_11.png" align="center" width="75%" border={true} />


**Reset clicks during testing**: if you need to relaunch the guide while testing, reset the user's clicks under **Settings > Users > Test Users > Reset Clicks**.


<Image src="https://files.readme.io/02209e9972782a84e3327eed8d096416e5bf73f00f979148bdb8df6435727237-payment_12.png" align="center" width="75%" border={true} />


**Use the built-in preview tool**: alternatively, use the Preview Tool in the **Live Preview** section and set the user ID to the one you want to test.


<Image src="https://files.readme.io/96e9e17659e4a9969fed1cb81d8d6792e8e03ff3e80417a4fffd4732cabfe0e3-payment_13.png" align="center" width="75%" border={true} />


Once you're satisfied with your flow, remember to update your segments to target live users instead of test users, then set your guide's status to **Live**.

## Estimate your savings

<div class="rp-card">

Every churn is lost revenue — and this flow can help you get it back.

Losing users isn't just a number, it's a direct hit to your bottom line. If you're losing 1,000 users a month at $10 each, that's **$10,000 in lost revenue** every month.

Recovering even a fraction of that can make a real difference to your business. By proactively re-engaging users, you can recover meaningful revenue and build a more sustainable subscriber base.

Want to see how you could turn churned users into recovered revenue?

</div>

<a class="rp-btn-primary" href="https://recurly.com/product/engage/" target="_blank">Book a quick demo →</a>
