---
title: Sync user traits
excerpt: >-
  How to sync and import user attributes into Recurly Engage for targeted
  campaigns and personalized experiences.
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
  <div class="rp-overview">Learn how to select, format, and upload user traits to Recurly Engage so you can segment your audience and activate tailored workflows.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available to all customers on any Recurly Engage subscription plan</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have <strong>Administrator</strong> access in your Recurly Engage console.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>Trait imports run on a daily schedule unless you're using real-time Segment events.</li>
</ul>

# Definition

<div class="rp-definition">User traits are attributes — like plan type or billing status — that describe each customer. Syncing these traits lets Recurly Engage dynamically target users based on their behavior or profile data.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-bullseye" aria-hidden="true"></i></div>
    <strong>Targeted engagement</strong>
    <span>Deliver personalized messages and experiences based on real user data.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-chart-pie" aria-hidden="true"></i></div>
    <strong>Data-driven segmentation</strong>
    <span>Group customers by attributes like plan tier, billing date, or payment status.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-arrows-rotate" aria-hidden="true"></i></div>
    <strong>Automated workflows</strong>
    <span>Keep segments up to date with scheduled imports or real-time events.</span>
  </div>
</div>

# Key details

Depending on your use case, identify which user attributes you'll need and gather them in a CSV or via Segment events. For example:

<table class="rp-params">
  <tr class="rp-thead-row"><td>Item</td><td>Example</td><td>Interval</td><td>Source</td></tr>
  <tr><td>Current plan</td><td>Trial / Monthly / Annual</td><td>Daily</td><td>CSV</td></tr>
  <tr><td>Customer since</td><td>6 months</td><td>Daily</td><td>CSV</td></tr>
  <tr><td>Next bill date</td><td>2025-07-15</td><td>Daily</td><td>CSV</td></tr>
  <tr><td>Payment method</td><td>Credit card / iOS</td><td>Daily</td><td>CSV</td></tr>
  <tr><td>Last payment status</td><td>Failed</td><td>Real time</td><td>Segment event</td></tr>
</table>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Create your CSV</h4><p>Build a file with a header row matching your attribute names, plus the user identifiers you'll match on.</p></div>
  </div>
</div>

<ul class="rp-list">
  <li>Include a header row matching the attribute names.</li>
  <li>Populate each row with the user identifier (email or user ID) plus the trait columns.</li>
  <li>See the example file in the shared folder for formatting guidelines.</li>
</ul>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Upload your traits</h4><p>In Recurly Engage, go to <strong>Settings > Data imports</strong>, select <strong>User traits</strong>, and upload your CSV.</p></div>
  </div>
</div>

<ol>
  <li>Go to <strong>Settings > Data imports</strong>.</li>
  <li>Select <strong>User traits</strong> and upload your CSV.</li>
  <li>Schedule the import frequency — daily or one-off.</li>
</ol>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Add real-time events (optional)</h4><p>If you use Segment or another event source, configure it to send trait updates as they happen.</p></div>
  </div>
</div>

<div class="rp-callout rp-callout-tip">
  <div><strong><i class="fa-solid fa-lightbulb" aria-hidden="true"></i> Tip</strong>Real-time imports keep your segments reflecting the latest customer activity, without waiting for the daily CSV.</div>
</div>

A CSV isn't required if your campaign doesn't rely on attribute-based targeting. Learn more about <a href="https://docs.recurly.com/recurly-engage/docs/user-traits" target="_blank">importing user traits</a>.
