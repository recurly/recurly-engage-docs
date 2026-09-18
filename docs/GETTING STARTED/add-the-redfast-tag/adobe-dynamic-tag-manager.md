---
title: Adobe dynamic tag manager
excerpt: >-
  Step-by-step instructions for integrating the Recurly Engage JavaScript client
  via Adobe Dynamic Tag Manager.
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
  <div class="rp-overview">Learn how to deploy the Recurly Engage tag through Adobe Dynamic Tag Manager (DTM) to start syncing your site's data with Engage for personalized customer experiences.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available to all customers on any Recurly Engage subscription plan</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You need to be able to add or modify embed code in your site's header.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>You must have publish and rule-creation permissions in your Adobe DTM account.</li>
</ul>

# Definition

<div class="rp-definition">The Adobe Dynamic Tag Manager integration injects the Recurly Engage JavaScript client into your pages using DTM rules and workflows, letting Engage collect events and deliver customized checkout experiences.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Seamless deployment</strong>
    <span>Use your existing DTM workflows to roll out Engage without touching site code.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-flask" aria-hidden="true"></i></div>
    <strong>Controlled release</strong>
    <span>Use DTM's approval process to test in staging before going live.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-gauge-high" aria-hidden="true"></i></div>
    <strong>Performance-safe</strong>
    <span>Host the client via Akamai or your preferred DTM option to minimize latency.</span>
  </div>
</div>

# Key details

## Guide

### Configure embed code

Choose one of three hosting options in DTM, then decide where to place the embed tag.

#### Hosting options

<ul class="rp-list">
  <li>Akamai</li>
  <li>FTP delivery</li>
  <li>Library download</li>
</ul>

#### Location options

<ul class="rp-list">
  <li>Header</li>
  <li>Footer</li>
</ul>

We recommend Akamai hosting with the embed tag in the header for the fastest load times. For more control, coordinate with your IT team to use the library download option.

### Rules

In most cases, use a Page-Load rule when targeting your site's pages.


<Image src="https://files.readme.io/b53b37f-rules2.png.img.png" align="center" width="75%" border={true} />


### Workflows

Propagate your tag from non-production (staging) to production using DTM's approval workflow to keep your rollouts safe.


<Image src="https://files.readme.io/77107ad-image_8.png.img.png" align="center" width="75%" border={true} />


### Installation

Add the DTM header code that loads the Recurly Engage tag to all pages of your site.


<Image src="https://files.readme.io/cdc7383-image_11.png.img.png" align="center" width="75%" border={true} />
