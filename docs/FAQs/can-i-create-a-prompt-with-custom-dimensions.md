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
<div class="rp-page">
  <div class="rp-overview">Set the exact width and height of a Recurly Engage prompt. Add a short Cascading Style Sheets (CSS) rule in the prompt Editor to override the default size.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
</div>

# How can I create a prompt with custom dimensions?

You can override the default size by adding CSS rules in the **Custom CSS** section of the prompt Editor. For example, to set a popup to 550 × 420 pixels:


<Image src="https://files.readme.io/e357b8c-image.png" align="center" width="75%" border={true} />


```css
.outer-modal {
  width: 550px !important;
  height: 420px !important;
}
```

<div class="rp-callout rp-callout-important">
  <div><strong><i class="fa-solid fa-circle-exclamation" aria-hidden="true"></i> Important</strong>Use <code>!important</code> to ensure your dimensions take precedence over default styles.</div>
</div>

<div class="rp-callout rp-callout-tip">
  <div><strong><i class="fa-solid fa-lightbulb" aria-hidden="true"></i> Tip</strong>Test in <span style={{fontWeight: "bold"}}>Live Preview</span> to verify your custom sizing behaves correctly across devices.</div>
</div>
