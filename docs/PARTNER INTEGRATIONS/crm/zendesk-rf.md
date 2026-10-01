---
title: Zendesk
excerpt: >-
  Configuration guide for the Recurly Engage Zendesk integration, enabling
  support workflows to be triggered directly from prompts.
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
  <div class="rp-overview">The Zendesk integration lets Recurly Engage prompts handle support tasks directly in your Zendesk instance, so common requests don't need a manual hand-off.</div>
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
  <li>Your Zendesk account must support API token authentication, and you must have an admin-generated token.</li>
</ul>

# Definition

<div class="rp-definition">The Zendesk integration allows Recurly Engage prompts to perform support actions, such as creating tickets, assigning agents, and managing user status, directly in your Zendesk instance.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-ticket" aria-hidden="true"></i></div>
    <strong>Automate ticket creation</strong>
    <span>Instantly log support tickets when users interact with prompts.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-list-check" aria-hidden="true"></i></div>
    <strong>Streamline support workflows</strong>
    <span>Assign, prioritize, or suspend users without leaving your app's interface.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-stopwatch" aria-hidden="true"></i></div>
    <strong>Improve response times</strong>
    <span>Reduce manual hand-offs by handling common support tasks programmatically.</span>
  </div>
</div>

# Key details

## Required settings

Provide the following settings:

* **Domain**: Your Zendesk domain (for example, `yourcompany.zendesk.com`).
* **API Key** (also called an API token): Your Zendesk API token.
* **Username**: Your Zendesk account email.

## Supported actions

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Action</td><td>Description</td><td>User dependencies</td><td>Additional instructions</td></tr>
  <tr><td>Create support ticket with notification of offer acceptance</td><td>Creates a support ticket with information about the user and prompt</td><td>n/a</td><td>—</td></tr>
  <tr><td>Set priority of all existing tickets</td><td>Sets priority attribute for all tickets created by the user</td><td><code>zendesk_id</code> or <code>email_address</code></td><td>Select the priority level on the prompt screen</td></tr>
  <tr><td>Assign all existing tickets to a specific agent</td><td>Assigns all tickets created by the user to one agent</td><td><code>zendesk_id</code> or <code>email_address</code></td><td>Select the agent on the prompt screen. Manage agents under <strong>Admin &gt; People &gt; Agents</strong> in Zendesk dashboard</td></tr>
  <tr><td>Suspend user</td><td>Sets the user to suspended state</td><td><code>zendesk_id</code> or <code>email_address</code></td><td>—</td></tr>
  <tr><td>Restore suspended user</td><td>Restores the user from suspended state</td><td><code>zendesk_id</code> or <code>email_address</code></td><td>—</td></tr>
  <tr><td>Assign all existing tickets to a group</td><td>Assigns all tickets created by the user to a group</td><td><code>zendesk_id</code> or <code>email_address</code></td><td>Select the group on the prompt screen. Manage groups under <strong>Admin &gt; People &gt; Groups</strong> in Zendesk dashboard</td></tr>
  <tr><td>Delete all tickets</td><td>Deletes all tickets created by the user</td><td><code>zendesk_id</code> or <code>email_address</code></td><td>—</td></tr>
  <tr><td>Set status of all existing tickets</td><td>Sets status of all tickets created by the user</td><td><code>zendesk_id</code> or <code>email_address</code></td><td>Select the status on the prompt screen</td></tr>
  <tr><td>Delete and spam all existing tickets</td><td>Marks all tickets created by the user as spam</td><td><code>zendesk_id</code> or <code>email_address</code></td><td>—</td></tr>
</table>

## Additional resources

<ul class="rp-list">
  <li><a href="https://support.zendesk.com/hc/en-us/articles/226022787-Generating-a-new-API-token-" target="_blank">Zendesk API token</a></li>
</ul>
