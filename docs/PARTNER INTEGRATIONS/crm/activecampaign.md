---
title: ActiveCampaign
excerpt: >-
  Configuration guide for the ActiveCampaign connector in Recurly Engage—API
  setup and supported automation actions.
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
  <div class="rp-overview">The ActiveCampaign integration lets you add or update contacts and manage lists and automations directly from Recurly Engage prompts, using your ActiveCampaign marketing workflows.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly Engage subscription plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have <strong>Company</strong> or <strong>App Administrator</strong> permissions in Recurly Engage.</li>
  <li>You must have an ActiveCampaign account with API access enabled.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>Make sure your ActiveCampaign subscription allows API usage and automations.</li>
</ul>

# Definition

<div class="rp-definition">The ActiveCampaign connector synchronizes contact data and exposes actions (such as adding contacts, subscribing to lists, and triggering automations) from within your in-app or web prompts.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-user-plus" aria-hidden="true"></i></div>
    <strong>Automated contact flows</strong>
    <span>Enroll users into marketing lists and automations.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-envelope" aria-hidden="true"></i></div>
    <strong>Personalized engagement</strong>
    <span>Trigger tailored email or SMS campaigns based on user interactions.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-window-maximize" aria-hidden="true"></i></div>
    <strong>Unified interface</strong>
    <span>Manage marketing workflows without leaving the Recurly Engage console.</span>
  </div>
</div>

# Key details

## Required settings

Under **Settings > Connectors > ActiveCampaign**, provide:

* **API Key**: Obtain it from your ActiveCampaign account. See <a href="https://help.activecampaign.com/hc/en-us/articles/207317590-Getting-started-with-the-API#getting-started-with-the-api-0-0" target="_blank">Getting started with the API</a>.
* **Subdomain**: Your ActiveCampaign account subdomain (for example, `myaccount` in `myaccount.api-us1.com`).

## Supported actions

Use these actions within prompt configurations to drive marketing automations:

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Action</td><td>Description</td><td>Additional instructions</td><td>Form inputs</td></tr>
  <tr><td><strong>Add Contact</strong></td><td>Add or update a user record in ActiveCampaign contacts.</td><td>None</td><td>Use Form Inputs to capture contact fields if needed</td></tr>
  <tr><td><strong>Add to List</strong></td><td>Subscribe the user to a specified contact <a href="https://help.activecampaign.com/hc/en-us/articles/5772650812316-Where-can-I-find-my-lists" target="_blank">list</a>.</td><td>None</td><td>Select the desired List ID from the dropdown</td></tr>
  <tr><td><strong>Add to Automation</strong></td><td>Enroll the user into an <a href="https://help.activecampaign.com/hc/en-us/articles/218788657-What-are-automations-in-ActiveCampaign-An-overview" target="_blank">automation</a>.</td><td>None</td><td>Select the Automation ID from the dropdown</td></tr>
</table>

Attach these actions to prompt interactions (Accept, Secondary Accept, and so on) to automate your marketing campaigns directly from user prompts.
