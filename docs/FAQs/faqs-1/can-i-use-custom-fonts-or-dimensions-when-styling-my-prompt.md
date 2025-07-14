---
title: Using custom fonts in a prompt
excerpt: >-
  Configuration guide for applying custom fonts to Recurly Engage prompts using
  Custom CSS.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# How can I use custom fonts in a prompt?

You can apply any web-loaded font to your prompt elements via the **Custom CSS** section in the prompt Editor. Refer to the [styling guide](styling-fine-tuning-css-selectors) for the full list of CSS classes available for prompt styling.

<Image align="center" className="border" border={true} src="https://files.readme.io/396ca85-image.png" />

For example, to set the modal content wrapper to use Roboto:

```css
.rfmodal-content-wrapper {
  font-family: "Roboto", sans-serif!important;
}
```

> **Notes:**
>
> * Only use fonts that are already loaded on your website.
> * Custom fonts won’t render in the Editor’s built-in preview, but they will display correctly when using **Live Preview** or on the live site, provided your site loads those font files.