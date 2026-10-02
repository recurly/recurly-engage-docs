---
title: Download data
excerpt: >-
  Configuration guide for the Download Data feature, which allows you to export
  Segment, Prompt, Guide, and activity data from Recurly Engage.
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
  <div class="rp-overview">Get your Recurly Engage data out and into the tools you already use. Download comma-separated values (CSV) exports of segments, prompts, and guides, or pull detailed prompt activity data for offline analysis.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly Engage plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have <span style={{fontWeight: "bold"}}>Company</span> or <span style={{fontWeight: "bold"}}>App Administrator</span> permissions in Engage.</li>
</ul>

# Definition

<div class="rp-definition">The <span style={{fontWeight: "bold"}}>Download Data</span> feature lets you export datasets — such as segment definitions, prompt configurations, and user activity — for offline analysis or integration with external systems.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Flexible exports</strong>
    <span>Get CSV files of segments, prompts, and guides for quick offline review.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Easy integration</strong>
    <span>Sync activity data with external reporting tools like Google Analytics or Amazon Web Services (AWS) S3.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Comprehensive auditing</strong>
    <span>Access detailed prompt interaction logs to understand user behavior and system performance.</span>
  </div>
</div>

# Key details

Engage can export data to various external systems. The simplest option is a CSV export of Segment, Prompt, and Guide data. More advanced options are also available, including receiving event data and syncing with an external reporting system like Google Analytics.

## Download from Pulse

See the <a href="/docs/can-i-download-prompt-interactions-data#detailed-activity-data" target="_blank">article on downloading prompt interaction data</a> for instructions on downloading activity data directly from Pulse.

## Download from AWS S3

Data from all user activity relating to running prompts is continuously saved to an AWS S3 bucket. You can import this data into your business intelligence (BI) system for offline analysis.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open User Traits</h4><p>Go to <span style={{fontWeight: "bold"}}>Settings &gt; User Traits</span>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Show your credentials</h4><p>Select <span style={{fontWeight: "bold"}}>“Show credentials”</span>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/60d5733d567e8ebe61eeef8a39345ccf6c7c78e00d792a40bf4f185f6db46108-aws-creds.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Log in and set the path</h4><p>Copy the AWS Bucket, Access Key, and Secret Key to log in. Replace <code>ingest</code> with <code>exports</code> within the Upload Location path. All filenames start with the activities prefix.</p></div>
  </div>
</div>

## Prompt activity data specifications

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Field</td><td>Description</td><td>Notes</td></tr>
  <tr><td><code>app_id</code></td><td>Engage app ID</td><td>Assigned by Engage</td></tr>
  <tr><td><code>app_name</code></td><td>Engage app name</td><td>Name as saved in Settings &gt; Application</td></tr>
  <tr><td><code>activity</code></td><td>Type of activity</td><td>Values: impression, timeout, dismiss, decline, click, exclude</td></tr>
  <tr><td><code>user_id</code></td><td>Unique ID of user</td><td></td></tr>
  <tr><td><code>anonymous_user_id</code></td><td>Identifier for a user when userId isn't available</td><td></td></tr>
  <tr><td><code>promo_id</code></td><td>Unique ID of prompt</td><td>Assigned by Engage</td></tr>
  <tr><td><code>promo_name</code></td><td>Name of prompt</td><td>As configured in the Engage console</td></tr>
  <tr><td><code>experiment_id</code></td><td>Unique ID of experiment</td><td>Only populated if there is a running experiment</td></tr>
  <tr><td><code>variation_id</code></td><td>Unique ID of variation</td><td>Only populated if there is a running experiment</td></tr>
  <tr><td><code>variation_name</code></td><td>Name of variation</td><td>Only populated if there is a running experiment</td></tr>
  <tr><td><code>survey_option</code></td><td>Survey option label</td><td>Only populated for survey prompts</td></tr>
  <tr><td><code>ts</code></td><td>Timestamp of when the activity occurred</td><td>Epoch</td></tr>
  <tr><td><code>pipeline_stage_start_id</code></td><td>Unique ID of pipeline stage</td><td>Populated as part of Pipeline_Transition activity (optional)</td></tr>
  <tr><td><code>pipeline_stage_start_name</code></td><td>Name of pipeline stage</td><td>Populated as part of Pipeline_Transition activity (optional)</td></tr>
  <tr><td><code>pipeline_stage_end_id</code></td><td>Unique ID of pipeline stage</td><td>Populated as part of Pipeline_Transition activity (optional)</td></tr>
  <tr><td><code>pipeline_stage_end_name</code></td><td>Name of pipeline stage</td><td>Populated as part of Pipeline_Transition activity (optional)</td></tr>
</table>
