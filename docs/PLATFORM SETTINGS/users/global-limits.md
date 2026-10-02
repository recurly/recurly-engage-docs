---
title: Global limits
excerpt: >-
  Configuration guide for the Global Limits tab, which allows you to apply
  account-wide holdout, frequency cap, impression limits, and overlay interval
  settings in Recurly Engage.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
<div class="rp-page">
  <div class="rp-overview">Control how often your users see prompts across your whole Pulse account. In Recurly Engage, global limits let you hold back a share of users, cap exposure over time, and pace overlay prompts on web.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly Engage plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have <span style={{fontWeight: "bold"}}>Company</span> or <span style={{fontWeight: "bold"}}>App Administrator</span> permissions in Engage.</li>
</ul>

# Definition

<div class="rp-definition">The <span style={{fontWeight: "bold"}}>Global Limits</span> tab lets you set account-wide constraints — such as holdout percentage, frequency cap, impression limit, and overlay interval — to control prompt exposure across your Pulse account.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Consistent experimentation</strong>
    <span>Ensure a controlled percentage of users never see prompts.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>User-friendly experience</strong>
    <span>Prevent overexposure by capping how often a user encounters prompts.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Resource management</strong>
    <span>Limit total prompt impressions to manage system load and budgets.</span>
  </div>
</div>

# Key details

This tab lets you apply limits to your Pulse account globally by setting a holdout percentage, frequency cap, impression limit, and overlay interval.


<Image src="https://files.readme.io/f4f061d7ef9fb6a4431a7729f086f644fc8e4be964a70e48329b84af7d870f63-image.png" align="center" width="75%" border={true} />


## Global holdout

The **Global Holdout** setting lets you set a percentage of users who never see any Engage prompts. For example, with the settings below, only 90% of your users across all segments are shown prompts.


<Image src="https://files.readme.io/d4d64b2-image.png" align="center" width="75%" border={true} />


## Global frequency cap

The **Global Frequency Cap** setting lets you set the maximum number of prompts a user can be shown within a specified time range. For example, with the settings below, a single user can see no more than 10 prompts within 30 days. After 30 days, the cap resets.


<Image src="https://files.readme.io/50c0908-image.png" align="center" width="75%" border={true} />


## Global impression limit

The **Global Impression limit** setting restricts the total number of times prompts are shown to your users. For example, setting it to 100,000 impressions limits the system to showing prompts only the first 100,000 times they're triggered. Once the limit is reached, prompts are paused automatically. You can also configure a warning to notify you when the global impression limit is approaching.


<Image src="https://files.readme.io/ad648f7-image.png" align="center" width="75%" border={true} />


## Overlay interval

The **Overlay Interval** setting lets you set a minimum interval between overlay prompt impressions on web (page triggers only). For example, if you set the interval to 5 minutes, your users won't see page-triggered overlay prompts on web more often than every 5 minutes.

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>The interval resets if the browser tab is closed.</div>
</div>


<Image src="https://files.readme.io/e9f0c59531668b8b7da64d915c0cc155e828c69edc4c1106ff079f8456972c88-image.png" align="center" width="75%" border={true} />


Once you've set the limits, click **Save changes** to apply them to your account.
