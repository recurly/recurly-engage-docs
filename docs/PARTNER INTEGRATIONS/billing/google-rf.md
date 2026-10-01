---
title: Google
excerpt: >-
  Setup guide for Google’s Firebase Cloud Messaging (FCM) connector in Recurly
  Engage Push Prompts.
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
  <div class="rp-overview">The Google integration lets Recurly Engage send push notifications to Android apps and web browsers through Firebase Cloud Messaging (FCM).</div>
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
  <li>Push notifications are supported on Android devices and web browsers with FCM support.</li>
</ul>

# Definition

<div class="rp-definition">The FCM connector ingests your Firebase service account JSON file, which lets Recurly Engage send push notifications through Google's FCM infrastructure.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-mobile-screen-button" aria-hidden="true"></i></div>
    <strong>Broad device reach</strong>
    <span>Target Android apps and modern web clients.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-lock" aria-hidden="true"></i></div>
    <strong>Secure authentication</strong>
    <span>Use Google's service account keys.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-key" aria-hidden="true"></i></div>
    <strong>Centralized management</strong>
    <span>Handle push credentials within Recurly Engage.</span>
  </div>
</div>

# Key details

## Get your FCM service account JSON

**Required information**: `FCM service json` file

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open the Firebase Console</h4><p>Go to the <a href="https://console.firebase.google.com/" target="_blank">Firebase Console</a> and select your project.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Open service accounts</h4><p>Select the gear icon in the sidebar, and then choose <span style={{fontWeight: "bold"}}>Project Settings → Service Accounts</span>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Generate a key</h4><p>Select <span style={{fontWeight: "bold"}}>Generate new private key</span>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Download the file</h4><p>Download the resulting JSON file.</p></div>
  </div>
</div>

**Sample service account JSON payload**:

```json
{
  "type": "service_account",
  "project_id": "PROJECT_ID",
  "private_key_id": "PRIVATE_KEY_ID",
  "private_key": "-----BEGIN PRIVATE KEY-----\n...\n-----END PRIVATE KEY-----\n",
  "client_email": "firebase-adminsdk-xxx@PROJECT_ID.iam.gserviceaccount.com",
  "client_id": "CLIENT_ID",
  "auth_uri": "https://accounts.google.com/o/oauth2/auth",
  "token_uri": "https://oauth2.googleapis.com/token",
  "auth_provider_x509_cert_url": "https://www.googleapis.com/oauth2/v1/certs",
  "client_x509_cert_url": "CLIENT_X509_CERT_URL"
}
```

## Upload the file to Recurly Engage

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open Push Credentials</h4><p>In Recurly Engage, go to <span style={{fontWeight: "bold"}}>Settings → Push Credentials</span>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Upload your JSON file</h4><p>Select <span style={{fontWeight: "bold"}}>Firebase Cloud Messaging</span> and upload your downloaded JSON file.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Turn on FCM push prompts</h4><p>Toggle <span style={{fontWeight: "bold"}}>Active</span> to <span style={{fontWeight: "bold"}}>On</span> to enable FCM push prompts.</p></div>
  </div>
</div>
