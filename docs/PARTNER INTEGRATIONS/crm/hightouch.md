---
title: Hightouch
excerpt: >-
  Learn how to connect your data warehouse to Recurly Engage using Hightouch’s
  HTTP Request destination to automate user property updates and
  personalizations.
deprecated: false
hidden: false
metadata:
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">This guide walks you through syncing customer data from Hightouch to Recurly Engage. Using the Recurly Engage Ingest API keeps user attributes, such as subscription plans, names, and custom tags, up to date, so you can trigger more relevant user experiences and retention workflows.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

# Definition

<div class="rp-definition">The Hightouch integration syncs user data from your data warehouse to Recurly Engage. It uses a Hightouch HTTP Request destination that sends each user's attributes to the Recurly Engage Ingest API.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-user-pen" aria-hidden="true"></i></div>
    <strong>Automated personalization</strong>
    <span>Keep user properties in Recurly Engage in sync with your source of truth, such as Snowflake or BigQuery, without manual uploads.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-code" aria-hidden="true"></i></div>
    <strong>Low-code integration</strong>
    <span>Use Hightouch's flexible HTTP Request destination to connect to the Recurly Engage API without custom engineering resources.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-bullseye" aria-hidden="true"></i></div>
    <strong>Real-time accuracy</strong>
    <span>Make sure changes in a user's status (for example, upgrading from "Basic" to "Premium") are reflected immediately in your engagement campaigns.</span>
  </div>
</div>

# Key details

## Set up the sync

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Create a new destination</h4><p>In your Hightouch dashboard, navigate to the <span style={{fontWeight: "bold"}}>Destinations</span> page and select <span style={{fontWeight: "bold"}}>Add Destination</span>. Search for and select <span style={{fontWeight: "bold"}}>HTTP Request</span>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/f9ca3e5af1bb3580c1d1eb1a31dd739b33e39bd82039fa9dca9b45699bfcb00f-1.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Configure the HTTP Request</h4><p>To establish the connection, enter the configuration details listed below.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/b6b9a73bb04adbdb16cd81547747ed4909c1b4a33f258973f74c259a408c4067-2.png" align="center" width="75%" border={true} />


* **Authentication Method**: Select Basic Auth.
* **Base URL**: `https://conduit.redfast.com/ingest/property`


<Image src="https://files.readme.io/564f1cf153749242eee8b3872cfa0651b991adb13041a7bca71e69b6abe90eb6-3.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Initialize a new sync</h4><p>Navigate to the <span style={{fontWeight: "bold"}}>Syncs</span> page and select <span style={{fontWeight: "bold"}}>Add Sync</span>. Select the Model that contains the user data you want to move into Recurly Engage.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/29efb9e046de6d47e36385b6196da2de554d6c66bb91c05f0e898158061ccbf2-4.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Select the destination</h4><p>Choose the HTTP Request destination you configured in step 2.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/f8633c34562976a7d27af39f84fabe4d319981f9ee6e815ddec5e9616faf9e62-5.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Configure the sync mapping</h4><p>The specific mapping depends on your data model. Use these standard configurations for the payload.</p></div>
  </div>
</div>

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Setting</td><td>Configuration</td></tr>
  <tr><td>Batching</td><td>A single row</td></tr>
  <tr><td>HTTP Method</td><td>POST</td></tr>
  <tr><td>URL</td><td>Add your API key as query string parameter</td></tr>
  <tr><td>Payload Type</td><td>JSON</td></tr>
</table>

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>To find your API key, navigate to <span style={{fontWeight: "bold"}}>Settings &gt; Application &gt; API Key</span>.</div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">6</div>
    <div><h4>Map the request body</h4><p>Make sure your JSON payload matches the Recurly Engage requirements. Your mapping should generate a structure similar to this.</p></div>
  </div>
</div>

```json
{
  "id": "123-456-789-012-",
  "user_id": "test-user-001",
  "properties": {
    "first_name": "Jane",
    "plan": "premium"
  }
}

```

**Example response**

```json
{
  "success": true
}

```


<Image src="https://files.readme.io/4189f595130811d944706d105c1364987eb2972d93b30102111769e78d015760-6.png" align="center" width="75%" border={true} />


<br />

<br />
