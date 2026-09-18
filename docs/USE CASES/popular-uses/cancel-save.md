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
<div class="rp-page">
  <div class="rp-overview">Cancel Save — also known as voluntary churn mitigation — intercepts a customer's cancellation attempt and presents a tailored offer or survey to keep them subscribed. This guide walks you through building a Cancel/Save flow from setup to launch.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-callout rp-callout-important">
    <div><strong><i class="fa-solid fa-circle-exclamation" aria-hidden="true"></i> Important</strong>Conversions are significantly lower when using a redirect URL instead of 1-Click Actions.</div>
  </div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
    <a class="rp-toc-pill" href="#example"><span class="rp-toc-num">4</span>Example</a>
    <a class="rp-toc-pill" href="#estimate-your-savings"><span class="rp-toc-num">5</span>Estimate your savings</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have <strong>Company</strong>, <strong>App Administrator</strong>, or <strong>App Member</strong> permissions in Recurly Engage.</li>
</ul>

# Definition

<div class="rp-definition">Cancel Save — also known as voluntary churn mitigation — is a highly effective strategy for reducing cancellations. You can save up to 40% of your cancelling users with just this one flow. The idea is simple: intercept a customer's attempt to cancel their subscription, then present a tailored offer or resolution designed to keep them subscribed. That can range from a single offer to a full exit survey that serves different solutions based on the customer's stated reason for cancelling.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-arrow-trend-down" aria-hidden="true"></i></div>
    <strong>Reduced churn</strong>
    <span>Present targeted offers at the exact moment a customer intends to cancel.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-face-smile" aria-hidden="true"></i></div>
    <strong>Improved satisfaction</strong>
    <span>Give customers alternatives — a different plan, a temporary discount — instead of just letting them cancel.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-chart-line" aria-hidden="true"></i></div>
    <strong>Data-driven insights</strong>
    <span>Capture feedback on why customers are leaving, and use it to sharpen your retention strategy.</span>
  </div>
</div>

# Key details

Follow these steps to build a simple, effective Cancel/Save prompt.

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>Combine this with <a href="https://docs.recurly.com/recurly-engage/docs/actions-1" target="_blank">1-Click Actions</a> for a significant reduction in cancellations and better customer satisfaction.</div>
</div>

## Step-by-step guide

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
    <div><h4>Activate 1-Click Actions</h4><p>To use features like auto-applying a coupon, enable the connector for your <a href="https://docs.recurly.com/recurly-engage/docs/billing" target="_blank">billing platform</a> (Recurly, Stripe, and others), then activate <a href="https://docs.recurly.com/recurly-engage/docs/actions-1" target="_blank">1-Click Actions</a>.</p></div>
  </div>
</div>

<ul class="rp-list">
  <li>If you'd rather redirect users to an existing cancellation page on your site, specify that URL instead.</li>
  <li>If your billing platform isn't one of the out-of-the-box options, you can still integrate it with API actions — see <a href="https://docs.recurly.com/recurly-engage/docs/billing" target="_blank">platform integration</a> for details.</li>
</ul>


<Image src="https://files.readme.io/0c70fd88cadbe4ded00ad4b2510717b33ad88f030081518231a48647520188e8-cancel_1.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Create a Cancel Survey with Offers</h4><p>This guide is a multi-step journey to re-engage customers who are trying to cancel.</p></div>
  </div>
</div>

<ol>
  <li>Go to <strong>Guides</strong> in the main navigation.</li>
  <li>Select the pre-configured <strong>Cancel Survey with Offers</strong>.</li>
</ol>


<Image src="https://files.readme.io/e0bed59ebb84babc996bc9e52d8eb3837dd727eb90fd60cc7075232757f7aa60-cancel_2.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Review the guide data</h4><p>The pre-configured guide opens to a dashboard showing its <strong>Segments</strong>, <strong>Limits</strong>, <strong>Status</strong>, <strong>Schedule</strong>, and any <strong>Daypart</strong> settings, plus a chart of <strong>Users</strong>, <strong>Clicks</strong>, and <strong>Conversion Rate</strong>. Edit these to fit your customized guide.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/72ff000242fba0e849f8ee007d999355e3cec86f408113a1e4eace2db2555cd4-cancel_3.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">6</div>
    <div><h4>Set up your prompt</h4><p>Select the <strong>Cancellation Reasons Survey</strong> from the guide.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/64154c89c1a4b56224c397100eadc53648d4b09ef28626614a8a1fb5c1da4a1d-cancel_4.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">7</div>
    <div><h4>Add your trigger</h4><p>In the <strong>Details</strong> section, set your trigger — the CSS selector on your site that fires the prompt when clicked. Since the Cancel Survey flow follows the user's interactions, you only need a trigger on the first prompt.</p></div>
  </div>
</div>

<ul class="rp-list">
  <li>For example: the cancellation survey prompt fires when the user clicks the "Cancel Subscription" button.</li>
</ul>


<Image src="https://files.readme.io/44709757aef931a087945318a4063a6161b5c682448f7174ef6e9b716ace2da4-cancel_5.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">8</div>
    <div><h4>Set your actions</h4><p>In the <strong>Actions</strong> section, set your action and values to trigger customized flows based on the user's input.</p></div>
  </div>
</div>

For example:

<ol type="a">
  <li>Too expensive → CTA to a save offer</li>
  <li>Not enough content → CTA to the latest content or a save offer</li>
  <li>Technical issues → CTA to support</li>
</ol>


<Image src="https://files.readme.io/5a8d386476cd5d74a59ced1fd99863a1e8ce6b26ee73536cf36a6605b810daff-cancel_7.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">9</div>
    <div><h4>Edit your design</h4><p>From the <strong>Details</strong> section, click <strong>Edit prompt design</strong> to open the prompt customization window.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/b3336790a31fd879577c7cfedd6af3abdfd4093a9b5058995803abadffca8ea7-cancel_8.png" align="center" width="75%" border={true} />


Customize the title, message, size, and styling to fit your messaging — make sure the message is clear and compelling, and configure the prompt for both **Desktop & Mobile**.


<Image src="https://files.readme.io/8f3c527f5f7c120bb9aab711eddc2272fef33f2025ba9a02b5f4a9b2effb9ac5-cancel_9.png" align="center" width="75%" border={true} />


If you'd like, adjust the prompt's visibility settings in the **User Interaction** section to show it again after specific button clicks within your guide.


<Image src="https://files.readme.io/2f15699bf2836225d4d37ec21024cf7302638069154069364cc399a66d4431f5-cancel_10.png" align="center" width="75%" border={true} />


In the **Form** section, configure the form to show and hide your survey options — make sure each value matches the corresponding action on the Details screen.


<Image src="https://files.readme.io/673d29073865432f7332848a74a1b9e1662d7c631c38a53d0247b38206748d36-cancel_11.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">10</div>
    <div><h4>Repeat steps 6, 8, and 9 for additional prompts</h4><p>Additional prompts might present the actions tied to a user's survey answer — for example, selecting "Too expensive" could surface a follow-up "Price - Save offer" prompt that needs its own design and configuration. Be sure to set criteria for when the guide should continue or exit, if needed.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/60fbea1fc41413091b7ddb4a48159f91dddec9f4f84ed4465ba88a649a513483-cancel_12.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">11</div>
    <div><h4>Preview, test, and launch</h4><p>After customizing your prompt, click <strong>Live Preview</strong> to see how the design appears on your site. Live Preview doesn't test the actual flows.</p></div>
  </div>
</div>

**Test the flow on Live**: add your own user ID to the **Test Users** segment under **Settings > Users > Test Users**.


<Image src="https://files.readme.io/ab10db3a14f319a92e4be5bdd3ee5821901de56112578c9efddfe8f98e2d6182-cancel_13.png" align="center" width="75%" border={true} />


**Add Test Users to the guide**: in the Cancel Survey guide, add Test Users as the segment so only test users see the prompt.


<Image src="https://files.readme.io/4c47b6b47683b920a6319001ac9e876830a24fe910415bc60c49f86442c7f6d9-cancel_14.png" align="center" width="75%" border={true} />


**Reset clicks during testing**: if you need to relaunch the guide while testing, reset the user's clicks under **Settings > Users > Test Users > Reset Clicks**.


<Image src="https://files.readme.io/4947bd8af0dbdcaf25f72ab3bb855071ac04963189b70a1b879647acbb1d1a21-cancel_15.png" align="center" width="75%" border={true} />


**Use the built-in preview tool**: alternatively, use the Preview Tool in the **Live Preview** section and set the user ID to the one you want to test.


<Image src="https://files.readme.io/0210d22d8974405a35c6db572d1200ce32909f262385cab2f09963b5da976df1-cancel_16.png" align="center" width="75%" border={true} />


Once you're satisfied with your flow, remember to update your segments to target live users instead of test users, then set your guide's status to **Live**.

## Example

<div style={{position: "relative", paddingTop: "62.5%", marginBottom: "28px", borderRadius: "10px", overflow: "hidden"}}>
  <iframe src="https://www.loom.com/embed/3a55570da3084432bf8516b442ab5590?sid=80617f1e-c3be-4bc3-b322-99d6ad886dee"
    title="Cancel Save example walkthrough"
    allow="autoplay; fullscreen"
    allowtransparency="true"
    frameBorder="0"
    scrolling="no"
    allowFullScreen
    style={{position: "absolute", top: 0, left: 0, width: "100%", height: "100%", border: "none"}}></iframe>
</div>

## Estimate your savings

<div class="rp-card">

Every churn is lost revenue — and this flow can help you get it back.

Losing users isn't just a number, it's a direct hit to your bottom line. If you're losing 1,000 users a month at $10 each, that's **$10,000 in lost revenue** every month.

Recovering even a fraction of that can make a real difference to your business. By proactively re-engaging users, you can recover meaningful revenue and build a more sustainable subscriber base.

Want to see how you could turn churned users into recovered revenue?

</div>

<a class="rp-btn-primary" href="https://recurly.com/product/engage/" target="_blank">Book a quick demo →</a>
