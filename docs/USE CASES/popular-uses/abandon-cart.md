---
title: Abandon cart
excerpt: >-
  Configuration guide for the Abandon Cart use case, which targets visitors who
  leave items in their cart and encourages them to complete checkout.
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
  <div class="rp-overview">More than 95% of visitors to your site won't convert on their first visit. The Abandon Cart use case recovers lost revenue by prompting returning visitors to resume their checkout — recovering 40% or more of abandoned carts.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have <strong>Company</strong>, <strong>App Administrator</strong>, or <strong>App Member</strong> permissions in Recurly Engage.</li>
</ul>

# Definition

<div class="rp-definition">The Abandon Cart use case detects returning visitors who left items in their cart and shows a prompt guiding them back to complete their purchase.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-arrow-trend-up" aria-hidden="true"></i></div>
    <strong>Revenue recovery</strong>
    <span>Recover a significant portion of abandoned carts by re-engaging visitors.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-bullseye" aria-hidden="true"></i></div>
    <strong>Contextual prompts</strong>
    <span>Trigger messages only when users show exit intent during checkout.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-user-pen" aria-hidden="true"></i></div>
    <strong>Personalized messaging</strong>
    <span>Use dynamic variables, like first name, to make the message more relevant.</span>
  </div>
</div>

# Key details

With this approach, you can recover 40% or more of users with abandoned carts when they return to your site.


<Image src="https://files.readme.io/50f04cb-Screenshot_2024-04-30_at_4.09.36_PM.png" align="center" width="75%" border={true} />


<div class="rp-callout rp-callout-tip">
  <div><strong><i class="fa-solid fa-lightbulb" aria-hidden="true"></i> Tip</strong>For best results, consider offering an incentive to complete the checkout process.</div>
</div>

## Guide

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Create your segment</h4><p>Sync visitor attributes related to cart abandonment and create an <strong>Abandoned Cart</strong> segment, or use the built-in <strong>Anonymous Users</strong> segment.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Create the prompt</h4><p>Create a <strong>Popup Prompt</strong> (<strong>Settings > Prompts</strong>) — see <a href="https://docs.recurly.com/recurly-engage/docs/create-a-pop-up-recurly-engage" target="_blank">Create a pop-up</a> — and customize the headline, message, and any dynamic variables.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Configure the redirect action</h4><p>Under <strong>Add Action</strong>, configure a redirect to your cart URL.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Target Test Users</h4><p>Target the prompt to the <strong>Test Users</strong> segment.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Set the trigger</h4><p>Set the trigger to fire on your checkout flow (for example, URL pattern <code>/checkout/*</code>) and enable the <strong>Exit Intent</strong> advanced trigger.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">6</div>
    <div><h4>Launch the prompt</h4></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">7</div>
    <div><h4>Add yourself as a test user</h4><p>Add your user ID to <strong>Test Users</strong> (<strong>Settings > Users > Test Users</strong>).</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">8</div>
    <div><h4>Verify the prompt</h4><p>Confirm the prompt appears when exit intent is detected during checkout.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">9</div>
    <div><h4>Roll out to production</h4><p>Update the prompt's targeting segment to <strong>Abandoned Cart</strong> for the production deployment.</p></div>
  </div>
</div>
