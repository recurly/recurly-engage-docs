---
title: APIs
excerpt: >-
  How to configure custom API actions within Recurly Engage, including setting
  up credentials and defining action details.
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
  <div class="rp-overview">Already have a backend that does the work? Custom API actions let your Recurly Engage prompts call it directly, passing along user data and securely stored credentials.</div>
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

<div class="rp-definition">Custom API actions let you call external backend endpoints from prompts, using dynamic user data and secure credentials.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Build on existing systems</strong>
    <span>Integrate with your own APIs without additional development in Engage.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Secure and dynamic</strong>
    <span>Store credentials securely and inject user-specific data into API calls.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Flexible configurations</strong>
    <span>Define URLs, methods, headers, query strings, and payloads for diverse use cases.</span>
  </div>
</div>

# Key details

You can define custom API actions to use your existing backend endpoints, sending dynamic user data and secure credentials as needed.

## Add credentials

Credentials data is stored in a secure, encrypted location that is only accessible to components tasked with performing the action. The most common credentials are API keys and client secrets.

Add a new credential and specify its name and value.


<Image src="https://files.readme.io/faeced9-Screenshot_2024-05-02_at_15.50.02.png" align="center" width="75%" border={true} />


## Add actions

Define a custom API action by specifying the URL, HTTP method, request headers, query string, and request payload (if necessary).

Engage supports static and dynamic values. Use the special character (%) and placeholders to inject dynamic user data. You can reference placeholders like `%provider.api_key%` or `%provider.client_secret%`, user traits ingested via Engage, and <a href="forms" target="_blank">form inputs</a>. Dynamic values work in URLs, payloads, headers, and query strings.

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>Payloads don't support complex JSON structures — only a single level of key-value pairs.</div>
</div>


<Image src="https://files.readme.io/8a45296-Screenshot_2024-05-02_at_15.52.36.png" align="center" width="75%" border={true} />
