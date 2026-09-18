---
title: Google tag manager
excerpt: >-
  Step-by-step instructions for deploying the Recurly Engage client SDK via
  Google Tag Manager.
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
  <div style={{position: "relative", paddingTop: "56.25%", marginBottom: "28px", borderRadius: "10px", overflow: "hidden"}}>
    <iframe src="https://www.loom.com/embed/9299487b721c4345a6326916ef68f287?sid=a721bfdd-f71a-431c-ae76-bd8f84bbbc82"
      title="Google Tag Manager integration walkthrough"
      allow="autoplay; fullscreen"
      allowtransparency="true"
      frameBorder="0"
      scrolling="no"
      allowFullScreen
      style={{position: "absolute", top: 0, left: 0, width: "100%", height: "100%", border: "none"}}></iframe>
  </div>
  <div class="rp-overview">Install the Recurly Engage SDK across your site using a custom Google Tag Manager template — no manual code edits required. This guide walks you through adding the tag, connecting your Application ID, and publishing your container.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available to all customers on any Recurly Engage subscription plan</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have already created a Recurly Engage application and have its Application ID on hand.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>You need publish permissions in the GTM container for your site.</li>
</ul>

# Definition

<div class="rp-definition">The Google Tag Manager integration uses a custom GTM template to inject the Recurly Engage SDK onto every page you specify, enabling tracking and branded checkout across your site.</div>

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>Find the official template in the <a href="https://tagmanager.google.com/gallery/#/owners/redfast/templates/redfast-gtm" target="_blank">Google Tag Manager Gallery</a>.</div>
</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>One-click setup</strong>
    <span>Install the SDK entirely within GTM — no manual code edits.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-gauge" aria-hidden="true"></i></div>
    <strong>Centralized management</strong>
    <span>Control SDK triggers and updates from a single GTM interface.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-bolt" aria-hidden="true"></i></div>
    <strong>Instant rollouts</strong>
    <span>Publish changes immediately, without redeploying your site.</span>
  </div>
</div>

# Key details

## Guide

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Log in to Google Tag Manager</h4><p>Visit <a href="https://tagmanager.google.com/#/home" target="_blank">GTM</a> and open the container for your application.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Select your container</h4><p>Make sure it matches the domain you registered during <a href="https://docs.recurly.com/recurly-engage/docs/setup-your-app" target="_blank">app setup</a>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/2fe6657-Screenshot_2024-05-22_at_18.16.19.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Add a new tag</h4><p>In the left navigation, click <strong>Tags</strong>, then <strong>New</strong>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/ac79c42-Screenshot_2024-05-22_at_18.17.19.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Search for the Recurly Engage template</h4><p>In the <strong>Choose tag type</strong> pane, use the search bar and enter <strong>Recurly Engage</strong>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/d98bcf3-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Get your Application ID</h4><p>Log in to your Recurly Engage console and go to <strong>Settings > Application</strong> to copy the ID.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/f048f16-Screenshot_2024-05-22_at_18.30.09.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">6</div>
    <div><h4>Configure the tag</h4><p>Set up the template with your application's details.</p></div>
  </div>
</div>

<ul class="rp-list">
  <li>Name it <strong>Recurly Engage Tag</strong>.</li>
  <li>Paste your <strong>Application ID</strong> into the template field.</li>
  <li>Under <strong>Triggering</strong>, choose <strong>All Pages</strong>.</li>
  <li>Click <strong>Save</strong>.</li>
</ul>


<Image src="https://files.readme.io/1056d86-Screenshot_2024-05-22_at_18.33.53.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">7</div>
    <div><h4>Publish your container</h4><p>Click <strong>Submit</strong> in the top right of GTM, add a descriptive version name (for example, "Add Recurly Engage SDK"), and click <strong>Publish</strong>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/a0de186-Screenshot_2024-05-22_at_18.35.42.png" align="center" width="75%" border={true} />
