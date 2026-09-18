---
title: Create an experiment
excerpt: >-
  Step-by-step guide to creating and running A/B experiments on your prompts in
  Recurly Engage.
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
  <div class="rp-overview">Run multiple versions of a prompt against each other to see which one performs best. This guide walks you through setting a custom goal, building variations, allocating traffic, and launching your experiment.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available to all customers on any Recurly Engage subscription plan</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have <strong>Company</strong> or <strong>App Administrator</strong> permissions in Recurly Engage.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>At least one prompt must exist in <strong>draft</strong> or <strong>review</strong> status before you can create an experiment.</li>
</ul>

# Definition

<div class="rp-definition">An experiment runs multiple versions (variations) of a prompt against each other — optionally including a control group — to measure performance against custom goals and decide which version to deploy.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-chart-line" aria-hidden="true"></i></div>
    <strong>Data-driven decisions</strong>
    <span>Use real user interactions to choose the most effective prompt variant.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-flask" aria-hidden="true"></i></div>
    <strong>Controlled testing</strong>
    <span>Isolate a single change — copy, design, or trigger — to understand its impact.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-trophy" aria-hidden="true"></i></div>
    <strong>Seamless rollout</strong>
    <span>Promote the winning variation automatically when the experiment completes.</span>
  </div>
</div>

# Key details

## Guide

Experiments follow these steps.

### Add a custom goal (optional)

Define what success looks like — a click or a purchase, for example — before creating variations.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Add a tracker</h4><p>In Recurly Engage, go to <strong>Settings > Usage Tracker</strong> and add a new tracker.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/92f9bc4-image.png" align="center" width="75%" border={true} />



<Image src="https://files.readme.io/0aa0cf3-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Attach the goal to your prompt</h4><p>Return to your prompt and attach the custom goal under <strong>Goals</strong>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/b7ac98d-image.png" align="center" width="75%" border={true} />



<Image src="https://files.readme.io/ae3bdf1-image.png" align="center" width="75%" border={true} />


### Create the experiment

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Start a new experiment</h4><p>Open your prompt and click <strong>+ New experiment</strong>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/26772c2-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Name your experiment</h4><p>Give it a clear name — see the <a href="https://docs.recurly.com/recurly-engage/docs/experiments-1" target="_blank">overview on experiments</a> for naming best practices.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/d785a04-Screenshot_2024-04-24_at_19.03.27.png" align="center" width="75%" border={true} />


### Configure variations

**Default setup**: your experiment starts with the **Original** prompt. If you added a custom goal, you can also include a **Control** group to measure the impact of showing the prompt versus hiding it.


<Image src="https://files.readme.io/743630a-image.png" align="center" width="75%" border={true} />


**Add a variation**: click **Add variation**, name it to reflect the change (for example, "New headline"), and modify one or more aspects — text, design, triggers, or actions.


<Image src="https://files.readme.io/bc5027f-Screenshot_2024-04-24_at_19.17.57.png" align="center" width="75%" border={true} />


Use the editor to scroll down and adjust settings as needed.


<Image src="https://files.readme.io/c7be6b1-image.png" align="center" width="75%" border={true} />


### Allocate traffic

Set the percentage of users who see each variation — make sure the total adds up to 100%.


<Image src="https://files.readme.io/f175e0f-image.png" align="center" width="75%" border={true} />


### Launch and monitor

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Start the experiment</h4><p>Click <strong>Start experiment</strong> and confirm.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/db1802e-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Monitor performance</h4><p>Click-through and conversion rates update in real time, within minutes depending on traffic.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Deploy the winner</h4><p>When you're ready, click <strong>Use This</strong> on the winning variation to replace the control and end the experiment.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/5f30ea5-image.png" align="center" width="75%" border={true} />


That's it — your experiment is live, and you can review the results to make data-driven optimizations to your prompts.
