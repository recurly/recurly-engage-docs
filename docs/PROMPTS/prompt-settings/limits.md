---
title: Limits
excerpt: >-
  Guide to configuring prompt delivery limits—impression, frequency, budget,
  user, and delivery caps—in Recurly Engage.
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
  <div class="rp-overview">Limits let you control how often, and to how many users, a prompt can be shown. Apply limits to an individual prompt, or use <a href="/recurly-engage/docs/global-limits" target="_blank">Global limits</a> for account-wide caps.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly Engage subscription plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>To create or update prompt limits, you must have <strong>Company</strong>, <strong>App Administrator</strong>, or <strong>App Member</strong> permissions in Recurly Engage.</li>
  <li>To update Global limits, you must have <strong>Company</strong> or <strong>App Administrator</strong> permissions in Recurly Engage.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>Global limits affect all prompts and require appropriate application-level configuration.</li>
</ul>

# Definition

<div class="rp-definition">A limit restricts prompt exposures based on impressions, user frequency, spendable budget, or user and delivery caps. Limits keep rollouts controlled and spending within budget.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-sack-dollar" aria-hidden="true"></i></div>
    <strong>Cost control</strong>
    <span>Prevent overspending by capping impressions or budget.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-users" aria-hidden="true"></i></div>
    <strong>Audience management</strong>
    <span>Avoid overexposure by limiting frequency per user or total deliveries.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-scale-balanced" aria-hidden="true"></i></div>
    <strong>Scalable governance</strong>
    <span>Use Global limits for consistent thresholds across all prompts.</span>
  </div>
</div>

# Key details

## Impression limit

An impression limit restricts the total number of times a prompt is shown to the targeted segment, regardless of user. Once the impression count is reached, the prompt stops displaying.


<Image src="https://files.readme.io/a7d13f1-image.png" align="center" width="75%" border={true} />


## Frequency cap

A frequency cap limits how many times an individual user can see the prompt within a defined period. For example, two impressions over 30 days means each user can view the prompt twice in a rolling 30-day window that starts from their first impression.


<Image src="https://files.readme.io/fb6c9f7-image.png" align="center" width="75%" border={true} />


## Budget limit

A budget limit sets a consumable budget that decreases each time a user takes the prompted action. Configure a total budget and a decrement value. For instance, a $10,000 budget with a decrement of $10 charges $10 per user interaction until funds are exhausted.


<Image src="https://files.readme.io/42214b6-image.png" align="center" width="75%" border={true} />


## User limit

A user limit caps the total number of unique users who can receive or act on the prompt. For example, a user limit of 1,000 ensures that only the first 1,000 eligible users see the prompt.


<Image src="https://files.readme.io/b726d62-image.png" align="center" width="75%" border={true} />


## Delivery limit

A delivery limit restricts the number of unique deliveries — instances when a user meets the trigger conditions and is eligible to see the prompt. A delivery limit of 1,000 delivers to the first 1,000 unique users who match the trigger, then stops.


<Image src="https://files.readme.io/9a7bf89-image.png" align="center" width="75%" border={true} />


<div class="rp-card">Want to set account-wide caps? Learn more in <a href="/recurly-engage/docs/global-limits" target="_blank">Global limits</a>.</div>
