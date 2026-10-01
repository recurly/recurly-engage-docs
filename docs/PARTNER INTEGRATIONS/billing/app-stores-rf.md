---
title: App Stores
excerpt: >-
  Guidance for configuring in-app purchase flows in Recurly Engage prompts
  across Roku, Apple, and Google platforms.
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
  <div class="rp-overview">Configure Recurly Engage prompts to start native in-app purchase flows on Roku, Apple, and Google Play devices. Users can buy, upgrade, or downgrade without leaving your app or the prompt.</div>
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
  <li>Supported on Android devices and web browsers with FCM support.</li>
</ul>

# Definition

<div class="rp-definition">The In-App Purchase feature enables direct purchase, upgrade, and downgrade flows from within prompts, using native store dialogs and validation.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-bag-shopping" aria-hidden="true"></i></div>
    <strong>Streamlined UX</strong>
    <span>Let users complete purchases without leaving your app or prompt.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-layer-group" aria-hidden="true"></i></div>
    <strong>Consistent integration</strong>
    <span>Use the same prompt UI across platforms while invoking native purchase flows.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-sliders" aria-hidden="true"></i></div>
    <strong>Flexibility</strong>
    <span>Support upgrades, downgrades, and one-time purchases natively.</span>
  </div>
</div>

# Key details

Configure your prompt's main call-to-action (CTA) to trigger the in-app purchase flow for a specific product identifier. The steps vary by platform.

## Roku App Store

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open the prompt</h4><p>Open the <span style={{fontWeight: "bold"}}>Prompt Edit</span> screen in Pulse.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Enter the product ID</h4><p>In the <span style={{fontWeight: "bold"}}>In-App Purchase</span> section, enter the <span style={{fontWeight: "bold"}}>Product ID</span> that matches your Roku In-Channel Product Identifier.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Choose the purchase type</h4><p>Choose <span style={{fontWeight: "bold"}}>Upgrade</span> or <span style={{fontWeight: "bold"}}>Downgrade</span> from the dropdown to specify the purchase type.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/a4de93b-roku-inapp.png" align="center" width="40%" border={true} />


When the user taps the CTA, the Roku SDK starts the appropriate purchase flow.

## Apple App Store

### Add in-app product IDs

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open Apple actions</h4><p>Navigate to <span style={{fontWeight: "bold"}}>Settings → Actions → Apple</span> in Pulse.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Define your product IDs</h4><p>Define one or more <span style={{fontWeight: "bold"}}>Product IDs</span> that match those in App Store Connect.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/d01be52-apple-add-inapp-product.png" align="center" width="75%" border={true} />


### Attach a product ID to a prompt

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Select the product ID</h4><p>Open the <span style={{fontWeight: "bold"}}>Prompt Edit</span> screen and select the product ID you want under <span style={{fontWeight: "bold"}}>In-App Purchase</span>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/f500c36-appstore-select-inapp.png" align="center" width="40%" border={true} />


When the user selects the CTA, the Recurly Engage SDK handles the native purchase dialog.

## Google Play Store

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open the prompt</h4><p>Open the <span style={{fontWeight: "bold"}}>Prompt Edit</span> screen in Pulse.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Enter the product ID</h4><p>Enter your <span style={{fontWeight: "bold"}}>Product ID</span> under <span style={{fontWeight: "bold"}}>In-App Purchase</span>.</p></div>
  </div>
</div>

When the user selects the CTA, the SDK triggers the Google Play purchase flow.

Use these settings to add native in-app purchase experiences to your Recurly Engage prompts across Roku, iOS, and Android.

<br />
