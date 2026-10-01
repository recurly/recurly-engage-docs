---
title: Mixpanel
excerpt: >-
  Integration guide for the Mixpanel connector in Recurly Engage—setup and
  required credentials for event and user trait sync.
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
  <div class="rp-overview">The Mixpanel integration streams Recurly Engage prompt events and user traits into your Mixpanel project, so you can run analytics and segmentation based on in-app messaging interactions.</div>
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
  <li>You must have a Mixpanel account with Service Account credentials and project access.</li>
</ul>

# Definition

<div class="rp-definition">The Mixpanel connector authenticates with service account credentials and uses your project token to send prompt events and mapped user traits to Mixpanel in real time.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-chart-line" aria-hidden="true"></i></div>
    <strong>Unified analytics</strong>
    <span>Combine prompt interactions with existing Mixpanel event streams for comprehensive user behavior insights.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-users-viewfinder" aria-hidden="true"></i></div>
    <strong>Segmentation</strong>
    <span>Use Mixpanel's cohort and segmentation tools based on prompt engagement.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-bolt" aria-hidden="true"></i></div>
    <strong>Real-time sync</strong>
    <span>Forward events and user traits immediately upon prompt interactions.</span>
  </div>
</div>

# Key details

## What Recurly Engage sends

Once the integration is activated, Recurly Engage sends both prompt interaction events (impression, click, dismiss, and so on) and your configured user trait properties to Mixpanel.

Learn more:

<ul class="rp-list">
  <li><a href="https://developer.mixpanel.com/reference/service-accounts" target="_blank">Mixpanel Service Accounts</a></li>
  <li><a href="https://developer.mixpanel.com/reference/project-token" target="_blank">Mixpanel Project Token</a></li>
</ul>

## Required settings

Under **Settings → Integrations → External → Mixpanel**, provide:

* **Service Account Username**
* **Service Account Password**
* **Project Token**
* **Project ID**
