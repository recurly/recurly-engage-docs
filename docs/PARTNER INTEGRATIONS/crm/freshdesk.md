---
title: Freshdesk
excerpt: >-
  Configuration guide for the Freshdesk connector in Recurly Engage—API setup
  and supported support ticket and contact management actions.
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
  <div class="rp-overview">The Freshdesk integration lets you create and update support tickets and manage contacts directly from Recurly Engage prompts.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly Engage subscription plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have <strong>Company</strong> or <strong>App Administrator</strong> permissions in Recurly Engage.</li>
  <li>You must have a Freshdesk account with API access and a valid API key.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>Your Freshdesk plan must support API-based ticket and contact management.</li>
</ul>

# Definition

<div class="rp-definition">The Freshdesk connector lets you automate customer support workflows (creating tickets when a user accepts a promo, updating ticket fields in bulk, and managing contacts) through prompt-driven 1-Click actions.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-headset" aria-hidden="true"></i></div>
    <strong>Automated support</strong>
    <span>Instantly generate support tickets from user interactions without manual intervention.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-list-check" aria-hidden="true"></i></div>
    <strong>Bulk ticket updates</strong>
    <span>Adjust priority, status, group, or responder for all tickets tied to a user with one action.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-address-book" aria-hidden="true"></i></div>
    <strong>Contact lifecycle management</strong>
    <span>Soft-delete or restore contacts and purge related tickets on demand.</span>
  </div>
</div>

# Key details

## Required settings

Under **Settings > Connectors > Freshdesk**, provide:

* **Domain**: Your Freshdesk subdomain (for example, `yourcompany.freshdesk.com`).
* **API Key**: Your Freshdesk API token. See <a href="https://support.freshdesk.com/support/solutions/articles/215517-how-to-find-your-api-key" target="_blank">How to find your API key</a>.

## Supported actions

Use these actions in prompt configurations to handle tickets and contacts:

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Action</td><td>Description</td><td>User dependencies</td><td>Additional instructions</td></tr>
  <tr><td><strong>Create support ticket with notification of offer acceptance</strong></td><td>Creates a ticket including user details and promo information</td><td>None</td><td>n/a</td></tr>
  <tr><td><strong>Update existing tickets priority</strong></td><td>Bulk-update priority for all tickets created by the user</td><td><code>freshdesk_id</code> or <code>email_address</code></td><td>Configure new priority level on prompt screen</td></tr>
  <tr><td><strong>Update existing tickets status</strong></td><td>Bulk-update status for all user tickets</td><td><code>freshdesk_id</code> or <code>email_address</code></td><td>Configure new status on prompt screen</td></tr>
  <tr><td><strong>Update existing tickets responder</strong></td><td>Bulk-update ticket responder for all user tickets</td><td><code>freshdesk_id</code> or <code>email_address</code></td><td>Select responder on prompt screen</td></tr>
  <tr><td><strong>Update existing tickets group</strong></td><td>Bulk-update group assignment for all user tickets</td><td><code>freshdesk_id</code> or <code>email_address</code></td><td>Select group on prompt screen</td></tr>
  <tr><td><strong>Update existing tickets source</strong></td><td>Bulk-update ticket source for all user tickets</td><td><code>freshdesk_id</code> or <code>email_address</code></td><td>Select source on prompt screen</td></tr>
  <tr><td><strong>Soft delete a contact</strong></td><td>Mark the contact as deleted in Freshdesk</td><td><code>freshdesk_id</code> or <code>email_address</code></td><td>n/a</td></tr>
  <tr><td><strong>Restore a contact</strong></td><td>Restore a previously soft-deleted contact</td><td><code>freshdesk_id</code> or <code>email_address</code></td><td>n/a</td></tr>
  <tr><td><strong>Delete all tickets</strong></td><td>Permanently delete all tickets associated with the contact</td><td><code>freshdesk_id</code> or <code>email_address</code></td><td>n/a</td></tr>
  <tr><td><strong>Spam all existing tickets</strong></td><td>Mark all tickets created by the user as spam</td><td><code>freshdesk_id</code> or <code>email_address</code></td><td>n/a</td></tr>
</table>
