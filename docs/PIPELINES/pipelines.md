---
title: 'Overview: Pipelines'
excerpt: >-
  Overview of Recurly Engage Pipelines for lifecycle staging and behavior-based
  user segmentation.
deprecated: true
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
<div class="rp-page">
  <div class="rp-overview">Pipelines let you manage users across lifecycle stages or custom behavior loops in Recurly Engage. Visualize where your users are, and trigger targeted prompts that move them to the next stage.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly Engage subscription plans</div>
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

### Limitations

<ul class="rp-list">
  <li>Pipelines update automatically based on incoming trait and usage data. Allow time for the data to refresh.</li>
</ul>

# Definition

<div class="rp-definition">A pipeline is a multi-stage user lane, either lifecycle-based or custom, that organizes users by progression. You can attach prompts to a pipeline to drive movement between stages.</div>


<Image src="https://files.readme.io/effdb79-Screenshot_2024-04-30_at_6.53.20_PM.png" align="center" width="75%" border={true} />


# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-eye" aria-hidden="true"></i></div>
    <strong>Holistic user view</strong>
    <span>See where users are in their journey, from anonymous visitors to loyal customers.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-repeat" aria-hidden="true"></i></div>
    <strong>Behavioral reinforcement</strong>
    <span>Create custom pipelines to reward and reinforce desired usage patterns.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-diagram-project" aria-hidden="true"></i></div>
    <strong>Prompt orchestration</strong>
    <span>Attach prompts at each stage to guide users forward in the funnel.</span>
  </div>
</div>

# Key details

## Lifecycle pipelines

Recurly Engage includes three built-in pipelines.

### Member pipeline

1. **Anonymous**: Visitors to marketing pages.
2. **Trial**: Users in their trial period.
3. **Monthly**: Subscribers on a monthly plan.
4. **Premium**: Subscribers on a premium plan.
5. **Pending Cancel**: Canceled subscribers with continued access.
6. **Cancelled**: Users who have fully churned.

### Engagement pipeline

1. **New users**
2. **Repeat users**
3. **Regular users**
4. **Frequent users**
5. **Heavy users**

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>Based on visit and minute trends, you can further segment each stage into <span style={{fontWeight: "bold"}}>Engaged</span> (increasing activity), <span style={{fontWeight: "bold"}}>At Risk</span> (decreasing activity), or <span style={{fontWeight: "bold"}}>Everyone Else</span>.</div>
</div>

### Ecommerce pipeline

1. **Visitor**: Has not started checkout.
2. **Shopper**: Added items to cart.
3. **Checkout**: In the checkout process.
4. **Customer**: Completed purchase.

## Behavior pipelines

Create custom, behavior-driven pipelines to reinforce lifetime value patterns. For example, a "Watch More" pipeline:

1. Watched one episode
2. Watched two episodes
3. Watched three or more episodes

## Moving users between stages

You can attach prompts directly to any pipeline stage. For example, to convert **Engaged Trial** users into paying members before their trial expires:

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Add a prompt</h4><p>Select <span style={{fontWeight: "bold"}}>Add Prompt</span> on the <span style={{fontWeight: "bold"}}>Trial</span> stage.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Choose a style and sub-segment</h4><p>Select a prompt style and target the sub-segment ("Engaged Trial").</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Define a custom goal</h4><p>Define a custom goal and continue configuring the prompt as usual.</p></div>
  </div>
</div>

The remaining setup steps follow the same flow as <a href="/docs/prompts" target="_blank">creating a prompt</a>. Once live, prompts fire when users enter that pipeline stage, driving them toward the next segment.


<Image src="https://files.readme.io/05d43d1-Screenshot_2024-04-30_at_7.00.32_PM.png" align="center" width="75%" border={true} />
