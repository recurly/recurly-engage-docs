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
<div class="rp-page">
<div class="rp-overview">Mobile interstitials are native, full-screen prompts that render directly inside your mobile app to spotlight offers, announcements, or calls to action. Configure text, colors, buttons, and triggers from the Recurly Engage admin console, and the SDK handles the native rendering on iOS and Android.</div>
<div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly Engage plans</div>
<div class="rp-toc">
<a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
<a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
<a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
</div>
</div>

### Prerequisites

<ul class="rp-list">
<li>Company, App Administrator, or App Member permissions in Recurly Engage.</li>
</ul>

# Definition

<div class="rp-definition">A mobile interstitial is a native-style, full-screen prompt delivered within your mobile app to highlight offers, announcements, or calls to action.</div>

# Key benefits

<div class="rp-benefits">
<div class="rp-benefit"><div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div><strong>Full-screen impact</strong><span>Captures the entire device viewport for maximum visibility.</span></div>
<div class="rp-benefit"><div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div><strong>Native rendering</strong><span>Uses the device SDK to ensure smooth performance and consistent styling.</span></div>
<div class="rp-benefit"><div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div><strong>Flexible configuration</strong><span>Customize text, visuals, and interactive buttons for mobile-specific use cases.</span></div>
</div>

# Key details

Recurly Engage supports the creation and delivery of full-screen interstitials on mobile devices such as iPhones and Android phones.


<Image src="https://files.readme.io/fb9833de82d86aafb60d172d84d67b7c7b2d7d361dbecf2bd8419825736f7e54-Screenshot_2024-10-01_at_3.36.35_PM.png" align="center" width="40%" border={true} />


## UI elements

Use the Recurly Engage admin console to configure these properties; the SDK renders native buttons at runtime.

<table class="rp-params">
<tr class="rp-thead-row"><td>Item</td><td>Type</td><td>Description</td></tr>
<tr><td>Title</td><td>Text</td><td>Headline text</td></tr>
<tr><td>Message</td><td>Text</td><td>Message body</td></tr>
<tr><td>Background color</td><td>Hex color</td><td>Solid background color</td></tr>
<tr><td>Background image</td><td>Image</td><td>Full-screen background image</td></tr>
<tr><td>Legal text</td><td>Text</td><td>Legal disclaimer</td></tr>
<tr><td>Close button</td><td>Radio</td><td>Allow the user to close the prompt, or force it to display for a set time</td></tr>
<tr><td>Close timer</td><td>Number</td><td>Countdown in seconds before auto-close</td></tr>
<tr><td><strong>Buttons</strong></td><td></td><td>Up to three native SDK buttons</td></tr>
<tr><td>• Text</td><td>Text</td><td>Button label</td></tr>
<tr><td>• Text color</td><td>Hex color</td><td>Button text color</td></tr>
<tr><td>• Background</td><td>Hex color</td><td>Button background color (8-character hex with alpha)</td></tr>
<tr><td>• Font family</td><td>Dropdown</td><td>System fonts on iOS or Android</td></tr>
<tr><td>• Border radius</td><td>Number</td><td>Corner radius, in pixels</td></tr>
<tr><td>• Border color</td><td>Hex color</td><td>Button border color (8-character hex with alpha)</td></tr>
<tr><td>• Border width</td><td>Number</td><td>Border thickness, in pixels</td></tr>
<tr><td>• In-app SKU</td><td>Text</td><td>In-app purchase product or SKU code</td></tr>
<tr><td>• Deep link</td><td>Link</td><td>Deep link URL</td></tr>
</table>

## Triggers

Configure when to show the prompt by specifying a screen name or element click ID in your app. For implementation details, see the Recurly Engage <a href="ios-sdk" target="_blank">iOS</a> and <a href="android-sdk" target="_blank">Android</a> SDK docs.
