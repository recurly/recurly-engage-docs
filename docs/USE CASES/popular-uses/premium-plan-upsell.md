---
title: Premium plan adoption
excerpt: >-
  Configuration guide for the Premium Plan Adoption use case, which targets
  engaged users with contextual prompts to upgrade to premium plans or add-ons.
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
  <div class="rp-overview">Most subscription businesses rely on outbound email to promote premium plans and add-ons — effective for highly engaged users, but casual visitors need more context to see the value of upgrading. Recurly Engage takes an on-site, personalized approach instead: prompt users who haven't purchased an add-on or premium plan, using screen- or event-based triggers to deliver upgrade messaging exactly when it matters.</div>
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

<div class="rp-definition">The Premium Plan Adoption use case delivers targeted on-site prompts to users who meet your engagement criteria but haven't yet upgraded, using contextual triggers — page views or events — for maximum relevance.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-arrow-trend-up" aria-hidden="true"></i></div>
    <strong>Increased conversions</strong>
    <span>Reach users in context to motivate plan upgrades.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-user-pen" aria-hidden="true"></i></div>
    <strong>Personalized offers</strong>
    <span>Dynamically tailor messaging based on user behavior and variables, like first name.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-clock" aria-hidden="true"></i></div>
    <strong>Optimized timing</strong>
    <span>Trigger upgrade prompts on key screens or after specific actions to maximize impact.</span>
  </div>
</div>

# Key details

This scenario prompts users on your site who haven't yet purchased the add-on or premium plan, with contextual upgrade offers. Configure the trigger on relevant screens or events to make sure users see the right message at the right time.


<Image src="https://files.readme.io/b953f97-Screenshot_2024-04-22_at_4.48.39_PM.png" align="center" width="75%" border={true} />


## Guide

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Update your segment</h4><p>Modify the <strong>Engaged Users</strong> segment to include users on the target subscription plan.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Create the prompt</h4><p>Create a <strong>Popup Prompt</strong> (<strong>Settings > Prompts</strong>) and customize the headline, message, and dynamic variables, like first name.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Configure the upgrade action</h4><p>Under <strong>Add Action</strong>, select your <a href="https://docs.recurly.com/recurly-engage/docs/billing" target="_blank">billing</a> platform and specify the plan users should upgrade to.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Set the effective date (optional)</h4><p>Set the effective date for the plan change if you'd like one.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Target Test Users</h4><p>Target the prompt to the <strong>Test Users</strong> segment.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">6</div>
    <div><h4>Set the trigger</h4><p>Set the trigger to fire on the homepage (for example, URL <code>/</code>) or other key pages.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">7</div>
    <div><h4>Start the prompt</h4></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">8</div>
    <div><h4>Add yourself as a test user</h4><p>Add your user ID to <strong>Test Users</strong> (<strong>Settings > Users > Test Users</strong>).</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">9</div>
    <div><h4>Verify the prompt</h4><p>Confirm the prompt launches when you visit the homepage.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">10</div>
    <div><h4>Roll out to production</h4><p>Update the prompt's targeting to include <strong>Engaged Users</strong> for the production rollout.</p></div>
  </div>
</div>

## Example

<div style={{position: "relative", paddingTop: "62.5%", marginBottom: "28px", borderRadius: "10px", overflow: "hidden"}}>
  <iframe src="https://www.loom.com/embed/c977818bce834868ae954663a38083f2?sid=6e1c0360-be70-4276-ba3e-38d96ed60a1b"
    title="Premium Plan Adoption example walkthrough"
    allow="autoplay; fullscreen"
    allowtransparency="true"
    frameBorder="0"
    scrolling="no"
    allowFullScreen
    style={{position: "absolute", top: 0, left: 0, width: "100%", height: "100%", border: "none"}}></iframe>
</div>
