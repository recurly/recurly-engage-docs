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
# Overview

Recurly Engage requires a consistent **User ID** to differentiate authenticated visitors, personalize prompts, and attribute downstream reporting. This page explains how to configure User ID matching.

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

export const PrerequisitesLimitations = ({ header }) => {
  return (
    <div className="flex justify-start">
      <div className="rounded-md p-6 m-4 max-w-lg shadow-md border border-gray-300 dark:bg-gray-800 dark:border-gray-600">
        <p className="text-lg font-bold">{header}</p>
        <p>
          <i className="fa-solid fa-check mr-2" />
          You must have <strong>Company</strong> or <strong>App Administrator</strong> permissions in Recurly Engage.
        </p>
        <p>
          <i className="fa-solid fa-exclamation-triangle mr-4" />
          Developer assistance may be required for custom storage or decoding logic.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

**User ID Matching** tells the Recurly Engage client how to retrieve and normalize a unique user identifier from browser storage or global objects.

# Key benefits

* **Accurate personalization**: Ensures prompts target the correct authenticated user.
* **Reliable reporting**: Associates prompt interactions with user profiles for analytics.
* **Flexible storage**: Supports cookies, localStorage, sessionStorage, dataLayer, or custom JS logic.

# Key details

***

When authenticated users visit your site, their unique **User ID** is stored in the browser. Configure Recurly Engage to read this value from one of the following sources:

* **localStorage** item
* **sessionStorage** item
* **Cookie**
* **dataLayer** variable

Specify the storage location and key in the **User ID Matching** form:

<Image align="center" className="border" border={true} src="https://files.readme.io/997b754b9eca52a38e829bfb135e3a944f21ae3abdcb7736520990b6561e118c-image.png" />

If the value is encoded (e.g. Base64), select the appropriate decode option:

<Image align="center" className="border" border={true} src="https://files.readme.io/a10af0c7a355927ec26e1db6537ebf1727b49ac6d90a2486d9fb6a5b52d4213a-image.png" />

If the decoded value is a JSON object, provide a property path to extract the final ID:

<Image align="center" className="border" border={true} src="https://files.readme.io/40644c7db538ade718d1542656d22f4a71f2330860e791905b935daa6ea1c894-image.png" />

Once configured, scroll to the bottom and click **Save**:

<Image align="center" src="https://files.readme.io/935237ece01241309498a59cc33773274673fd51a06cf21dee221983a34202ce-image.png" />

For assistance, please contact Recurly Engage Support.

***

# `fetchUserId` examples

For complex cases, choose **Custom JS Snippet** and implement a `fetchUserId` function in **Settings → Custom JS Snippet**. Below are examples using built-in `RFHelpers`:

You can view all helper functions here: [RFHelpers on GitHub](https://gist.github.com/peter-redfast/24555da8e489a0278bda2c29f8092f3c)

### Basic example

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

Read a Base64-encoded ID from a cookie and decode:

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