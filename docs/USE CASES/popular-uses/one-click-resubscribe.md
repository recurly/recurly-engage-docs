---
title: 1-click resubscribe
excerpt: >-
  Configuration guide for the 1-Click Resubscribe use case, which enables
  churned users to reactivate their subscription with a single click.
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
  <div class="rp-overview">The 1-Click Resubscribe use case targets churned users visiting your site with a re-activation prompt. When their payment information is already on file, they can restart their subscription instantly — with an optional confirmation step to verify intent.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
    <a class="rp-toc-pill" href="#example"><span class="rp-toc-num">4</span>Example</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have <strong>Company</strong>, <strong>App Administrator</strong>, or <strong>App Member</strong> permissions in Recurly Engage.</li>
</ul>

# Definition

<div class="rp-definition">The 1-Click Resubscribe use case targets churned users visiting your site with a re-activation prompt. When their payment information is on file, they can restart their subscription instantly. You can also configure a second confirmation prompt (double opt-in) to verify intent.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-bolt" aria-hidden="true"></i></div>
    <strong>Effortless reactivation</strong>
    <span>Let users resume their subscription with a single click.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-arrow-trend-up" aria-hidden="true"></i></div>
    <strong>Revenue recovery</strong>
    <span>Recover 10%+ of churned users through on-site prompts.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-code-branch" aria-hidden="true"></i></div>
    <strong>Flexible flow</strong>
    <span>Add an optional double opt-in step to confirm reactivation.</span>
  </div>
</div>

# Key details

Target churned users visiting your site in real time with a re-activation prompt. If their card data is available in your subscriber system, they can reactivate in one click. You can configure an optional confirmation prompt to double-check intent.


<Image src="https://files.readme.io/c958740-Screenshot_2024-04-30_at_12.18.40_PM.png" align="center" width="75%" border={true} />


<div class="rp-callout rp-callout-tip">
  <div><strong><i class="fa-solid fa-lightbulb" aria-hidden="true"></i> Tip</strong>For best results, consider offering an incentive to the user for resubscribing.</div>
</div>

## Step-by-step

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Create your segments</h4><p>Create a <strong>Churned Users</strong> segment. Optionally, create a separate Dunning segment.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Create the prompt</h4><p>Create a <strong>Notification Prompt</strong> (<strong>Settings > Prompts</strong>).</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Customize the prompt</h4><p>Customize the headline, message, and dynamic variables, like first name.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Configure the reactivation action</h4><p>Under <strong>Add Action</strong>, select your billing platform and specify the reactivation plan.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Set the effective date (optional)</h4><p>Set the effective date for the plan change if you'd like one.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">6</div>
    <div><h4>Target Test Users</h4><p>Target the prompt to the <strong>Test Users</strong> segment.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">7</div>
    <div><h4>Set the trigger</h4><p>Set the trigger to fire on your homepage (for example, URL <code>/</code>).</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">8</div>
    <div><h4>Launch the prompt</h4></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">9</div>
    <div><h4>Add yourself as a test user</h4><p>Add your user ID to <strong>Test Users</strong> (<strong>Settings > Users > Test Users</strong>).</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">10</div>
    <div><h4>Verify the prompt</h4><p>Confirm the prompt appears when you visit your homepage.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">11</div>
    <div><h4>Roll out to production</h4><p>Update the targeting to include the <strong>Churned Users</strong> segment for production.</p></div>
  </div>
</div>

## Example

<div style={{position: "relative", paddingTop: "62.5%", marginBottom: "28px", borderRadius: "10px", overflow: "hidden"}}>
  <iframe src="https://www.loom.com/embed/42ea0c623c0e48b98d77e1d992ed0686?sid=fb0b44f8-127c-4072-a45a-8e0fa757f6a2"
    title="1-Click Resubscribe example walkthrough"
    allow="autoplay; fullscreen"
    allowtransparency="true"
    frameBorder="0"
    scrolling="no"
    allowFullScreen
    style={{position: "absolute", top: 0, left: 0, width: "100%", height: "100%", border: "none"}}></iframe>
</div>
