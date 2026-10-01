---
title: Application
excerpt: >-
  Configure your application settings—ID, API Key, domain, aliases, and
  timezone—to ensure Recurly Engage functions correctly on your site or app.
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
  <div class="rp-overview">The Application settings are where you set up and update your application configuration in Recurly Engage. Come here to grab your credentials, manage your domains, and set the timezone Engage uses for scheduling and reporting.</div>
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
</ul>

# Definition

<div class="rp-definition">The <span style={{fontWeight: "bold"}}>Application</span> settings define the core identity and access credentials for your Engage instance, including tag installation and API usage.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Secure access</strong>
    <span>Manage your API Key and regenerate it whenever you need to.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Multi-domain support</strong>
    <span>Use domain aliases to serve prompts across multiple brands or subdomains.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Accurate scheduling</strong>
    <span>Set your application timezone for prompt scheduling and performance reporting.</span>
  </div>
</div>

# Key details

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Setting</td><td>Description</td></tr>
  <tr><td>ID</td><td>Your application’s unique identifier. Use this to <a href="google-tag-manager" target="_blank">add the Engage tag</a> on your site via Google Tag Manager.</td></tr>
  <tr><td>API Key</td><td>Your application’s API key. The <span style={{fontWeight: "bold"}}>ID</span> and <span style={{fontWeight: "bold"}}>API Key</span> fields are pre-filled. Click the rotate icon to regenerate the key, which invalidates the previous one.</td></tr>
  <tr><td>Name (required)</td><td>The friendly name of your site or application. You can change this at any time.</td></tr>
  <tr><td>Domain (required)</td><td>The primary domain where your application is accessed. You don’t need to include subdomains like <code>www</code> unless you manage multiple apps under one domain.</td></tr>
  <tr><td>Domain Aliases</td><td>Additional domains that can use the same Engage configuration. Useful for multi-brand or regional deployments.</td></tr>
  <tr><td>Timezone</td><td>The application’s timezone. Engage uses it for prompt scheduling (unless user timezone is selected) and for displaying performance metrics.</td></tr>
</table>


<Image src="https://files.readme.io/46e455b-image.png" align="center" width="75%" border={true} />
