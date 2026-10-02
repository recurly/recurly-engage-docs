---
title: Google Analytics
excerpt: >-
  Configuration guide for integrating Recurly Engage with Google Analytics
  Measurement Protocol via API actions.
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
  <div class="rp-overview">Send prompt and experience events from Recurly Engage to Google Analytics, so you can see how users interact with prompts next to the rest of your site analytics. You set it up in the Engage console with an API action, with no middleware required.</div>
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
  <li>A valid Google Analytics property with Measurement Protocol enabled.</li>
</ul>

# Definition

<div class="rp-definition">The <span style={{fontWeight: "bold"}}>Google Analytics</span> integration lets you send prompt and experience events from Engage to Google Analytics, using API actions configured as POST requests to the Measurement Protocol endpoint.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Richer analytics</strong>
    <span>Track prompt interactions alongside other site events in Google Analytics.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Custom reporting</strong>
    <span>Use dynamic parameters to break down user engagement data the way you need it.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Easy setup</strong>
    <span>Configure actions in the Engage console without additional middleware.</span>
  </div>
</div>

# Key details

## Create an action

\[TODO: Dev/PO review — possible issue: the endpoint and the `tid` (Tracking ID) parameter follow the Universal Analytics Measurement Protocol, which Google has retired. Confirm this still works with Google Analytics 4.]

Follow the steps to create an API action. The action must be a POST request to the Google Analytics Measurement Protocol endpoint: `https://www.google-analytics.com/collect`.


<Image src="https://files.readme.io/ebf7cc4-Google_Analytics_Custom_Action.png" align="center" width="75%" border={true} />


## Specify the payload

Add parameters to the payload, static or dynamic, using Measurement Protocol fields. Required parameters include:

* `v` — Protocol version
* `tid` — Web property ID (Tracking ID)
* `t` — Hit type (for example, `event`)

Optional parameters include:

* `cid` — Client ID
* `ea` — Event action
* `el` — Event label

For a full list of supported parameters, see the <a href="https://developers.google.com/analytics/devguides/collection/protocol/v1/parameters" target="_blank">Measurement Protocol Parameter Reference</a>.

## Add the action to a prompt or experience

Once the action is defined, attach it to a prompt or experience by following the steps to <a href="actions-1" target="_blank">add the action</a>.
