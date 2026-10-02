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
<div class="rp-page">
  <div class="rp-overview">Use the fonts your website already loads in your Recurly Engage prompts. Add a short Cascading Style Sheets (CSS) rule in the prompt Editor, and your prompt elements use the font you choose.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
</div>

# How can I use custom fonts in a prompt?

You can apply any web-loaded font to your prompt elements in the **Custom CSS** section of the prompt Editor.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open Custom CSS</h4><p>In the prompt Editor, open the <span style={{fontWeight: "bold"}}>Custom CSS</span> section.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/396ca85-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Add your font rule</h4><p>Add a rule that sets the font for the prompt elements you want to style. Refer to the <a href="styling-fine-tuning-css-selectors" target="_blank">styling guide</a> for the full list of CSS classes available for prompt styling.</p></div>
  </div>
</div>

For example, to set the modal content wrapper to use Roboto:

```css
.rfmodal-content-wrapper {
  font-family: "Roboto", sans-serif!important;
}
```

<div class="rp-callout rp-callout-important">
  <div><strong><i class="fa-solid fa-circle-exclamation" aria-hidden="true"></i> Important</strong>Only use fonts that are already loaded on your website.</div>
</div>

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>Custom fonts don’t render in the Editor’s built-in preview, but they display correctly when you use <span style={{fontWeight: "bold"}}>Live Preview</span> or view the live site, provided your site loads those font files.</div>
</div>
