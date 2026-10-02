---
title: Push notifications
excerpt: >-
  How to configure push notification endpoints and credentials for Recurly
  Engage.
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
  <div class="rp-overview">Push prompts reach your users even when they aren't in your app or on your site. Add your device endpoints and push credentials to Recurly Engage, and you can send notifications through Firebase Cloud Messaging (FCM), Amazon Device Messaging (ADM), or Apple Push Notification service (APNs).</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly Engage plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#add-endpoint-addresses"><span class="rp-toc-num">3</span>Add endpoint addresses</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have <span style={{fontWeight: "bold"}}>Company</span> or <span style={{fontWeight: "bold"}}>App Administrator</span> permissions in Engage.</li>
</ul>

# Definition

<div class="rp-definition">Push prompts use device-specific endpoints to deliver notifications to users outside the app or website.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Reach users off-app</strong>
    <span>Engage users even when they aren't actively using your site or app.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Highly targeted</strong>
    <span>Deliver notifications to specific user segments based on traits and behaviors.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Flexible delivery</strong>
    <span>Support FCM, ADM, and APNs channels from a single interface.</span>
  </div>
</div>

# Add endpoint addresses

First, upload or sync your device endpoint information to Engage via a comma-separated values (CSV) file or API. Prepare a CSV with these columns:

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Column</td><td>Description</td></tr>
  <tr><td><code>Id</code></td><td>The device endpoint identifier.</td></tr>
  <tr><td><code>ChannelType</code></td><td>The push service (<code>FCM</code>, <code>ADM</code>, or <code>APNS</code>).</td></tr>
  <tr><td><code>Address</code></td><td>The device token.</td></tr>
  <tr><td><code>User.UserId</code></td><td>The Engage user ID.</td></tr>
</table>

This can be a one-time initial load. To keep endpoints up to date, choose one of these options:

* Periodically upload updated CSVs to the S3 bucket provided by Engage.
* Call the Device Registration API from your application.

## Registration API

\[TODO: Dev/PO review — possible issue: the example uses "channel_type": "GCM", while the CSV ChannelType values listed above are FCM, ADM, and APNS.]

```
POST <base_url>/ingest/update_push_endpoint
Headers:
  Rf-App: <app_slug>
  User-Id: <user_id>
  Content-Type: application/json
Body:
{
  "token": "4d5e6f1a2b3c4d5e6f7g8h9i0j1a2b3c",
  "channel_type": "GCM",
  "endpoint_id": "eqmj8wpxszeqy/b3vch04sn41yw"
}
```

## Amazon Device Messaging (ADM)

**Required information:** `ADM Client ID` and `ADM Client Secret`.

Follow Amazon’s credential guide: <a href="https://developer.amazon.com/docs/adm/obtain-credentials.html" target="_blank">Obtain ADM Credentials</a>.

## Apple Push Notification service (APNs)

**Required information:**

* `Apple Push Notifications Service Bundle ID`
* `Apple Push Notifications Service Team ID`
* `Apple Push Notifications Service Token Key`
* `Apple Push Notifications Service Token Key ID`

**Steps:**

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Log in to Apple Developer</h4><p>Log in to <a href="https://developer.apple.com/account" target="_blank">Apple Developer</a>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Find your Bundle ID</h4><p>Under <span style={{fontWeight: "bold"}}>Certificates, IDs &amp; Profiles → Identifiers</span>, select your app to view the Bundle ID.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Find your Team ID</h4><p>Under <span style={{fontWeight: "bold"}}>Membership Details</span>, note your Team ID.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Create or retrieve an APNs key</h4><p>Under <span style={{fontWeight: "bold"}}>Certificates, IDs &amp; Profiles → Keys</span>, create or retrieve an APNs key.</p></div>
  </div>
</div>

## Firebase Cloud Messaging (FCM)

**Required information:** `FCM service JSON` key.

**Steps:**

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open Service Accounts</h4><p>In <a href="https://console.firebase.google.com/" target="_blank">Firebase Console</a>, go to <span style={{fontWeight: "bold"}}>Project Settings → Service Accounts</span>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Generate a private key</h4><p>Click <span style={{fontWeight: "bold"}}>Generate New Private Key</span> and download the JSON file.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Upload the JSON</h4><p>Upload this JSON in the Engage console under <span style={{fontWeight: "bold"}}>Settings → Integrations → Push</span>.</p></div>
  </div>
</div>

The downloaded JSON file has this structure:

```json
{
  "type": "service_account",
  "project_id": "PROJECT_ID",
  "private_key_id": "PRIVATE_KEY_ID",
  "private_key": "PRIVATE_KEY",
  "client_email": "FIREBASE_ADMIN_SDK_EMAIL",
  "client_id": "CLIENT_ID",
  "auth_uri": "https://accounts.google.com/o/oauth2/auth",
  "token_uri": "https://oauth2.googleapis.com/token",
  "auth_provider_x509_cert_url": "https://www.googleapis.com/oauth2/v1/certs",
  "client_x509_cert_url": "CLIENT_X509_CERT_URL"
}
```

## Upload file to Engage

Once you have your FCM JSON file or your ADM or APNs credentials, upload them in the Engage console:

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open Push settings</h4><p>Go to <span style={{fontWeight: "bold"}}>Settings → Integrations → Push</span>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Add your credentials</h4><p>Select the channel and upload the corresponding credential file or enter key values.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Save to activate</h4><p>Click <span style={{fontWeight: "bold"}}>Save</span> to activate push messaging for your application.</p></div>
  </div>
</div>
