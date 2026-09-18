---
title: Direct tag management
excerpt: >-
  Instructions for embedding the Recurly Engage JavaScript SDK directly into
  your site’s HTML.
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
  <div class="rp-overview">Add the Recurly Engage SDK to your application by inserting the script snippet directly into your HTML. Once it's in place, Recurly Engage starts syncing customer data for personalized experiences.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available to all customers on any Recurly Engage subscription plan</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You need <strong>Administrator</strong> access to your Recurly Engage console.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>You must be able to edit and redeploy your site's HTML files.</li>
</ul>

# Definition

<div class="rp-definition">The Direct tag integration lets you manually paste the Recurly Engage JavaScript snippet into your site's HTML, enabling Engage features without a tag manager.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-sliders" aria-hidden="true"></i></div>
    <strong>Full control</strong>
    <span>Embed the script exactly where you need it in your page lifecycle.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-code" aria-hidden="true"></i></div>
    <strong>No external tools</strong>
    <span>Skip tag managers and deploy directly in your codebase.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-gauge-high" aria-hidden="true"></i></div>
    <strong>Performance-safe</strong>
    <span>Use the <code>defer</code> attribute to keep the script from blocking page rendering.</span>
  </div>
</div>

# Key details

Follow these steps to add the Recurly Engage SDK directly:

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Log in to Recurly Engage and select your application</h4><p>Make sure you're in the correct app context before retrieving your snippet.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Retrieve the JavaScript snippet</h4><p>In the Engage console, go to <strong>Settings > Usage Tracking</strong>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/2c35d83-Screenshot_2024-05-23_at_16.23.58.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Copy the code snippet</h4><p>Select and copy the entire <code>&lt;script&gt;</code> block provided.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/9e21b53-Screenshot_2024-05-23_at_16.25.30.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Locate your root HTML file</h4><p>Open your project and find the main HTML file — commonly named <code>index.html</code> — where your other scripts load.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/3520de0-js-tag-direct-3.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Paste the snippet above the closing <code>&lt;/head&gt;</code> tag</h4><p>Insert the <code>&lt;script&gt;</code> block right before <code>&lt;/head&gt;</code>. You can add <code>defer</code> if you'd like — it won't affect the SDK's operation.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/5bffbbf-js-tag-direct-4.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">6</div>
    <div><h4>Save and deploy your project</h4><p>Commit your changes, deploy your site, and confirm the SDK loads on page view.</p></div>
  </div>
</div>
