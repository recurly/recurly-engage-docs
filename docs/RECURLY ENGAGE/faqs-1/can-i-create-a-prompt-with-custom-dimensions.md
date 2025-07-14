---
title: Creating a prompt with custom dimensions
excerpt: >-
  Configuration guide for setting custom dimensions on Recurly Engage prompts
  using Custom CSS.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# How can I create a prompt with custom dimensions?

You can override the default size by adding CSS rules in the **Custom CSS** section of the prompt Editor. For example, to set a popup to 550 × 420 px:

<Image align="center" className="border" border={true} src="https://files.readme.io/e357b8c-image.png" />

```css
.outer-modal {
  width: 550px !important;
  height: 420px !important;
}
````

> **Notes:**
> - Use `!important` to ensure your dimensions take precedence over default styles.
> - Test in **Live Preview** to verify your custom sizing behaves correctly across devices.