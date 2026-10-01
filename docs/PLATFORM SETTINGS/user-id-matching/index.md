---
title: User ID matching
excerpt: >-
  Guide for configuring how Recurly Engage matches authenticated users via
  unique browser-stored identifiers.
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
  <div class="rp-overview">Recurly Engage needs a consistent <span style={{fontWeight: "bold"}}>User ID</span> to tell authenticated visitors apart, personalize prompts, and attribute downstream reporting. This page walks you through configuring User ID matching.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly Engage plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
    <a class="rp-toc-pill" href="#fetchuserid-examples"><span class="rp-toc-num">4</span>fetchUserId examples</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have <span style={{fontWeight: "bold"}}>Company</span> or <span style={{fontWeight: "bold"}}>App Administrator</span> permissions in Engage.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>Developer assistance may be required for custom storage or decoding logic.</li>
</ul>

# Definition

<div class="rp-definition">The <span style={{fontWeight: "bold"}}>User ID Matching</span> settings tell the Engage client how to retrieve and normalize a unique user identifier from browser storage or global objects.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Accurate personalization</strong>
    <span>Ensures prompts target the correct authenticated user.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Reliable reporting</strong>
    <span>Associates prompt interactions with user profiles for analytics.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Flexible storage</strong>
    <span>Supports cookies, localStorage, sessionStorage, dataLayer, or custom JS logic.</span>
  </div>
</div>

# Key details

When authenticated users visit your site, their unique **User ID** is stored in the browser. Configure Engage to read this value from one of the following sources:

* **localStorage** item
* **sessionStorage** item
* **Cookie**
* **dataLayer** variable

Specify the storage location and key in the **User ID Matching** form:


<Image src="https://files.readme.io/997b754b9eca52a38e829bfb135e3a944f21ae3abdcb7736520990b6561e118c-image.png" align="center" width="75%" border={true} />


If the value is encoded (such as Base64), select the appropriate decode option:


<Image src="https://files.readme.io/a10af0c7a355927ec26e1db6537ebf1727b49ac6d90a2486d9fb6a5b52d4213a-image.png" align="center" width="75%" border={true} />


If the decoded value is a JSON object, provide a property path to extract the final ID:


<Image src="https://files.readme.io/40644c7db538ade718d1542656d22f4a71f2330860e791905b935daa6ea1c894-image.png" align="center" width="75%" border={true} />


Once you've configured everything, scroll to the bottom and click **Save**:


<Image src="https://files.readme.io/935237ece01241309498a59cc33773274673fd51a06cf21dee221983a34202ce-image.png" align="center" width="75%" border={true} />


For assistance, contact <a href="mailto:support@recurly.com">[support@recurly.com](mailto:support@recurly.com)</a>.

# `fetchUserId` examples

For complex cases, choose **Custom JS Snippet** and implement a `fetchUserId` function in **Settings → Custom JS Snippet**. The examples below use the built-in `RFHelpers`. You can view all helper functions in <a href="https://gist.github.com/peter-redfast/24555da8e489a0278bda2c29f8092f3c" target="_blank">RFHelpers on GitHub</a>.

## Basic example

Retrieve a JSON-wrapped ID from localStorage (common with Twilio Segment):

```javascript
static fetchUserId() {
  // Get value from localStorage
  const value = window.localStorage.getItem('ajs_user_id'); // '"user123"'
 
  // Parse JSON if possible, otherwise return raw value
  return RFHelpers.tryParseJSON(value); // 'user123'
}
```

## Cookies and decoding

Read a Base64-encoded ID from a cookie and decode it:

```javascript
static fetchUserId() {
  // Get cookie value
  const value = RFHelpers.getCookie('encoded_user'); // 'dXNlcjEyMw=='
 
  // Decode Base64
  return RFHelpers.decodeBase64(value); // 'user123'
}
```

## JavaScript object digging

Decode a JWT from a window variable and extract a nested `user.id`:

```javascript
static fetchUserId() {
  // Get JWT token
  const token = window['_JWT_USER_VAR'];
 
  // Decode JWT payload
  const obj = RFHelpers.decodeJWT(token);
  // e.g. { auth: '{"user":{"id":"user123"}}', ... }
  
  // Extract nested ID
  return RFHelpers.dig(obj, 'auth.user.id'); // 'user123'
}
```

## Multiple fallbacks

Combine methods to handle various sources:

```javascript
static fetchUserId() {
  // Path-based logic
  if (window.location.pathname.startsWith('/app/')) {
    return window.localStorage.getItem('USERID');
  }

  // Try cookie
  const cookie = RFHelpers.getCookie('user');
  if (cookie) return cookie;
  
  // Fall back to JWT in localStorage
  const local = window.localStorage.getItem('auth_token');
  if (local) {
    const decoded = RFHelpers.decodeJWT(local);
    return RFHelpers.dig(decoded, 'auth.id');
  }
}
```
