---
title: Churn Propensity Modeling
excerpt: >-
  Churn propensity modeling is a machine learning feature in Recurly Engage that
  assigns each subscriber a real-time risk score from 1–10 to surface at-risk
  subscribers before they cancel.
deprecated: false
hidden: true
metadata:
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">Churn propensity modeling surfaces at-risk subscribers before they cancel — giving you time to intervene with targeted retention campaigns, personalized offers, or guided experiences. Each subscriber receives a continuously updated risk score based on their behavioral engagement signals, and for Recurly Subscription Management (RSM) merchants, billing and payment history as well.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available to Recurly Engage customers</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Prerequisites</strong>Recurly Engage must be enabled on your account. The Churn Propensity Score feature must be activated by your Recurly customer success team before it appears in the Engage console. Approximately two weeks of subscriber data is required for meaningful predictions; full model accuracy is reached after approximately 12 weeks.</div>
</div>

<div class="rp-callout rp-callout-warning">
  <div><strong><i class="fa-solid fa-triangle-exclamation" aria-hidden="true"></i> Limitations</strong>Score distributions may take time to stabilize for new accounts or accounts that have recently onboarded a large number of subscribers. It's normal for some accounts to have few or no subscribers in the 8–10 risk range — this reflects the model's confidence threshold, not a misconfiguration. Merchants using Recurly Engage without RSM have access to a behavioral engagement-only model; the enhanced model incorporating billing and payment history requires RSM.</div>
</div>

# Definition

<div class="rp-definition">Churn Propensity Modeling is a machine learning feature within Recurly Engage that assigns each subscriber a real-time risk score from 1 to 10 — where 1 indicates low churn risk and 10 indicates very high churn risk. The model trains on your historical subscriber data to learn the behavioral patterns associated with churn, and establishes merchant-level baselines to ensure scores are contextually meaningful for your platform. Scores update automatically on every new engagement event, or every five days in the absence of activity.</div>

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Integration type</td><td>Data used in model</td></tr>
  <tr><td>Recurly Engage + RSM</td><td>Behavioral engagement signals + subscription billing and payment history</td></tr>
  <tr><td>Recurly Engage only</td><td>Behavioral engagement signals only</td></tr>
</table>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-shield-halved" aria-hidden="true"></i></div>
    <strong>Proactive retention</strong>
    <span>Identify at-risk subscribers before they make a cancellation decision, enabling timely and relevant outreach.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-layer-group" aria-hidden="true"></i></div>
    <strong>Unified data model</strong>
    <span>For RSM merchants, behavioral engagement signals are combined with billing data — including payment history, renewal trends, and pause and cancellation events — for a more complete picture of subscriber health.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-sliders" aria-hidden="true"></i></div>
    <strong>Granular risk scoring</strong>
    <span>The 1–10 scale gives you more flexibility than a binary flag, supporting tiered intervention strategies based on confidence level.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-users-viewfinder" aria-hidden="true"></i></div>
    <strong>Flexible segmentation</strong>
    <span>Combine churn scores with other subscriber attributes — such as geographic location, coupon usage history, or prior prompt interactions — to build highly targeted audiences.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-rotate" aria-hidden="true"></i></div>
    <strong>Dynamic score updates</strong>
    <span>Scores recalculate on every new engagement event and every five days of inactivity, keeping risk signals current without manual intervention.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Works across merchant types</strong>
    <span>All Recurly Engage merchants can use this feature regardless of RSM status. RSM merchants benefit from a richer dataset that improves model accuracy over time.</span>
  </div>
</div>

# Key details

## How to use churn propensity modeling

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Request feature enablement</h4><p>Contact your Recurly customer success team to activate the Churn Propensity Score feature on your account. It won't appear in the Engage console until it's been enabled.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Allow the model to accumulate data</h4><p>Once enabled, the model begins learning from incoming subscriber activity. Meaningful predictions emerge after approximately two weeks of data, with full model accuracy reached around 12 weeks.</p></div>
  </div>
</div>

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>If your account is brand new or has recently onboarded a large number of subscribers, expect score distributions to stabilize over time. It's also normal for some accounts to have few or no subscribers in the 8–10 range — this reflects the model's confidence threshold and is not a misconfiguration.</div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Create a segment using the churn score</h4><p>In the Recurly Engage console, navigate to Segments and build an audience based on the Churn Score attribute.</p></div>
  </div>
</div>

<ol>
  <li>Navigate to <strong>Segments</strong> in the Recurly Engage console.</li>
  <li>Select <strong>Add new segment</strong>.</li>
  <li>Under the <strong>Users</strong> section, locate the <strong>Churn Score</strong> attribute.</li>
  <li>Use the slider to define the score range you want to target — for example, 7–10 for high-risk subscribers.</li>
  <li>Optionally, add additional conditions to refine the audience, such as geographic filters, coupon usage history, or prior prompt interactions.</li>
  <li>Save the segment.</li>
</ol>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Associate the segment with a prompt or campaign</h4><p>Attach your saved segment to a prompt, guide, or retention campaign within Engage. Common use cases include surfacing a discount offer, initiating a cancel-save flow, or triggering a personalized re-engagement message for subscribers in a defined risk band.</p></div>
  </div>
</div>

<br />