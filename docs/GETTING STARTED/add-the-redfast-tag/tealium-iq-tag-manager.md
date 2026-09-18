---
title: Tealium iQ tag manager
excerpt: >-
  Step-by-step instructions for integrating the Recurly Engage JavaScript client
  via Tealium iQ Tag Manager.
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
  <div class="rp-overview">Use Tealium iQ Tag Manager to load the Recurly Engage SDK on your site without editing page code.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available to all customers on any Recurly Engage subscription plan</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>Access to <strong>Settings > Usage Tracking</strong> in your Recurly Engage app.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>You must have publish permissions in both your Recurly Engage and Tealium iQ accounts.</li>
</ul>

# Definition

<div class="rp-definition">The Tealium iQ Tag Manager integration injects the Recurly Engage JS client via a generic script tag, enabling data collection and branded checkout flows.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-bolt" aria-hidden="true"></i></div>
    <strong>Rapid setup</strong>
    <span>Deploy the client through Tealium's UI — no code changes needed.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-tags" aria-hidden="true"></i></div>
    <strong>Unified tagging</strong>
    <span>Manage Engage alongside all your marketing and analytics tags.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-gauge-high" aria-hidden="true"></i></div>
    <strong>Instant rollouts</strong>
    <span>Publish to Dev, QA, and Prod environments in one workflow.</span>
  </div>
</div>

# Key details

Integrate the Recurly Engage JavaScript client into your web application through Tealium iQ Tag Manager by following the steps below. Once complete, Recurly Engage starts syncing its data with your site to personalize customer experiences.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Log in to Recurly Engage and select your application</h4><p>Make sure you're in the correct app context.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Retrieve the client URL</h4><p>Go to <strong>Settings > Usage Tracking</strong>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/539dc52-Screenshot_2024-05-22_at_21.56.18.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Copy the URL</h4><p>Copy the URL portion of the code snippet — you'll need it in step 7.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/1e10450-Screenshot_2024-05-22_at_21.59.39.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Log in to Tealium iQ and select the correct profile</h4></div>
  </div>
</div>


<Image src="https://files.readme.io/7cde0a3-tealium-2a.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Add a new tag</h4><p>Go to the <strong>Tags</strong> tab and click <strong>Add Tag</strong>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/daa497e-tealium-3.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">6</div>
    <div><h4>Choose the Generic Tag template</h4><p>In the popup, search for "Generic Tag" and click <strong>Add</strong>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/af67285-tealium-4.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">7</div>
    <div><h4>Configure the Recurly Engage tag</h4><p>Set the fields below to match your integration.</p></div>
  </div>
</div>

<ul class="rp-list">
  <li><strong>Title:</strong> Recurly Engage Tag</li>
  <li><strong>Type:</strong> Script</li>
  <li><strong>Base URL:</strong> paste the URL from step 2</li>
  <li><strong>Request Script Once:</strong> enable</li>
</ul>


<Image src="https://files.readme.io/aaa8198-tealium-5a.png" align="center" width="75%" border={true} />



<Image src="https://files.readme.io/93928cb-tealium-5.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">8</div>
    <div><h4>Publish the tag</h4><p>Click <strong>Dev</strong>, <strong>QA</strong>, and <strong>Prod</strong> to push the tag through each environment.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/e8db19b-tealium-6.png" align="center" width="75%" border={true} />
