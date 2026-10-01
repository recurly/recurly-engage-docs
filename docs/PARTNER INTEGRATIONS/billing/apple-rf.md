---
title: Apple
excerpt: >-
  Guide to configuring Apple Push Notification Service (APNs) credentials in
  Recurly Engage for push prompts.
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
  <div class="rp-overview">The Apple integration lets Recurly Engage send push notifications to iOS and tvOS devices through the Apple Push Notification service (APNs).</div>
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
  <li>Supported on Android devices and web browsers with FCM support.</li>
</ul>

# Definition

<div class="rp-definition">The APNs connector ingests your Apple Push credentials (Bundle ID, Team ID, Token Key, and Key ID), so Recurly Engage can authenticate and send push notifications through APNs.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-brands fa-apple" aria-hidden="true"></i></div>
    <strong>Native iOS delivery</strong>
    <span>Reach iPhone, iPad, and Apple TV clients with rich notifications.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-lock" aria-hidden="true"></i></div>
    <strong>Secure token-based authentication</strong>
    <span>Use modern JSON Web Token (JWT) keys to avoid expired certificates.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-key" aria-hidden="true"></i></div>
    <strong>Centralized management</strong>
    <span>Store and rotate your APNs keys within Recurly Engage.</span>
  </div>
</div>

# Key details

## Required information

Provide the following under **Settings > Push Credentials** in Recurly Engage:

* **APNs Bundle ID**: Your app's Bundle Identifier.
* **APNs Team ID**: Your Apple Developer Team Identifier.
* **APNs Token Key**: The private key file (`.p8`) generated in Apple Developer.
* **APNs Token Key ID**: The Key ID associated with your `.p8` file.

## Get your APNs credentials

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Log in to the Apple Developer Console</h4><p>Log in to the <a href="https://developer.apple.com/account" target="_blank">Apple Developer Console</a>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Find your Bundle ID</h4><p>Go to <span style={{fontWeight: "bold"}}>Certificates, Identifiers &amp; Profiles → Identifiers</span>, select your app, and note the <span style={{fontWeight: "bold"}}>Bundle ID</span>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Find your Team ID</h4><p>Under <span style={{fontWeight: "bold"}}>Membership</span> (top-right avatar → <span style={{fontWeight: "bold"}}>Membership</span>), locate your <span style={{fontWeight: "bold"}}>Team ID</span>.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Create a token key and get the Key ID</h4><p>Navigate to <span style={{fontWeight: "bold"}}>Certificates, Identifiers &amp; Profiles → Keys</span>, and select <span style={{fontWeight: "bold"}}>+</span> to create a new key with <span style={{fontWeight: "bold"}}>Apple Push Notification service (APNs)</span> enabled.</p></div>
  </div>
</div>

<ul class="rp-list">
  <li>Give your key a name.</li>
  <li>After creation, download the <code>.p8</code> file.</li>
  <li>Record the <strong>Key ID</strong> (displayed next to your key name).</li>
</ul>

Once you've imported the credentials, toggle your APNs credentials to **Active** in Recurly Engage to begin sending push prompts to iOS and tvOS users.

<br />
