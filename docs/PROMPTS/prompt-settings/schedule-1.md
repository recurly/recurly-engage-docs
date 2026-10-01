---
title: Schedule
excerpt: >-
  How to schedule prompts or guides to run only during specific dates, days, and
  times in Recurly Engage.
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
  <div class="rp-overview">A schedule controls when a prompt or guide is active in Recurly Engage. Set a date range, choose the weekdays it runs, and narrow it to specific hours so it turns on and off automatically.</div>
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
  <li>Times are interpreted in the selected time zone (user's or app's).</li>
</ul>

# Definition

<div class="rp-definition">A schedule is a configuration that limits when a prompt or guide is active. It uses three nested settings: <span style={{fontWeight: "bold"}}>Date Window</span>, <span style={{fontWeight: "bold"}}>Day Part</span>, and <span style={{fontWeight: "bold"}}>Time Part</span>.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-bullseye" aria-hidden="true"></i></div>
    <strong>Precision timing</strong>
    <span>Target promotions or messages during high-traffic windows.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-gears" aria-hidden="true"></i></div>
    <strong>Automated control</strong>
    <span>Automatically enable and disable prompts without manual intervention.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-calendar-days" aria-hidden="true"></i></div>
    <strong>Flexible recurrence</strong>
    <span>Combine date ranges, weekdays, and hourly windows for complex schedules.</span>
  </div>
</div>

# Key details

## Date window

The <span style={{fontWeight: "bold"}}>Date Window</span> defines the overall start and end dates for your prompt or guide. The item is active from 12:01 AM on the start date to 11:59 PM on the end date. Leave the dates blank to run indefinitely.


<Image src="https://files.readme.io/bc5ca6e-image.png" align="center" width="75%" border={true} />


## Day part

The <span style={{fontWeight: "bold"}}>Day Part</span> setting lets you choose the specific weekdays when the prompt or guide is active. If you don't set it, all days are included.


<Image src="https://files.readme.io/bfd314d-image.png" align="center" width="75%" border={true} />


## Time part

The <span style={{fontWeight: "bold"}}>Time Part</span> setting defines the specific hours within each selected day when the prompt or guide appears. Time parts are a sub-setting of day parts, so select your days first. You must also choose whether to enforce the schedule in the <span style={{fontWeight: "bold"}}>user's time zone</span> or the <span style={{fontWeight: "bold"}}>app's time zone</span>.


<Image src="https://files.readme.io/a77ae00-image.png" align="center" width="75%" border={true} />


<div class="rp-callout rp-callout-warning">
  <div><strong><i class="fa-solid fa-triangle-exclamation" aria-hidden="true"></i> Warning</strong>Make sure your time windows don't overlap midnight unless you intend the schedule to wrap across days.</div>
</div>


<Image src="https://files.readme.io/fcbe451-image.png" align="center" width="75%" border={true} />


<div class="rp-callout rp-callout-tip">
  <div><strong><i class="fa-solid fa-lightbulb" aria-hidden="true"></i> Tip</strong>Use these settings together to create complex schedules. For example, show a weekend-only special offer every Friday and Saturday evening between 6 PM and 11 PM, from May 1, 2024, through December 31, 2024.</div>
</div>
