---
title: Engagement categories
excerpt: >-
  Learn how to assign specific use-case categories to prompts during
  configuration to ensure accurate success rate tracking and reporting.
deprecated: false
hidden: false
link:
  new_tab: false
metadata:
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">The prompt classification system lets you define the intended use case for every prompt you configure. Choose a category, such as Acquisition or Retention, from the dropdown when you create or edit a prompt. Every prompt then carries a clear intent from launch, whether or not it results in a transaction.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

# Definition

<div class="rp-definition">An engagement category is a label on a prompt that describes its intended use case, such as acquiring, retaining, or winning back users.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-chart-line" aria-hidden="true"></i></div>
    <strong>Accurate success rate tracking</strong>
    <span>Classifying prompts at the configuration stage lets you calculate the Prompt Success Rate for specific campaign types, such as Acquisition versus Upgrade. This closes the data gap where only successful, revenue-generating prompts were categorized.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-sack-dollar" aria-hidden="true"></i></div>
    <strong>Enhanced revenue analysis</strong>
    <span>Defining a prompt's intent allows more precise Recovered Revenue analysis for Recurly Subscription Management (RSM) merchants. Business Intelligence teams can attribute revenue to specific strategies, which gives sales and strategy conversations a clearer picture of return on investment (ROI).</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-tag" aria-hidden="true"></i></div>
    <strong>Clear intent from launch</strong>
    <span>Every prompt is tagged with its intent from the moment it launches.</span>
  </div>
</div>

# Key details

## Assign a category

When you configure a new prompt, you'll see a required dropdown menu labeled **Prompt Category**. You must select one of the following intent types:

<ul class="rp-list">
  <li><strong>Acquisition</strong>: Encourages new user conversion.</li>
  <li><strong>Retention</strong>: Keeps existing users active.</li>
  <li><strong>Win Back</strong>: Re-engages lapsed users.</li>
  <li><strong>Upgrade</strong>: Moves users to a higher tier or product.</li>
  <li><strong>Engagement</strong>: Promotes general interaction and usage.</li>
</ul>

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>Default generated guides and prompts have these categories assigned automatically.</div>
</div>

## Update existing prompts and guides

For prompts and guides created before categories were introduced, assigning an engagement category is optional. You don't need to tag your entire library right away. To keep your reporting data as accurate as possible, you can assign categories to existing content at any time.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open the detail screen</h4><p>Navigate to the Detail Screen of the prompt or guide.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Select a category</h4><p>Select the appropriate engagement category from the dropdown menu.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Save your changes</h4><p>Save your changes to begin tracking that item's intent in your success rate metrics.</p></div>
  </div>
</div>

## Behavior with guides

If a prompt is associated with a guide, categorization follows strict inheritance rules to keep things consistent:

* **Adding to a guide**: When you add a prompt to a guide, the prompt automatically inherits the guide's category, overriding any previous selection.
* **Inherited status**: While a prompt is part of a guide, its category is inherited and you can't change it manually. It must match the guide.
* **Removing from a guide**: When you remove a prompt from a guide, it keeps the category it inherited from that guide. You can then update it manually if necessary.
