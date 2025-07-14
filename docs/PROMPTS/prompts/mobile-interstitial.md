---
title: Mobile interstitial prompts
excerpt: >-
  Guide to creating and managing full-screen mobile interstitial prompts in
  Recurly Engage.
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

* You must have **Company**, **App Administrator** or **App member** permissions in Recurly Engage.

# Definition

A **mobile interstitial** is a native-style, full-screen prompt delivered within your mobile app to highlight offers, announcements, or calls to action.

# Key benefits

* **Full-screen impact**: Captures the entire device viewport for maximum visibility.
* **Native rendering**: Uses device SDK to ensure smooth performance and consistent styling.
* **Flexible configuration**: Customize text, visuals, and interactive buttons for mobile-specific use cases.

# Key details

Redfast supports the creation and delivery of full-screen interstitials on mobile devices such as iPhones and Android phones.

<Image align="center" width="30% " src="https://files.readme.io/fb9833de82d86aafb60d172d84d67b7c7b2d7d361dbecf2bd8419825736f7e54-Screenshot_2024-10-01_at_3.36.35_PM.png" />

<br />

## UI Elements

Use the Recurly Engage admin console to configure these properties; the SDK will render native buttons at runtime.

| Item             | Type      | Description                                     |
| :--------------- | :-------- | :---------------------------------------------- |
| Title            | Text      | Headline text                                   |
| Message          | Text      | Message body                                    |
| Background color | Hex color | Solid background color                          |
| Background Image | Image     | Full-screen background image                    |
| Legal text       | Text      | Legal disclaimer                                |
| Close button     | Radio     | Allow user to close or force display time       |
| Close timer      | Number    | Countdown in seconds before auto-close          |
| **Buttons**      |           | Up to three native SDK buttons                  |
| • Text           | Text      | Button label                                    |
| • Text color     | Hex color | Button text color                               |
| • Background     | Hex color | Button background color (8‑char hex with alpha) |
| • Font family    | Dropdown  | System fonts on iOS or Android                  |
| • Border radius  | Number    | Corner radius (px)                              |
| • Border color   | Hex color | Button border color (8‑char hex with alpha)     |
| • Border width   | Number    | Border thickness (px)                           |
| • In App SKU     | Text      | In-app purchase product/SKU code                |
| • Deep Link      | Link      | Deep link URL                                   |

## Triggers

Configure when to show the prompt by specifying screen name or element click ID in your app. For implementation details, see the Redfast [iOS](ios-sdk) and [Android SDK](android-sdk) docs.