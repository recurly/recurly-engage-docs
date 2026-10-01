---
title: Experiments
excerpt: >-
  Guide to creating and running A/B tests (experiments) on your prompts in
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
  <div class="rp-overview">Experiments let you test multiple variations of a prompt, such as copy, design, triggers, and actions, to find the version that performs best against your conversion goals.</div>
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
  <li>Only one active experiment can run per prompt at a time. Historical experiments remain accessible.</li>
  <li>We recommend a minimum of 30 users and five conversions per variation for statistical reliability.</li>
</ul>

# Definition

<div class="rp-definition">An experiment divides traffic among a prompt's variations, including an optional control group, and measures conversions with statistical tests to determine a winning configuration.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-chart-column" aria-hidden="true"></i></div>
    <strong>Data-driven optimization</strong>
    <span>Use real user interactions to choose the best-performing variation.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-flask" aria-hidden="true"></i></div>
    <strong>Controlled testing</strong>
    <span>Isolate single changes, such as title, imagery, or behavior, to understand their impact.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-trophy" aria-hidden="true"></i></div>
    <strong>One-click rollout</strong>
    <span>Promote the winning variation to replace the original prompt when the experiment ends.</span>
  </div>
</div>

# Key details

## What experiments can modify

<ul class="rp-list">
  <li>Prompt title and message body</li>
  <li>Call-to-action text and behaviors</li>
  <li>Images, styling, and layout</li>
  <li>Triggers, schedules, and actions (including 1-click workflows)</li>
</ul>

## Traffic allocation

Assign any percentage of visitors to each variation and to a <span style={{fontWeight: "bold"}}>Control</span> group (users who see no prompt). Control group users are still measured for conversion against your custom goal.


<Image src="https://files.readme.io/e053b1d-image.png" align="center" width="75%" border={true} />


## Statistical analysis

Experiments use a Z-test to compare variation conversion rates against the control. To detect a meaningful lift (for example, an improvement greater than 5%), each variation should see at least 30 users and five conversions. Depending on your baseline rate, that often means hundreds or thousands of users.

When statistical significance is reached, select <span style={{fontWeight: "bold"}}>Use This</span> to end the experiment and update your baseline prompt to the winning variation.

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>Z-test significance indicates superiority over the control only. It doesn't compare variations against each other. We plan to support Bayesian methods in the future.</div>
</div>


<Image src="https://files.readme.io/f2b3598-image.png" align="center" width="75%" border={true} />


## Create and run an experiment

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Select a prompt</h4><p>Navigate to <span style={{fontWeight: "bold"}}>Prompts</span> and select the prompt you want to experiment on.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/23131d0-Screenshot_2024-04-24_at_18.58.50.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Start a new experiment</h4><p>Scroll to the <span style={{fontWeight: "bold"}}>Experiments</span> section and select <span style={{fontWeight: "bold"}}>+ New Experiment</span>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/0a15434-Screenshot_2024-04-24_at_19.02.02.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Name the experiment</h4><p>Enter a clear experiment name.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/d785a04-Screenshot_2024-04-24_at_19.03.27.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Add a control group (optional)</h4><p>If you have a custom goal configured, add a <span style={{fontWeight: "bold"}}>Control</span> group. It measures baseline conversions without showing a prompt.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/7c0ec9e-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Add a variation</h4><p>Select <span style={{fontWeight: "bold"}}>Add variation</span>, name it to reflect the change (for example, "New headline"), and modify the title, copy, imagery, triggers, or actions.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/bc5027f-Screenshot_2024-04-24_at_19.17.57.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">6</div>
    <div><h4>Configure the variation</h4><p>Configure the variation details by editing directly in the prompt editor.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/c7be6b1-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">7</div>
    <div><h4>Allocate traffic</h4><p>Allocate traffic percentages to each variation and the control, making sure they total 100%.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/f175e0f-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">8</div>
    <div><h4>Start the experiment</h4><p>Select <span style={{fontWeight: "bold"}}>Start experiment</span> and confirm to begin dividing traffic.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/db1802e-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">9</div>
    <div><h4>Monitor the experiment</h4><p>View users per variation, conversions, and conversion rates in real time for in-progress experiments.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/5f30ea5-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">10</div>
    <div><h4>Promote the winning variation</h4><p>When a variation demonstrates statistical significance, select <span style={{fontWeight: "bold"}}>Use This</span> to end the experiment and promote that variation as your new baseline.</p></div>
  </div>
</div>

## Edit live experiments

You can make minor updates to a running experiment's variants, such as copy changes or action updates, without stopping and restarting the experiment. This is useful for minor adjustments that are unlikely to affect the experiment's core metrics.

To use this feature, enable the **is live editable** option when you set up a new experiment. This setting is disabled by default.

Once the experiment is live, you can edit all editable variants, including the original variant's triggers and actions, directly from the main prompt screen.


<Image src="https://files.readme.io/74ee8dfbd552423dfb3e237e1e287e0f18d8708bb336c57a64caf2910a2be1a5-Screenshot_2025-09-23_at_1.55.59_PM.png" align="center" width="75%" border={true} />


## Experiment reporting

Experiment reporting lets you download a comma-separated values (CSV) file with detailed data from your experiments, so you can analyze and report on results.

<ul class="rp-list">
  <li><strong>Data availability</strong>: Export experiment data for a specific time frame from the Settings section of the application. The export includes data for currently running experiments and for any completed experiments that overlapped with the selected date range.</li>
  <li><strong>Data content</strong>: The exported CSV file includes only experiment-specific data, not general prompt data. For completed experiments, the export provides the total stats for the entire experiment run. For running experiments, the stats are scoped to the specified time frame.</li>
</ul>

***

📋 TODO before publishing:

- [ ] Confirm the "We plan to support Bayesian methods in the future" note is still accurate before publishing.
