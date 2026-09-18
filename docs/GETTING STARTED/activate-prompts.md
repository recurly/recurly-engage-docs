---
title: Activate prompts
excerpt: >-
  How to move your prompts from draft to live in Recurly Engage, including QA
  review and full deployment.
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
  <div class="rp-overview">Once a prompt is built, it's ready to activate. Move it through a review phase with an internal test segment, then release it to your full audience — and manage its status at any point along the way.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available to all customers on any Recurly Engage subscription plan</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have <strong>Company</strong>, <strong>App Administrator</strong>, or <strong>App Member</strong> permissions in Recurly Engage.</li>
  <li>At least one prompt and the segments it needs must already exist.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>A prompt needs at least one trigger before it can run.</li>
  <li>Ended prompts can't be restarted, but you can clone them.</li>
</ul>

# Definition

<div class="rp-definition">Activating prompts means enabling your designed prompts — pop-ups, interstitials, notifications, or video prompts — first for testing, then for full audience delivery.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-flask" aria-hidden="true"></i></div>
    <strong>Safe QA</strong>
    <span>Preview and tweak your prompt with a small group before broad release.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-layer-group" aria-hidden="true"></i></div>
    <strong>Phased rollout</strong>
    <span>Control exactly when and to whom a prompt goes live.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-toggle-on" aria-hidden="true"></i></div>
    <strong>Dynamic lifecycle</strong>
    <span>Pause, restart, or end prompts without touching code.</span>
  </div>
</div>

# Key details

## Activation phases

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Review phase</h4><p>Enable your prompt on an internal segment, such as <a href="https://docs.recurly.com/recurly-engage/docs/test-users" target="_blank">Test Users</a>, and run final QA to preview live behavior and refine settings.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Active phase</h4><p>Attach all target segments to deploy the prompt at scale, then monitor performance and engagement.</p></div>
  </div>
</div>

## Placement methods

<div class="rp-nav-grid">

<Cards>
  <Card title="Recurly Engage Live tool">
    Use the interactive point-and-click console tool (web only), with guidance from your support contact.
  </Card>
  <Card title="Class identifiers">
    Work with your development team to add Recurly Engage IDs to specific elements for precise on-page placement.
  </Card>
</Cards>
</div>

## Managing prompt status

Once a prompt is live, you can **pause**, **restart**, or **end** it at any time — unless an experiment is running against it.

<div class="rp-callout rp-callout-warning">
  <div><strong><i class="fa-solid fa-triangle-exclamation" aria-hidden="true"></i> Warning</strong>If an experiment is running on a prompt, end the experiment before pausing the prompt to avoid conflicts.</div>
</div>
