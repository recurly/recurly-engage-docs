---
title: Data sources
excerpt: >-
  Use CSV uploads as data sources for dynamic prompt content and enrich in-app
  messages.
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
  <div class="rp-overview">Update a comma-separated values (CSV) file once, and every Recurly Engage prompt that references it stays current. Use data sources to keep variable content, like coupon details, in one place instead of editing prompts by hand.</div>
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

<div class="rp-definition"><span style={{fontWeight: "bold"}}>Data sources</span> let you upload structured CSV content into Engage and reference those values within prompt copy via dynamic content insertion.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Always up-to-date content</strong>
    <span>Update an external CSV and your prompts reflect the new values without manual edits.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Eliminate errors</strong>
    <span>Maintain a single source of truth for variable content, such as coupon details.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Flexible targeting</strong>
    <span>Combine data source values with segmentation and dynamic variables for highly personalized messaging.</span>
  </div>
</div>

# Key details

Any user information synced to Engage can be used not only for segmentation but also as dynamic content within a prompt’s title or message body, using [Dynamic Variables](doc:dynamic-variables).

Data source variables are another way to expand the content you can show. By uploading a CSV, you can import structured content to use within prompts.

For example, say you want to tell the user “Get 1 month off,” but the actual discount varies by marketing department based on the time of year, so it becomes “Get 2 weeks off.” One way to handle this is to edit the prompt manually each time something changes. A better way is to use a coupon data source.

In this example, you upload a CSV with various coupon attributes:


<Image src="https://files.readme.io/6a1c972-Capture-2024-05-20-182307.png" align="center" width="75%" border={true} />


Then you reference just the value in the prompt by inserting dynamic content. This eliminates errors and lets you import structured data from external sources into the system:


<Image src="https://files.readme.io/cbfa10c-Capture-2024-05-20-182358.png" align="center" width="75%" border={true} />
