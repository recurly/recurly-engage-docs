---
title: Recurly.js / HAM / Checkout
excerpt: >-
  Learn how Recurly Engage is automatically available in Hosted Account
  Management, Recurly Checkout, and Recurly.js, and how to install the tag
  manually.
deprecated: false
hidden: false
metadata:
  description: >
    Information on Recurly Engage's automatic integration with Recurly.js,
    Hosted Account Management, and Checkout. It explains how this integration
    enables churn prevention and abandoned cart use cases with minimal
    engineering effort.
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">If you use Recurly Subscription Management (RSM), Recurly Engage is built into your hosted pages and Recurly.js. This page explains what's included and how to get started.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

# Definition

<div class="rp-definition">Recurly Engage is a low-code platform that helps businesses manage and optimize subscriber engagement. For RSM customers, once your Recurly Engage account is enabled, it's automatically available across Recurly.js, Hosted Account Management, and Recurly Checkout. You can start implementing core use cases like Cancel Save and Involuntary Churn right away, with no additional engineering effort.</div>


<Image src="https://files.readme.io/a4db3dcdd83acc1b07904125149de9ec922be851bc2b6695ddc4550af1d58fe3-Screenshot_2025-09-12_at_1.25.37_PM.png" align="center" width="75%" border={true} />


# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-user-gear" aria-hidden="true"></i></div>
    <strong>Hosted Account Management</strong>
    <span>Recurly Engage is automatically enabled on Hosted Account Management pages. Target existing subscribers to reduce involuntary churn, offer cancel-save incentives, or promote plan upgrades.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-cart-shopping" aria-hidden="true"></i></div>
    <strong>Recurly Checkout</strong>
    <span>Recurly Engage is pre-integrated into Recurly Checkout pages to optimize your conversion funnel. It supports abandoned cart recovery, cross-sells, and upsells, helping you drive new visitors and improve checkout completion rates.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-code" aria-hidden="true"></i></div>
    <strong>Recurly.js</strong>
    <span>If you use Recurly.js to build custom account and checkout experiences, the Engage integration is included automatically wherever Recurly.js is installed. It's a no-code way to add in-app messaging on payment and checkout pages to address abandoned carts, prevent payment failures, and run upsell campaigns.</span>
  </div>
</div>

This deep integration lets you fully customize Engage prompts to suit your business needs across these critical pages.


<Image src="https://files.readme.io/c383fd83e685b78808654a4a6d27be7dd52e793b9678c71888f3e7f4f98fea16-Screenshot_2025-09-12_at_1.27.52_PM.png" align="center" width="75%" border={true} />


# Key details

After your Recurly Account Manager enables your Recurly Engage account, follow these steps to start using the integration.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Follow the integration guide</h4><p>Follow the <a href="https://docs.recurly.com/recurly-subscriptions/docs/recurly-engage-integration" target="_blank">official Recurly Engage Integration Guide</a> to complete the initial setup of your Recurly Engage account.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Use the built-in functionality</h4><p>When you complete the integration guide, Recurly Engage is automatically enabled on your Hosted Account Management pages, Recurly Checkout, and any pages where Recurly.js is installed. These core use cases need no additional engineering effort.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Install the tag manually (optional)</h4><p>To extend Recurly Engage to additional site pages, such as your product catalog or marketing content, manually install the Recurly Engage JavaScript tag (<code>redfast.js</code>) on those pages.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Manage multiple tags</h4><p>If you use Recurly.js and manually install the <code>redfast.js</code> tag, we recommend disabling the automatic <code>redfast.js</code> installation to prevent duplication.</p></div>
  </div>
</div>

The system deduplicates tags, but managing a single tag is the best practice. The system always uses the first tag it encounters. <a href="https://docs.recurly.com/recurly-subscriptions/v1.2/docs/engage#/" target="_blank">Learn more about disabling Engage</a>.

```html
<head>
  <!-- auto installed when Recurly.js is installed, ideally disable, but we dedupe –>
  <script src="https://00c2a588-6f6c-454a-950a-bbfaae614b3b.redfastlabs.com/assets/redfast.js" async>		</script> 

  <!-- manually installed by you or added via google/tealium tag manager →
  <script src="https://00c2a588-6f6c-454a-950a-bbfaae614b3b.redfastlabs.com/assets/redfast.js" async>		</script>
</head>

```

<br />

<br />
