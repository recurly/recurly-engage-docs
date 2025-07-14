---
title: Prompt Attributes
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Base Attributes

Redfast generally offloads the visual aspects of prompt creation within the design section. We take all visual settings of a particular personalization and combine it into an image url located in an attribute named `rf_settings_bg_image_[DEVICE_NAME]_composite`, which can be rendered as specified.

Alternatively, you may opt to produce a fully custom experience by accessing the properties annotated in the images below.

<Image align="center" src="https://files.readme.io/b75ab10-device-render-1.png" />

### Additional Behaviors

To add behaviors such as deep linking, redirects, or other custom behaviors a device developer is required. The following attributes are used in order to implement behaviors such as content deep linking, redirects, and other custom actions.

<Image align="center" src="https://files.readme.io/a0221ae-device-render-2.png" />

<br />

# Attributes by Device

This document provides an overview of all prompt attributes supported per device platform. 

Please note that the attribute names still follow a legacy naming convention for backwards compatibility.

* "Confirm", "Accept" prefix means "Button 1"
* "Button" means "Button 1"
* "Cancel" or "Decline" means "Button 3"
* "Accept2" means "Button 2"\
  For example, "rf\_retention\_confirm\_button\_text" refers to Button 1 text.

<Embed url="https://assets.redfastlabs.com/docs/matrix.html" provider="assets.redfastlabs.com" href="https://assets.redfastlabs.com/docs/matrix.html" typeOfEmbed="iframe" height="1000px" width="100%" iframe="true" title="undefined" />
