---
title: Segment traffic split
excerpt: >-
  A guide on Recurly Engage's traffic splitting feature. It explains how to A/B
  test different prompt experiences, like modals and banners, to optimize
  performance and conversion rates.
deprecated: false
hidden: false
metadata:
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">Segment traffic splitting lets you A/B test different prompt experiences by distributing a segment's traffic across multiple prompts. Compare formats head to head, such as a modal and an inline banner. Unlike <a href="https://docs.recurly.com/recurly-engage/docs/create-an-experiment#/" target="_blank">experiments</a>, which test variations within a single prompt, traffic splits let you test across different prompt types.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

# Definition

<div class="rp-definition">A segment traffic split distributes a segment's traffic across multiple prompts so you can compare how different prompt types perform. Each user is assigned to a group by percentage range and stays in that group.</div>

# Key benefits

<div class="rp-benefits rp-benefits-2x2">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-chart-column" aria-hidden="true"></i></div>
    <strong>Data-driven decisions</strong>
    <span>Move beyond guesswork by comparing how different prompt types engage your audience, so you can make informed choices that drive the best results.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-code-compare" aria-hidden="true"></i></div>
    <strong>Direct comparison</strong>
    <span>Experiments test variations within a single prompt. Traffic splits compare fundamentally different experiences, such as a modal and a banner, to show which performs better.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-arrow-trend-up" aria-hidden="true"></i></div>
    <strong>Maximize conversions</strong>
    <span>Collect performance data and use it to maximize conversions. For example, show a modal to the first 30% of your target segment and an inline banner to the remaining 70%, then analyze which experience drives higher engagement.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-user-shield" aria-hidden="true"></i></div>
    <strong>Control group</strong>
    <span>Set a control group by holding back a percentage of users in a segment who are never targeted.</span>
  </div>
</div>

# Key details

To implement a segment traffic split, follow these steps.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Confirm your Recurly Engage access</h4><p>Make sure you're an active Recurly Engage member. If you're not, <a href="https://recurly.com/product/engage/" target="_blank">book a demo</a>.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Open Segments</h4><p>Go to the <span style={{fontWeight: "bold"}}>Segments</span> section in Pulse, the Recurly Engage management console.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Select a segment</h4><p>Select the segment type you'd like to split.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/e409c776c04af53195f1da755493a6b4a5a2b0efc5c7c09e61e9909def8e3e03-unnamed.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Assign traffic to a prompt</h4><p>In the segment detail view, you'll see all of the prompts where the selected segment is active. Select the <span style={{fontWeight: "bold"}}>Assign Traffic</span> button on the prompt.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/244de544d0c37c8688ecf827078bc439d6c6c79baa10623d0a82eae334d87995-segment_split_2.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Set the split for each prompt</h4><p>For the selected prompt, set the segmentation split amount. Repeat this step for the second prompt you want to split, setting the amount for each prompt type.</p></div>
  </div>
</div>

<div class="rp-callout rp-callout-important">
  <div><strong><i class="fa-solid fa-circle-exclamation" aria-hidden="true"></i> Important</strong>Once a user is assigned to a group, they always remain in that group, based on a bucketing methodology.</div>
</div>

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Example</strong>For the first group, set the split to <code>0-50</code>. For the second group, set the split to <code>51-100</code>.</div>
</div>


<Image src="https://files.readme.io/ade828ff41c3d1f4fcf50723df1c3cce7d32ff92f6a8d22a3f711a52a9bdaa6b-segment_split_3.png" align="center" width="75%" border={true} />



<Image src="https://files.readme.io/18cacc2dd7ae5768b6ef9703fbb32eab55f1b74ea629747a778e4c7eb639b7a1-segment_split_4.png" align="center" width="75%" border={true} />


<br />

<br />
