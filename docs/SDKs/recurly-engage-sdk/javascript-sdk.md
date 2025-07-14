---
title: Javascript (Web and CTV)
excerpt: >-
  Configuration guide for the JavaScript SDK, supporting both web browsers and
  HTML5-based CTV devices in Recurly Engage.
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

The **JavaScript SDK** enables prompt delivery and tracking in standard web browsers as well as HTML5-based connected TV (CTV) platforms.

# Key benefits

* **Cross-platform support**: Use a single SDK for both web and CTV environments.
* **Custom device targeting**: Deliver prompts selectively to named CTV devices.
* **Consistent user ID fetching**: Ensure correct user identification across different app contexts.

# Key details

The JavaScript SDK supports web browsers as well as HTML5-based CTV devices. To install the JavaScript SDK, please visit this [article](add-the-redfast-tag).

## CTV Considerations

We recommend the following when integrating the JS SDK on CTV apps:

* **Create** **Custom Devices** under **Settings > Custom Devices**. **Define** entries like `SamsungTV`, `LGTV`, or `Vidaa`.
* **Create** prompts targeted to each Custom Device to control delivery on specific CTV platforms.
* **Include** the `data-rf-device-type` attribute in your script tag. For example:

```html
<script src="https://cdn.redfast.com/sdk.js" data-rf-device-type="SamsungTV"></script>
```