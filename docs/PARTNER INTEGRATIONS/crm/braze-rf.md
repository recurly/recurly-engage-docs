---
title: Braze
excerpt: >-
  Configuration guide for the Braze connector in Recurly Engage—API setup and
  supported user management actions.
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
  <div class="rp-overview">The Braze integration lets Recurly Engage add or update user records in Braze when users interact with your prompts, so you can use those profiles in your Braze campaigns.</div>
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
  <li>You must have a Braze account with REST API access enabled (App Group REST API Key).</li>
  <li>Your Braze instance's Base URL and API Key must be available.</li>
</ul>

# Definition

<div class="rp-definition">The Braze connector uses your Braze REST API credentials to add or update user records, mapping email addresses and optional aliases, when users interact with prompts.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-user-check" aria-hidden="true"></i></div>
    <strong>Synchronized user profiles</strong>
    <span>Automatically enroll or update users in Braze for downstream messaging.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-bullseye" aria-hidden="true"></i></div>
    <strong>Personalized engagement</strong>
    <span>Use prompt events to trigger Braze campaigns and segmentation.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-sliders" aria-hidden="true"></i></div>
    <strong>Centralized setup</strong>
    <span>Manage Braze credentials and actions within the Recurly Engage console.</span>
  </div>
</div>

# Key details

## Required settings

Under **Settings → Connectors → Braze**, provide:

* **Base URL**: Your Braze REST API endpoint (for example, `https://rest.iad-01.braze.com`).
* **API Key**: Your App Group REST API Key. See the <a href="https://www.braze.com/docs/api/basics/#app-group-rest-api-keys" target="_blank">Braze API Reference</a>.

## Supported actions

Use this action within prompt configurations to manage Braze user profiles:

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Action</td><td>Description</td><td>User dependencies</td><td>Additional instructions</td><td>Form inputs</td></tr>
  <tr><td><strong>Add a user with email address</strong></td><td>Adds a user record with an email address and optional alias to Braze</td><td>None</td><td>Enter the alias label in the prompt editor</td><td>required</td></tr>
</table>

Attach this action to a prompt interaction (for example, Accept) to automatically push the user's email and alias to Braze when they engage with your message.
