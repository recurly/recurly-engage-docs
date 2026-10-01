---
title: Integrations
excerpt: >-
  How to activate and configure third-party connectors for billing, support,
  marketing, and analytics within Recurly Engage.
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
  <div class="rp-overview">Recurly Engage comes with dozens of prebuilt integrations — connectors that let you trigger actions in your existing business systems or stream events to them.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly Engage plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have <span style={{fontWeight: "bold"}}>Company</span> or <span style={{fontWeight: "bold"}}>App Administrator</span> permissions in Engage.</li>
  <li>Connector-specific credentials, such as API keys and client IDs or secrets.</li>
  <li>Appropriate permissions in both Engage and the target system.</li>
</ul>

# Definition

<div class="rp-definition">An <span style={{fontWeight: "bold"}}>integration</span> (or connector) links Engage prompts and user interactions with external platforms, enabling one-click actions, event streaming, and data sync.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Streamline workflows</strong>
    <span>Automate subscription changes, support tickets, emails, and more directly from in-app prompts.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Unified user experience</strong>
    <span>Keep your user's context in sync across billing, customer relationship management (CRM), support, and analytics systems.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Rapid time to value</strong>
    <span>Prebuilt connectors mean you can be live in minutes, not weeks.</span>
  </div>
</div>

# Key details

## Configure external integrations

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open Actions settings</h4><p>Go to <span style={{fontWeight: "bold"}}>Settings → Actions</span>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/3f60efa-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Select a connector</h4><p>Select a connector, such as Zuora.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/2bae331-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Enter your credentials</h4><p>Fill in the required credentials.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/5f1e9d9-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Activate the connector</h4><p>Toggle the connector to <span style={{fontWeight: "bold"}}>Active</span> and click <span style={{fontWeight: "bold"}}>Save changes</span>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/dbee0b4-image.png" align="center" width="75%" border={true} />


## Connector capabilities

### SendGrid

* Send dynamic template email to user’s email address
* Add user to contact list
* Send dynamic template email to a user-submitted address

### Salesforce.com

* Create a Case (Support Cloud)
* Post offer acceptance to feed on all existing Cases

### Zendesk

* Create support ticket with offer details
* Set priority on all tickets by that user
* Assign all existing tickets to a specific agent
* Suspend or restore a user
* Assign tickets to a group
* Delete or spam all existing tickets
* Update ticket status or source

### Stripe

* Subscribe the user to a specific plan
* Unsubscribe the user from a plan
* Add a coupon code at checkout
* Extend a user’s trial period
* Switch subscriptions immediately or at period end

### Zuora

* Subscribe user to a rate plan
* Cancel, suspend, or resume a subscription
* Change auto-renew settings

### Freshdesk

* Create support ticket upon offer acceptance
* Bulk-update ticket priority, status, group, responder, or source
* Soft-delete or restore contacts
* Delete all tickets for a contact

### Recurly

* Apply coupon codes
* Change, pause, resume, or create subscriptions
* Convert trials to paid
* Record usage

### Iterable

* Track custom events in Iterable
* Add users to lists or automations
* Send campaign emails to stored or inputted addresses

### Cleeng

* Switch subscription offers
* Apply coupon codes
* Reactivate subscriptions

### Braze

* Create or update a user record by email

### Apple (APNs)

* Trigger in-app purchase flows (Upgrade/Downgrade)
* Send push notifications via APNs

<div class="rp-callout rp-callout-tip">
  <div><strong><i class="fa-solid fa-lightbulb" aria-hidden="true"></i> Need another connector?</strong>Contact your Engage Customer Success team to request a custom integration or new connector.</div>
</div>
