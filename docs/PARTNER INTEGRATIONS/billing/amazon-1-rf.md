---
title: Amazon
excerpt: >-
  Setup guide for the Amazon Device Messaging (ADM) connector in Recurly Engage
  Push Prompts.
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
  <div class="rp-overview">The Amazon integration lets you send push notifications from Recurly Engage to Fire OS devices, using your existing Amazon Device Messaging (ADM) credentials.</div>
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
  <li>Your app must integrate the Recurly Engage software development kit (SDK) on the target platform.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>Push notifications are supported only on Fire OS devices with ADM support.</li>
</ul>

# Definition

<div class="rp-definition">The ADM connector imports your ADM credentials into Recurly Engage, so you can deliver push notifications through Amazon's push infrastructure.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-tablet-screen-button" aria-hidden="true"></i></div>
    <strong>Native device reach</strong>
    <span>Send push notifications to Fire tablets and Fire TV devices.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-key" aria-hidden="true"></i></div>
    <strong>Simple configuration</strong>
    <span>Use your existing ADM credentials without additional infrastructure.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-diagram-project" aria-hidden="true"></i></div>
    <strong>Integrated workflows</strong>
    <span>Include push prompts as part of your Recurly Engage campaigns.</span>
  </div>
</div>

# Key details

## Required information

Provide the following in **Settings > Push Credentials**:

* **ADM Client ID**
* **ADM Client Secret**

Follow Amazon's guidelines to obtain these credentials: <a href="https://developer.amazon.com/docs/adm/obtain-credentials.html" target="_blank">Obtain ADM Credentials</a>.

Once you've configured the credentials, ADM push prompts are available under **Prompts > New Prompt > Push**.
