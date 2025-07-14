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
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

### Prerequisites & limitations

* Company or App Administrator permissions in Recurly Engage.
* Supported only on iOS and tvOS devices integrated with the Recurly Engage SDK.
* Your Apple Developer account must have an active membership to manage certificates and keys.

# Definition

The **APNs** connector ingests your Apple Push credentials—Bundle ID, Team ID, Token Key, and Key ID—so that Recurly Engage can authenticate and send push notifications via APNs.

# Key benefits

* **Native iOS delivery**: Reach iPhone, iPad, and Apple TV clients with rich notifications.
* **Secure token-based auth**: Use modern JWT token keys to avoid expired certificates.
* **Centralized management**: Store and rotate your APNs keys within Recurly Engage.

# Key details

### Required Information

Provide the following under **Settings > Push Credentials** in Recurly Engage:

* **APNs Bundle ID**: Your app’s Bundle Identifier.
* **APNs Team ID**: Your Apple Developer Team Identifier.
* **APNs Token Key**: The private key file (`.p8`) generated in Apple Developer.
* **APNs Token Key ID**: The Key ID associated with your `.p8` file.

### Steps to obtain your APNs credentials

1. **Log** **in** to the [Apple Developer Console](https://developer.apple.com/account).
2. **Bundle ID**: **Go** to **Certificates, Identifiers & Profiles → Identifiers**, **select** your app, and **note** the **Bundle ID**.
3. **Team ID**: Under **Membership** (top-right avatar → **Membership**), **locate** your **Team ID**.
4. **Token Key & Key ID**: **Navigate** to **Certificates, Identifiers & Profiles → Keys**, **click** **+** to create a new key with **Apple Push Notification service (APNs)** enabled.

   * **Give** your key a name.
   * After creation, **download** the `.p8` file.
   * **Record** the **Key ID** (displayed next to your key name).

Once imported, toggle your APNs credentials to **Active** in Recurly Engage to begin sending push prompts to iOS/tvOS users.