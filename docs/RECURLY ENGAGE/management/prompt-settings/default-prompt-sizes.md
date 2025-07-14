---
title: Default prompt sizes
excerpt: >-
  Configuration guide for default prompt sizes and CSS controls in Recurly
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
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

### Prerequisites & limitations

* You must have **Company**, **App Administrator**, or **App Member** permissions in Recurly Engage.

# Definition

The **Default Prompt Sizes** settings define recommended aspect ratios, dimensions, and CSS selectors for each prompt type on desktop and mobile browsers.

# Key benefits

* **Consistent appearance**: Standardize prompt dimensions for a unified look and feel.
* **Responsive design**: Provide optimized sizes for both desktop and mobile environments.
* **Developer-friendly**: Expose CSS selectors to facilitate styling and customization.

# Key details

## Horizontal

* **Supported aspect ratios (desktop)**: 2:1, 4:1, 6:1, 8:1, 10:1
* **Recommended size (desktop)**: 960 × 300 px
* **Recommended size (mobile browser)**: 300 × 200 px
* **CSS controls (desktop)**:
  * `.tile-header-msg-wrp` – Text container
  * `.promo-tile-wrapper-header` – Prompt title
  * `.promo-tile-wrapper-body` – Prompt message
  * `.promo-tile-wrapper-footer` – Buttons container
* **CSS controls (mobile browser)**:
  * `.rtile-mweb-content-msg` – Text container
  * `.rtile-mweb-content-footer` – Buttons container

## Vertical

* **Supported aspect ratios (desktop)**: 1:2, 1:3, 1:4
* **Recommended size (desktop)**: 250 × 500 px
* **Recommended size (mobile browser)**: 200 × 300 px
* **CSS controls (desktop)**:
  * `.tile-header-msg-wrp` – Text container
  * `.promo-tile-wrapper-header` – Prompt title
  * `.promo-tile-wrapper-body` – Prompt message
  * `.promo-tile-wrapper-footer` – Buttons container
* **CSS controls (mobile browser)**:
  * `.rtile-mweb-content-msg` – Text container
  * `.rtile-mweb-content-footer` – Buttons container

## Tile

* **Supported aspect ratios (desktop)**: 1:1, 1:2
* **Recommended size (desktop)**: 250 × 500 px
* **Recommended size (mobile browser)**: 375 × 205 px
* **CSS controls (desktop)**:
  * `.tile-header-msg-wrp` – Text container
  * `.promo-tile-wrapper-header` – Prompt title
  * `.promo-tile-wrapper-body` – Prompt message
  * `.promo-tile-wrapper-footer` – Buttons container
* **CSS controls (mobile browser)**:
  * `.rtile-mweb-content-msg` – Text container
  * `.rtile-mweb-content-footer` – Buttons container

## Text only

* **Supported aspect ratios (desktop)**: 6:1, 8:1, 10:1
* **Recommended size (desktop)**: 100% × auto
* **Recommended size (mobile browser)**: 100% × auto
* **CSS controls (desktop)**:
  * `.promo-text-wrapper-container` – Text container
  * `.promo-text-title` – Prompt title
  * `.promo-text-message` – Prompt message
* **CSS controls (mobile browser)**:
  * `.promo-text-wrapper-mobile` – Text container

## Notification

* **Recommended size (desktop)**: 450 × 180 px
* **Recommended size (mobile browser)**: 100% × 120 px
* **CSS controls (desktop)**:
  * `.rfmodal-text-container` – Text container
  * `.rfmodal-header` – Prompt title
  * `.rfmodal-message` – Prompt message
  * `.rfmodal-footer` – Buttons container
* **CSS controls (mobile browser)**:
  * `.mweb-widget-msg-container` – Text container
  * `.rfmodal-header-mobileweb` – Prompt title
  * `.rfmodal-message-mobileweb` – Prompt message
  * `.rfmodal-footer-mobileweb` – Buttons container

## Interstitial

* **Recommended size (desktop)**: 1200 × 800 px (text & buttons area)
* **CSS controls (desktop)**:
  * `.rfmodal-text-container` – Text container
  * `.rfmodal-header` – Prompt title
  * `.rfmodal-message` – Prompt message
  * `.rfmodal-footer` – Buttons container
* **CSS controls (mobile browser)**:
  * `.mobilewebModalContentWrapper` – Text container
  * `.rfmodal-header-mobileweb` – Prompt title
  * `.rfmodal-message-mobileweb` – Prompt message
  * `.rfmodal-footer-mobileweb` – Buttons container

## Popup

* **Recommended sizes (desktop)**:
  * Large: 1200 × 800 px
  * Medium: 960 × 640 px
  * Small: 750 × 500 px
* **Recommended size (mobile browser)**: 500 × 800 px
* **CSS controls (desktop)**:
  * `.rfmodal-text-container` – Text container
  * `.rfmodal-header` – Prompt title
  * `.rfmodal-message` – Prompt message
  * `.rfmodal-footer` – Buttons container
* **CSS controls (mobile browser)**:
  * `.mobilewebModalContentWrapper` – Text container
  * `.rfmodal-header-mobileweb` – Prompt title
  * `.rfmodal-message-mobileweb` – Prompt message
  * `.rfmodal-footer-mobileweb` – Buttons container

## Video

* **Recommended sizes (desktop)**:
  * Large: 1200 × 619 px
  * Medium: 960 × 619 px
  * Small: 750 × 619 px
* **CSS controls (desktop)**:
  * `.rfmodal-text-container` – Text container
  * `.rfmodal-header` – Prompt title
  * `.rfmodal-message` – Prompt message
  * `.rfmodal-footer` – Buttons container
* **CSS controls (mobile browser)**:
  * `.mobilewebModalContentWrapper` – Text container
  * `.rfmodal-header-mobileweb` – Prompt title
  * `.rfmodal-message-mobileweb` – Prompt message
  * `.rfmodal-footer-mobileweb` – Buttons container

## Bottom banner

* **Recommended size (desktop)**: 1000 × 100 px
* **Recommended size (mobile browser)**: 100% × 120 px
* **CSS controls (desktop)**:
  * `.rfmodal-text-container` – Text container
  * `.rfmodal-header` – Prompt title
  * `.rfmodal-message` – Prompt message
  * `.rfmodal-footer` – Buttons container
* **CSS controls (mobile browser)**:
  * `.mweb-widget-msg-container` – Text container
  * `.rfmodal-header-mobileweb` – Prompt title
  * `.rfmodal-message-mobileweb` – Prompt message
  * `.rfmodal-footer-mobileweb` – Buttons container