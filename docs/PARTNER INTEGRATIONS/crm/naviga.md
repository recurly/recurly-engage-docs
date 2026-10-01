---
title: Naviga
excerpt: >-
  Configuration guide for the Naviga connector in Recurly Engage—setup and
  supported subscription actions for news and publishing platforms.
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
  <div class="rp-overview">Naviga Subscribe is a common backend for news and publishing customers. With Naviga Subscribe version 3.13 or later and NCS Circ 2018.5 SP1 or later, Recurly Engage can run 1-Click actions to manage subscriptions directly from prompts.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly Engage subscription plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have <strong>Company</strong> or <strong>App Administrator</strong> permissions in Recurly Engage.</li>
  <li>Your environment must run Naviga Subscribe v3.13 or later and NCS Circ 2018.5 SP1+.</li>
</ul>

# Definition

<div class="rp-definition">The Naviga connector integrates Recurly Engage with the Naviga Subscribe API, so you can check subscription status and create, start, or end subscriptions from prompts.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-list-check" aria-hidden="true"></i></div>
    <strong>Streamlined workflows</strong>
    <span>Trigger subscription checks and lifecycle actions without leaving your app.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-plug" aria-hidden="true"></i></div>
    <strong>Direct backend integration</strong>
    <span>Use Naviga's existing subscription backend for real-time updates.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-user-gear" aria-hidden="true"></i></div>
    <strong>User-centric prompts</strong>
    <span>Personalize prompts based on subscription state.</span>
  </div>
</div>

# Key details

## Supported actions

Use these actions within prompt configurations (such as Accept and Secondary Accept) to drive Naviga workflows:

| Action                         | Description                                 | API method                                                              |
| :----------------------------- | :------------------------------------------ | :---------------------------------------------------------------------- |
| Check Subscription             | Verify if a user has an active subscription | `GET /subscribe/v1/subscription/status?userId=<USER_ID>`                |
| Create Subscription            | Create a new subscription for a user        | `POST /subscribe/v1/subscription`                                       |
| Start Subscription             | Activate a pending subscription             | `POST /subscribe/v1/subscription/{subscriptionId}/activate`             |
| End Subscription               | Cancel or end an active subscription        | `POST /subscribe/v1/subscription/{subscriptionId}/cancel`               |
| Upgrade/Downgrade Subscription | Upgrade or downgrade an active subscription | `POST /subscription/update/upgrade` OR `/subscription/update/downgrade` |

These actions use the <a href="https://docs.navigaglobal.com/naviga-subscribe/additional-resources/subscribe-apis/subscribe-api" target="_blank">Naviga Subscribe API</a>. Contact your Customer Success Manager or <a href="mailto:support@recurly.com">[support@recurly.com](mailto:support@recurly.com)</a> for partnership details and advanced integration options.

<br />
