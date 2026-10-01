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
<div class="rp-page">
  <div class="rp-overview">Use these recommended aspect ratios, sizes, and Cascading Style Sheets (CSS) selectors to design Recurly Engage prompts that look right on desktop and mobile browsers.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly Engage subscription plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have <strong>Company</strong>, <strong>App Administrator</strong>, or <strong>App Member</strong> permissions in Recurly Engage.</li>
</ul>

# Definition

<div class="rp-definition">The Default Prompt Sizes settings define recommended aspect ratios, dimensions, and CSS selectors for each prompt type on desktop and mobile browsers.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-object-group" aria-hidden="true"></i></div>
    <strong>Consistent appearance</strong>
    <span>Standardize prompt dimensions for a unified look and feel.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-mobile-screen-button" aria-hidden="true"></i></div>
    <strong>Responsive design</strong>
    <span>Use optimized sizes for both desktop and mobile environments.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-code" aria-hidden="true"></i></div>
    <strong>Developer-friendly</strong>
    <span>Use the exposed CSS selectors to style and customize prompts.</span>
  </div>
</div>

# Key details

## Horizontal

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Setting</td><td>Value</td></tr>
  <tr><td>Supported aspect ratios (desktop)</td><td>2:1, 4:1, 6:1, 8:1, 10:1</td></tr>
  <tr><td>Recommended size (desktop)</td><td>960 × 300 px</td></tr>
  <tr><td>Recommended size (mobile browser)</td><td>300 × 200 px</td></tr>
</table>

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Environment</td><td>CSS selector</td><td>Controls</td></tr>
  <tr><td>Desktop</td><td><code>.tile-header-msg-wrp</code></td><td>Text container</td></tr>
  <tr><td>Desktop</td><td><code>.promo-tile-wrapper-header</code></td><td>Prompt title</td></tr>
  <tr><td>Desktop</td><td><code>.promo-tile-wrapper-body</code></td><td>Prompt message</td></tr>
  <tr><td>Desktop</td><td><code>.promo-tile-wrapper-footer</code></td><td>Buttons container</td></tr>
  <tr><td>Mobile browser</td><td><code>.rtile-mweb-content-msg</code></td><td>Text container</td></tr>
  <tr><td>Mobile browser</td><td><code>.rtile-mweb-content-footer</code></td><td>Buttons container</td></tr>
</table>

## Vertical

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Setting</td><td>Value</td></tr>
  <tr><td>Supported aspect ratios (desktop)</td><td>1:2, 1:3, 1:4</td></tr>
  <tr><td>Recommended size (desktop)</td><td>250 × 500 px</td></tr>
  <tr><td>Recommended size (mobile browser)</td><td>200 × 300 px</td></tr>
</table>

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Environment</td><td>CSS selector</td><td>Controls</td></tr>
  <tr><td>Desktop</td><td><code>.tile-header-msg-wrp</code></td><td>Text container</td></tr>
  <tr><td>Desktop</td><td><code>.promo-tile-wrapper-header</code></td><td>Prompt title</td></tr>
  <tr><td>Desktop</td><td><code>.promo-tile-wrapper-body</code></td><td>Prompt message</td></tr>
  <tr><td>Desktop</td><td><code>.promo-tile-wrapper-footer</code></td><td>Buttons container</td></tr>
  <tr><td>Mobile browser</td><td><code>.rtile-mweb-content-msg</code></td><td>Text container</td></tr>
  <tr><td>Mobile browser</td><td><code>.rtile-mweb-content-footer</code></td><td>Buttons container</td></tr>
</table>

## Tile

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Setting</td><td>Value</td></tr>
  <tr><td>Supported aspect ratios (desktop)</td><td>1:1, 1:2</td></tr>
  <tr><td>Recommended size (desktop)</td><td>250 × 500 px</td></tr>
  <tr><td>Recommended size (mobile browser)</td><td>375 × 205 px</td></tr>
</table>

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Environment</td><td>CSS selector</td><td>Controls</td></tr>
  <tr><td>Desktop</td><td><code>.tile-header-msg-wrp</code></td><td>Text container</td></tr>
  <tr><td>Desktop</td><td><code>.promo-tile-wrapper-header</code></td><td>Prompt title</td></tr>
  <tr><td>Desktop</td><td><code>.promo-tile-wrapper-body</code></td><td>Prompt message</td></tr>
  <tr><td>Desktop</td><td><code>.promo-tile-wrapper-footer</code></td><td>Buttons container</td></tr>
  <tr><td>Mobile browser</td><td><code>.rtile-mweb-content-msg</code></td><td>Text container</td></tr>
  <tr><td>Mobile browser</td><td><code>.rtile-mweb-content-footer</code></td><td>Buttons container</td></tr>
</table>

## Text only

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Setting</td><td>Value</td></tr>
  <tr><td>Supported aspect ratios (desktop)</td><td>6:1, 8:1, 10:1</td></tr>
  <tr><td>Recommended size (desktop)</td><td>100% × auto</td></tr>
  <tr><td>Recommended size (mobile browser)</td><td>100% × auto</td></tr>
</table>

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Environment</td><td>CSS selector</td><td>Controls</td></tr>
  <tr><td>Desktop</td><td><code>.promo-text-wrapper-container</code></td><td>Text container</td></tr>
  <tr><td>Desktop</td><td><code>.promo-text-title</code></td><td>Prompt title</td></tr>
  <tr><td>Desktop</td><td><code>.promo-text-message</code></td><td>Prompt message</td></tr>
  <tr><td>Mobile browser</td><td><code>.promo-text-wrapper-mobile</code></td><td>Text container</td></tr>
</table>

## Notification

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Setting</td><td>Value</td></tr>
  <tr><td>Recommended size (desktop)</td><td>450 × 180 px</td></tr>
  <tr><td>Recommended size (mobile browser)</td><td>100% × 120 px</td></tr>
</table>

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Environment</td><td>CSS selector</td><td>Controls</td></tr>
  <tr><td>Desktop</td><td><code>.rfmodal-text-container</code></td><td>Text container</td></tr>
  <tr><td>Desktop</td><td><code>.rfmodal-header</code></td><td>Prompt title</td></tr>
  <tr><td>Desktop</td><td><code>.rfmodal-message</code></td><td>Prompt message</td></tr>
  <tr><td>Desktop</td><td><code>.rfmodal-footer</code></td><td>Buttons container</td></tr>
  <tr><td>Mobile browser</td><td><code>.mweb-widget-msg-container</code></td><td>Text container</td></tr>
  <tr><td>Mobile browser</td><td><code>.rfmodal-header-mobileweb</code></td><td>Prompt title</td></tr>
  <tr><td>Mobile browser</td><td><code>.rfmodal-message-mobileweb</code></td><td>Prompt message</td></tr>
  <tr><td>Mobile browser</td><td><code>.rfmodal-footer-mobileweb</code></td><td>Buttons container</td></tr>
</table>

## Interstitial

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Setting</td><td>Value</td></tr>
  <tr><td>Recommended size (desktop)</td><td>1200 × 800 px (text and buttons area)</td></tr>
</table>

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Environment</td><td>CSS selector</td><td>Controls</td></tr>
  <tr><td>Desktop</td><td><code>.rfmodal-text-container</code></td><td>Text container</td></tr>
  <tr><td>Desktop</td><td><code>.rfmodal-header</code></td><td>Prompt title</td></tr>
  <tr><td>Desktop</td><td><code>.rfmodal-message</code></td><td>Prompt message</td></tr>
  <tr><td>Desktop</td><td><code>.rfmodal-footer</code></td><td>Buttons container</td></tr>
  <tr><td>Mobile browser</td><td><code>.mobilewebModalContentWrapper</code></td><td>Text container</td></tr>
  <tr><td>Mobile browser</td><td><code>.rfmodal-header-mobileweb</code></td><td>Prompt title</td></tr>
  <tr><td>Mobile browser</td><td><code>.rfmodal-message-mobileweb</code></td><td>Prompt message</td></tr>
  <tr><td>Mobile browser</td><td><code>.rfmodal-footer-mobileweb</code></td><td>Buttons container</td></tr>
</table>

## Popup

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Setting</td><td>Value</td></tr>
  <tr><td>Recommended sizes (desktop)</td><td>Large: 1200 × 800 px<br/>Medium: 960 × 640 px<br/>Small: 750 × 500 px</td></tr>
  <tr><td>Recommended size (mobile browser)</td><td>500 × 800 px</td></tr>
</table>

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Environment</td><td>CSS selector</td><td>Controls</td></tr>
  <tr><td>Desktop</td><td><code>.rfmodal-text-container</code></td><td>Text container</td></tr>
  <tr><td>Desktop</td><td><code>.rfmodal-header</code></td><td>Prompt title</td></tr>
  <tr><td>Desktop</td><td><code>.rfmodal-message</code></td><td>Prompt message</td></tr>
  <tr><td>Desktop</td><td><code>.rfmodal-footer</code></td><td>Buttons container</td></tr>
  <tr><td>Mobile browser</td><td><code>.mobilewebModalContentWrapper</code></td><td>Text container</td></tr>
  <tr><td>Mobile browser</td><td><code>.rfmodal-header-mobileweb</code></td><td>Prompt title</td></tr>
  <tr><td>Mobile browser</td><td><code>.rfmodal-message-mobileweb</code></td><td>Prompt message</td></tr>
  <tr><td>Mobile browser</td><td><code>.rfmodal-footer-mobileweb</code></td><td>Buttons container</td></tr>
</table>

## Video

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Setting</td><td>Value</td></tr>
  <tr><td>Recommended sizes (desktop)</td><td>Large: 1200 × 619 px<br/>Medium: 960 × 619 px<br/>Small: 750 × 619 px</td></tr>
</table>

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Environment</td><td>CSS selector</td><td>Controls</td></tr>
  <tr><td>Desktop</td><td><code>.rfmodal-text-container</code></td><td>Text container</td></tr>
  <tr><td>Desktop</td><td><code>.rfmodal-header</code></td><td>Prompt title</td></tr>
  <tr><td>Desktop</td><td><code>.rfmodal-message</code></td><td>Prompt message</td></tr>
  <tr><td>Desktop</td><td><code>.rfmodal-footer</code></td><td>Buttons container</td></tr>
  <tr><td>Mobile browser</td><td><code>.mobilewebModalContentWrapper</code></td><td>Text container</td></tr>
  <tr><td>Mobile browser</td><td><code>.rfmodal-header-mobileweb</code></td><td>Prompt title</td></tr>
  <tr><td>Mobile browser</td><td><code>.rfmodal-message-mobileweb</code></td><td>Prompt message</td></tr>
  <tr><td>Mobile browser</td><td><code>.rfmodal-footer-mobileweb</code></td><td>Buttons container</td></tr>
</table>

## Bottom banner

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Setting</td><td>Value</td></tr>
  <tr><td>Recommended size (desktop)</td><td>1000 × 100 px</td></tr>
  <tr><td>Recommended size (mobile browser)</td><td>100% × 120 px</td></tr>
</table>

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Environment</td><td>CSS selector</td><td>Controls</td></tr>
  <tr><td>Desktop</td><td><code>.rfmodal-text-container</code></td><td>Text container</td></tr>
  <tr><td>Desktop</td><td><code>.rfmodal-header</code></td><td>Prompt title</td></tr>
  <tr><td>Desktop</td><td><code>.rfmodal-message</code></td><td>Prompt message</td></tr>
  <tr><td>Desktop</td><td><code>.rfmodal-footer</code></td><td>Buttons container</td></tr>
  <tr><td>Mobile browser</td><td><code>.mweb-widget-msg-container</code></td><td>Text container</td></tr>
  <tr><td>Mobile browser</td><td><code>.rfmodal-header-mobileweb</code></td><td>Prompt title</td></tr>
  <tr><td>Mobile browser</td><td><code>.rfmodal-message-mobileweb</code></td><td>Prompt message</td></tr>
  <tr><td>Mobile browser</td><td><code>.rfmodal-footer-mobileweb</code></td><td>Buttons container</td></tr>
</table>
