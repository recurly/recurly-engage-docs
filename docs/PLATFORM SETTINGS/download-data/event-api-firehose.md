---
title: Event API Firehose
excerpt: >-
  Configuration guide for the Event API Firehose feature, which allows you to
  export and stream usage tracking data via AWS S3 or custom webhooks.
deprecated: false
hidden: true
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
<div class="rp-page">
  <div class="rp-overview">The Event API Firehose sends your usage tracking events to systems outside Recurly Engage, as JSON. Pull the events from an Amazon Web Services (AWS) S3 bucket on demand, or have Engage push them to an endpoint you control in near real time.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly Engage plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#s3-event-data-logs"><span class="rp-toc-num">3</span>S3 event data logs</a>
    <a class="rp-toc-pill" href="#custom-web-api-firehose"><span class="rp-toc-num">4</span>Custom web API Firehose</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have <span style={{fontWeight: "bold"}}>Company</span> or <span style={{fontWeight: "bold"}}>App Administrator</span> permissions in Engage.</li>
</ul>

# Definition

<div class="rp-definition">The <span style={{fontWeight: "bold"}}>Event API Firehose</span> feature pushes usage tracking events in JSON format to external systems — either by writing to an S3 bucket or by POSTing to a custom web API endpoint — enabling real-time or batch consumption of event data.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Real-time insights</strong>
    <span>Stream usage events as they occur for immediate data-driven decisions.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Scalable storage</strong>
    <span>Offload event logs to S3 for long-term retention and business intelligence (BI) integration.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Flexible integration</strong>
    <span>Send data to any HTTP endpoint or cloud storage service to fit your architecture.</span>
  </div>
</div>

# S3 event data logs

Usage tracking data that you've enabled in Engage can be pushed to external systems. Anything added in the Usage Tracker section is sent as an event once the integration is set up.


<Image src="https://files.readme.io/d7f9c3c-Event_Export_1.png" align="center" width="75%" border={true} />


There are two ways to receive usage data. You must provide the following values to your account manager:

**AWS S3 requirements** — Pull data using Engage:

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open User Traits</h4><p>Go to <span style={{fontWeight: "bold"}}>Settings &gt; User Traits</span>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/bfbf239-Event_Exports_settings.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Show your S3 credentials</h4><p>Select <span style={{fontWeight: "bold"}}>“Click here for AWS S3 credentials”</span>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/a970314-Event_Exports_settings_1.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Pull your data</h4><p>Copy the <span style={{fontWeight: "bold"}}>AWS Bucket</span>, <span style={{fontWeight: "bold"}}>Access Key</span>, and <span style={{fontWeight: "bold"}}>Secret Key</span>, then navigate to the <code>exports</code> folder. All filenames start with the <code>usages</code> prefix. You can pull this data on demand.</p></div>
  </div>
</div>

## AWS S3 data specifications

All data is JSON formatted with the following fields. To enable optional fields, ask your account manager:

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Field</td><td>Description</td><td>Notes</td></tr>
  <tr><td><code>user_id</code></td><td>Primary user identifier</td><td></td></tr>
  <tr><td><code>anonymous_user_id</code></td><td>Identifier when userId is unavailable</td><td></td></tr>
  <tr><td><code>event</code></td><td>Name of event</td><td></td></tr>
  <tr><td><code>platform</code></td><td>Type of integration</td><td>Always <code>redfast</code> for usage</td></tr>
  <tr><td><code>type</code></td><td>Type of tracker</td><td>Values: <code>page</code>, <code>track</code>, <code>custom</code></td></tr>
  <tr><td><code>properties.id</code></td><td>Usage tracker ID</td><td></td></tr>
  <tr><td><code>properties.values</code></td><td>Configured values in the Engage console</td><td></td></tr>
  <tr><td><code>properties.options</code></td><td>Additional options</td><td>Specifies if regex is used for page trackers</td></tr>
  <tr><td><code>ts</code></td><td>Timestamp when activity occurred (epoch)</td><td></td></tr>
  <tr><td><code>app_id</code></td><td>Engage app ID</td><td>Optional</td></tr>
  <tr><td><code>traits</code></td><td>Key/value pairs of user attributes ingested from external and in-app sources</td><td>Optional</td></tr>
  <tr><td><code>segments</code></td><td>List of segment objects (ID + name) at event time</td><td>Optional</td></tr>
  <tr><td><code>paths</code></td><td>List of personalization path objects (ID, name, device_type, zone)</td><td>Optional</td></tr>
</table>

## Event types

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Type</td><td>Description</td></tr>
  <tr><td><code>Impression</code></td><td>User was shown the prompt</td></tr>
  <tr><td><code>Timeout</code></td><td>User did not respond before the timer expired</td></tr>
  <tr><td><code>Dismiss</code></td><td>User dismissed by clicking <code>X</code> or outside the window</td></tr>
  <tr><td><code>Decline</code></td><td>User clicked on the decline link</td></tr>
  <tr><td><code>Click</code></td><td>User accepted the prompt (phased out in favor of Goal)</td></tr>
  <tr><td><code>Goal</code></td><td>User accepted the prompt</td></tr>
  <tr><td><code>Custom_Goals_[Activity Type]</code></td><td>User completed a defined custom goal on a prompt</td></tr>
  <tr><td><code>Exclude</code></td><td>User excluded due to holdout or user limits</td></tr>
  <tr><td><code>Holdout</code></td><td>User in holdout group</td></tr>
  <tr><td><code>Pipeline_Impression</code></td><td>User shown the prompt and is in a pipeline stage</td></tr>
  <tr><td><code>Pipeline_Transition</code></td><td>User moved from one pipeline stage to another</td></tr>
</table>

# Custom web API Firehose

This option provides near-real-time delivery. Engage can send single or batched events within sub-minute windows to an endpoint you specify. Provide your account manager with:

* **URL**
* **API Key** or **Access Token**
* **Request type** (`GET`, `POST`, or `PUT`)

## Payload format

The payload is a JSON array of event objects. In S3, each event is one object per row.

```json
[  
  { /* event object as shown below */ },  
  { /* ... */ }  
]
```

## Example event payload

```json
{
  "app_id": "74f72649-0327-4911-bd21-a4cd533cec1c",
  "user_id": "123",
  "anonymous_user_id": "2528a84d8fa8…",
  "event": "Home Page",
  "platform": "redfast",
  "type": "page",
  "ts": 1630476856,
  "properties": {
    "id": "8e282c72-07da-4c2f-bf91-85df633828af",
    "values": [{ "url_hash": "", "url_path": "/", "query_params": "" }],
    "options": { "use_regex": false }
  },
  "traits": { /* user trait key/value pairs */ },
  "segments": [{ "id": "...", "name": "Engaged" }, /* ... */],
  "paths": [{ "id": "...", "name": "Prompt A", "device_type": "web", "zone": "banner" }, /* ... */]
}
```

## API data specifications

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Field</td><td>Description</td><td>Notes</td></tr>
  <tr><td><code>app_id</code></td><td>Engage app ID</td><td></td></tr>
  <tr><td><code>user_id</code></td><td>Primary user identifier</td><td></td></tr>
  <tr><td><code>anonymous_user_id</code></td><td>Identifier when userId is unavailable</td><td></td></tr>
  <tr><td><code>event</code></td><td>Name of event</td><td></td></tr>
  <tr><td><code>platform</code></td><td>Always <code>redfast</code></td><td></td></tr>
  <tr><td><code>type</code></td><td><code>page</code>, <code>track</code>, or <code>custom</code></td><td></td></tr>
  <tr><td><code>properties.id</code></td><td>Usage tracker ID</td><td></td></tr>
  <tr><td><code>properties.values</code></td><td>Configured tracker values</td><td></td></tr>
  <tr><td><code>properties.options</code></td><td>Regex or other options</td><td></td></tr>
  <tr><td><code>ts</code></td><td>Epoch timestamp</td><td></td></tr>
  <tr><td><code>traits</code></td><td>User attributes (key/value pairs)</td><td>Optional</td></tr>
  <tr><td><code>segments</code></td><td>Segment list (ID + name)</td><td>Optional</td></tr>
  <tr><td><code>paths</code></td><td>Personalization path list (ID, name, device_type, zone)</td><td>Optional</td></tr>
</table>

## Usage types

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Type</td><td>Description</td></tr>
  <tr><td><code>page</code></td><td>Page view tracker</td></tr>
  <tr><td><code>track</code></td><td>Button or Cascading Style Sheets (CSS) class click</td></tr>
  <tr><td><code>custom</code></td><td>Custom event (for example, transaction complete)</td></tr>
</table>

## API push example

```bash
curl 'example.backendurl.com/v1/api/ingest/' \
  -X POST \
  -H 'Content-Type: application/json' \
  -H 'your-api-key: abcdef' \
  --data-raw '[ { /* event objects */ } ]'
```
