---
title: 'Overview: Recurly Engage'
excerpt: >-
  High-level architecture and integration overview of the Recurly Engage
  platform—SDKs, console, core processor, and supported third-party connectors.
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
  <div class="rp-overview">Recurly Engage is an always-on, low-code platform that helps business teams deliver targeted in-app and web prompts, guides, and notifications — driving user actions they might not otherwise take. Use cases range from trial-to-paid conversion and feature adoption to churn prevention and cross-sell campaigns. Explore our <a href="/docs/popular-uses" target="_blank">Popular use cases</a> to see it in action.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available to Recurly Engage customers — contact <a href="mailto:support@recurly.com">support@recurly.com</a> or your CSM for details</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">1</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">2</span>Key details</a>
    <a class="rp-toc-pill" href="#recurly-engage-as-a-standalone-platform"><span class="rp-toc-num">3</span>Standalone platform</a>
    <a class="rp-toc-pill" href="#security-and-compliance"><span class="rp-toc-num">4</span>Security and compliance</a>
  </div>
</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-rocket" aria-hidden="true"></i></div>
    <strong>Rapid deployment</strong>
    <span>Launch prompts without engineering cycles, using tag managers or direct SDK integration.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-bullseye" aria-hidden="true"></i></div>
    <strong>Real-time personalization</strong>
    <span>Dynamic segmentation and machine learning deliver the right message to the right user at the right moment.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-plug" aria-hidden="true"></i></div>
    <strong>One-click integrations</strong>
    <span>Connectors across billing, support, marketing, CRM, and analytics systems.</span>
  </div>
</div>

# Key details

Recurly Engage combines lightweight client SDKs, a central management console, and a real-time data processor to get the right message to the right subscriber. The diagram below shows how these pieces fit together.


<Image src="https://files.readme.io/2a163da-image.png" align="center" width="75%" caption="The Recurly Engage platform" />


## Client SDKs

Lightweight clients collect events and render prompts and guides across web and devices.

- **Web**: install via <a href="/docs/google-tag-manager" target="_blank">Google Tag Manager</a>, <a href="/docs/tealium-iq-tag-manager" target="_blank">Tealium</a>, or a direct snippet.
- **Mobile and TV**: native libraries for <a href="/docs/ios-sdk" target="_blank">iOS</a>, Android, Apple TV, and Roku.

## Management console (Pulse)

Pulse is the central hub for configuring applications, user traits, segments, prompts, guides, and integrations.

- **Dashboards and pipelines**: monitor account-wide metrics and dynamic user pipelines.
- **Experiments**: A/B test prompt variations against custom goals.

## Stream data processor

A real-time engine segments incoming events into cohorts using rule-based or machine learning logic. These segments feed prompt targeting and journey orchestration.

## Third-party integrations

Recurly Engage connects to a broad ecosystem of one-click connectors across business domains:

- **Billing and subscription**: <a href="/docs/recurly-integration" target="_blank">Recurly</a>, <a href="/docs/zuora" target="_blank">Zuora</a>, <a href="/docs/stripe-rf" target="_blank">Stripe</a>, <a href="/docs/vindicia-rf" target="_blank">Vindicia</a>, <a href="/docs/braintree-rf" target="_blank">Braintree</a>, and <a href="/docs/piano" target="_blank">Piano</a>
- **Support and CRM**: <a href="/docs/zendesk-rf" target="_blank">Zendesk</a>, <a href="/docs/freshdesk" target="_blank">Freshdesk</a>, <a href="/docs/salesforce-marketing-cloud" target="_blank">Salesforce</a>, <a href="/docs/activecampaign" target="_blank">ActiveCampaign</a>, <a href="/docs/braze" target="_blank">Braze</a>, <a href="/docs/sendgrid" target="_blank">SendGrid</a>, and <a href="/docs/segment" target="_blank">Segment</a>
- **Marketing automation**: <a href="/docs/salesforce-marketing-cloud" target="_blank">Salesforce Marketing Cloud</a>, <a href="/docs/iterable" target="_blank">Iterable</a>, and <a href="/docs/adobe-aep-ajo" target="_blank">Adobe Campaign</a>
- **Ecommerce**: <a href="/docs/shopify" target="_blank">Shopify</a>, <a href="/docs/cleeng" target="_blank">Cleeng</a>, and <a href="/docs/chargify" target="_blank">Chargify</a>
- **Analytics**: <a href="/docs/google-analytics" target="_blank">Google Analytics</a>, <a href="/docs/amplitude" target="_blank">Amplitude</a>, <a href="/docs/mixpanel" target="_blank">Mixpanel</a>, <a href="/docs/mparticle" target="_blank">mParticle</a>, <a href="/docs/heap" target="_blank">Heap</a>, and <a href="/docs/adobe-analytics" target="_blank">Adobe Analytics</a>

Use these integrations to sync user data, trigger one-click actions, and report prompt events across your tech stack.

# Recurly Engage as a standalone platform

Recurly Engage is also available as a standalone platform for your entire subscriber base — no Recurly billing required. It supports acquisition, engagement, retention, upsell, and cross-sell across the full subscriber lifecycle. Reach out and our team will review your specific use cases to see whether Engage is the right fit.

<a class="rp-btn-primary" href="mailto:support@recurly.com" target="_blank">Contact us for pricing →</a>

# Security and compliance

Pulse, the Recurly Engage management console, is HIPAA compliant.

<div class="rp-callout rp-callout-warning">
  <div><strong><i class="fa-solid fa-triangle-exclamation" aria-hidden="true"></i> Warning</strong>To stay compliant with standards such as PCI-DSS and HIPAA, do not include sensitive information — such as protected health information (PHI) or credit card numbers — in any form or template processed by Recurly Engage.</div>
</div>
