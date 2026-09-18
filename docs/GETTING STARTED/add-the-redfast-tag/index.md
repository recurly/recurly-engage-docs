---
title: Recurly Engage javascript tag
excerpt: >-
  Implementation details for adding the Recurly Engage tag to your site, via tag
  managers or direct script injection.
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
  <div class="rp-overview">Add the Recurly Engage tag to your site to initialize Engage, track user interactions, and power secure, branded checkout flows. Install it directly or through the tag manager you already use.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available to all customers on any Recurly Engage subscription plan</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have <strong>Company</strong>, <strong>App Administrator</strong>, or <strong>App Member</strong> permissions in Recurly Engage.</li>
  <li>You need access to modify your site's HTML or your tag manager container.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>If you're using a tag manager, make sure you have publish permissions.</li>
</ul>

# Definition

<div class="rp-definition">The Recurly Engage tag is a lightweight JavaScript snippet that initializes Engage on your site. It enables tracking of user interactions and powers secure, branded checkout flows within your application.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-puzzle-piece" aria-hidden="true"></i></div>
    <strong>Easy integration</strong>
    <span>Deploy through a popular tag manager without editing page code.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-gauge-high" aria-hidden="true"></i></div>
    <strong>Optimal performance</strong>
    <span>Load asynchronously or deferred to avoid delaying page rendering.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-shuffle" aria-hidden="true"></i></div>
    <strong>Flexible deployment</strong>
    <span>Choose from multiple tag managers, or embed the script directly.</span>
  </div>
</div>

# Key details

The following tag managers are supported for convenience. You can also add the JavaScript directly to your site if you'd rather skip the tag manager.

In most cases, we recommend the `defer` or `async` script attribute to keep the tag from delaying page rendering — the Recurly Engage tag runs once the page has rendered. Reach out to your customer success manager if you have questions about specific requirements.

<div class="rp-sdk-grid">

<Cards>
  <Card title="Google Tag Manager" href="https://docs.recurly.com/recurly-engage/docs/google-tag-manager" target="_blank"></Card>
  <Card title="Adobe Dynamic Tag Manager" href="https://docs.recurly.com/recurly-engage/docs/adobe-dynamic-tag-manager" target="_blank"></Card>
  <Card title="Tealium iQ Tag Manager" href="https://docs.recurly.com/recurly-engage/docs/tealium-iq-tag-manager" target="_blank"></Card>
  <Card title="Direct" href="https://docs.recurly.com/recurly-engage/docs/rengage-direct-tag" target="_blank"></Card>
</Cards>
</div>

## Content Security Policy (CSP) requirements

If your site uses a Content Security Policy, you'll need to allowlist Recurly Engage's domains so the tag can load and communicate correctly. Add the following to your configuration:

<ul class="rp-list">
  <li><strong>Script source (script-src):</strong> your unique company-specific JS tag domain.</li>
  <li><strong>Connect source (connect-src):</strong> <code>conduit.redfast.com</code>, to allow the necessary network traffic.</li>
  <li><strong>Additional domains to allowlist:</strong> <code>assets.redfastlabs.com</code>, <code>sapi.redfast.com</code>, and any other <code>redfast.com</code> or <code>redfastlabs.com</code> domains you encounter.</li>
</ul>

### Why this is necessary

Without these entries, your browser may block the tag from executing or prevent it from sending data to our API. Common failures caused by a missing or misconfigured CSP include:

<ul class="rp-list">
  <li>The tag itself failing to load or execute — blocked by <code>script-src</code></li>
  <li>Prompt data failing to send to or receive from Recurly's API — blocked by <code>connect-src</code></li>
  <li>Images or media within a prompt failing to render — blocked by <code>img-src</code> or <code>media-src</code></li>
  <li>Custom fonts or inline styles failing to apply — blocked by <code>font-src</code> or <code>style-src</code></li>
  <li>Embedded iframes within a prompt failing to load — blocked by <code>frame-src</code></li>
</ul>

If you add a custom background image to a prompt, it may still fail to load even with the CSP entries above in place. This usually happens when your security settings require all image sources to be self-hosted — in that case, host the image on your own infrastructure rather than Recurly's, since Recurly's domain won't be an allowed source under those stricter policies.

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>This is a client-side configuration. Recurly Engage manages CORS on our end, but the CSP itself must be updated in your own site's headers or meta tags.</div>
</div>
