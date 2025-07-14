---
title: Adobe dynamic tag manager
excerpt: >-
  Step-by-step instructions for integrating the Recurly Engage JavaScript client
  via Adobe Dynamic Tag Manager.
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

Learn how to deploy the Recurly Engage tag through Adobe Dynamic Tag Manager (DTM) to begin syncing your site’s data with Engage for personalized customer experiences.

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

### Prerequisites & limitations

* You must have publish and rule-creation permissions in your Adobe DTM account.
* Ensure you can add or modify embed code in your site’s header.

# Definition

The **Adobe Dynamic Tag Manager integration** injects the Recurly Engage JavaScript client into your pages using DTM rules and workflows, enabling Engage to collect events and deliver customized checkout experiences.

# Key benefits

* **Seamless deployment**: Use your existing DTM workflows to roll out Engage without touching site code.
* **Controlled release**: Leverage DTM’s approval process to test in staging before going live.
* **Performance-safe**: Host the client via Akamai or your preferred DTM option to minimize latency.

# Key details

## Guide

### Configure embed code

Choose one of three hosting options in DTM, then select where to place the embed tag:

* **Hosting options**

  * Akamai
  * FTP Delivery
  * Library Download
* **Location options**

  * Header
  * Footer

We recommend **Akamai hosting** with the embed tag in the **Header** for fastest load times. For more control, coordinate with your IT team to use the Library Download option.

### Rules

In most cases, use a **Page-Load** rule when targeting your site’s pages.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/b53b37f-rules2.png.img.png" />

### Workflows

Propagate your tag from non-production (staging) to production using DTM’s approval workflow to ensure safe rollouts.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/77107ad-image_8.png.img.png" />

### Installation

Add the DTM header code that loads the Recurly Engage tag to **all pages** of your site.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/cdc7383-image_11.png.img.png" />