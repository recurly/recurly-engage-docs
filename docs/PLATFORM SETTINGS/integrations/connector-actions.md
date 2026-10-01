---
title: External
excerpt: >-
  How to configure and use connector actions in Recurly Engage to interact with
  third‑party services.
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
  <div class="rp-overview">Connector actions let your in-app prompts do real work in the rest of your stack. When a user interacts with a prompt, Recurly Engage can trigger the right operation in your billing, marketing, support, or analytics tools automatically.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly Engage plans</div>
  <div class="rp-cost">
    <strong>Additional cost</strong><br/>
    Adobe and Salesforce integrations can be purchased for an add-on fee. Contact <a href="mailto:support@recurly.com">support@recurly.com</a> or your Recurly account manager for pricing details.
  </div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have <span style={{fontWeight: "bold"}}>Company</span> or <span style={{fontWeight: "bold"}}>App Administrator</span> permissions in Engage.</li>
  <li>Relevant third-party accounts and API credentials must be provisioned before you configure connectors.</li>
</ul>

# Definition

<div class="rp-definition">Connector actions are predefined integrations that let you execute operations in external systems when users interact with your in-app prompts, such as clicking a call to action (CTA). You configure these actions in the Engage console, and they're invoked automatically at runtime.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Automate workflows</strong>
    <span>Trigger downstream processes like billing updates or customer relationship management (CRM) entries without manual intervention.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Unified interface</strong>
    <span>Manage all third-party integrations from a single console.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Flexible triggers</strong>
    <span>Actions can run on accept, secondary accept, decline, dismiss, or timeout events.</span>
  </div>
</div>

# Key details

Connector actions require that certain user attributes (for example, account IDs, email addresses, and device tokens) be synced into Engage beforehand. See each connector's documentation for specific data dependencies.

## Connector categories and links

### Billing

<div class="rp-sdk-grid">

<Cards>
  <Card title="Recurly" href="recurly-integration" target="_blank"></Card>
  <Card title="Stripe" href="stripe-rf" target="_blank"></Card>
  <Card title="Zuora" href="zuora" target="_blank"></Card>
  <Card title="Braintree" href="braintree-rf" target="_blank"></Card>
  <Card title="Chargify" href="chargify" target="_blank"></Card>
  <Card title="Vindicia" href="vindicia-rf" target="_blank"></Card>
  <Card title="In-app purchases" href="app-stores-rf" target="_blank"></Card>
  <Card title="Shopify" href="shopify-rf" target="_blank"></Card>
  <Card title="Cleeng" href="cleeng" target="_blank"></Card>
</Cards>
</div>

The In-app purchases connector covers Apple, Google, Amazon, and Roku.

### CRM & marketing

<div class="rp-sdk-grid">

<Cards>
  <Card title="Salesforce Marketing Cloud" href="salesforce-marketing-cloud" target="_blank"></Card>
  <Card title="Segment" href="segmentio-twilio" target="_blank"></Card>
  <Card title="Braze" href="braze-rf" target="_blank"></Card>
  <Card title="SendGrid" href="sendgrid" target="_blank"></Card>
  <Card title="ActiveCampaign" href="activecampaign" target="_blank"></Card>
  <Card title="Freshdesk" href="freshdesk" target="_blank"></Card>
  <Card title="Zendesk" href="zendesk-rf" target="_blank"></Card>
  <Card title="Adobe (AEP & AJO)" href="adobe-aep-ajo" target="_blank"></Card>
</Cards>
</div>

### Analytics & events

<div class="rp-sdk-grid">

<Cards>
  <Card title="Google Analytics" href="google-analytics" target="_blank"></Card>
  <Card title="Mixpanel" href="mixpanel" target="_blank"></Card>
  <Card title="mParticle" href="mparticle" target="_blank"></Card>
  <Card title="Heap" href="heap" target="_blank"></Card>
</Cards>
</div>

## Configuring a connector

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open Actions settings</h4><p>Navigate to <span style={{fontWeight: "bold"}}>Settings &gt; Actions</span> in the Engage console.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Select a connector</h4><p>Select the connector you want from the list.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Enter your credentials</h4><p>Enter the required API credentials and configuration fields.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Activate the connector</h4><p>Toggle <span style={{fontWeight: "bold"}}>Active</span> and click <span style={{fontWeight: "bold"}}>Save</span>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/3f60efa-image.png" align="center" width="75%" border={true} />


After activation, connector actions appear in each prompt’s **Actions** configuration panel, where you can assign them to specific user interaction events.
