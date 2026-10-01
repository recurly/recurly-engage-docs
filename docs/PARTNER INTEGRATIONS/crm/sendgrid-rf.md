---
title: SendGrid
excerpt: Connect Recurly Engage to SendGrid for dynamic emails and list management
deprecated: false
hidden: false
link:
  new_tab: false
metadata:
  title: ''
  description: ''
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">The SendGrid integration lets you send dynamic template emails and manage subscriber lists directly from Recurly Engage prompts, without custom code.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly Engage subscription plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

# Definition

<div class="rp-definition">The SendGrid connector uses your SendGrid API key to perform two core actions, sending dynamic template emails to users and adding users to SendGrid contact lists, whenever they interact with a prompt in Recurly Engage.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-envelope-open-text" aria-hidden="true"></i></div>
    <strong>On-brand communications</strong>
    <span>Use your SendGrid dynamic templates for polished, consistent emails.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-list" aria-hidden="true"></i></div>
    <strong>Automated list management</strong>
    <span>Instantly add engaged users to segmented SendGrid lists.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-window-maximize" aria-hidden="true"></i></div>
    <strong>Single-pane setup</strong>
    <span>Configure credentials and actions entirely within the Recurly Engage console.</span>
  </div>
</div>

# Key details

## Required settings

Under **Settings → Connectors → SendGrid**, provide:

* **API Key**: Generate and copy it from the <a href="https://sendgrid.com/docs/ui/account-and-settings/api-keys/" target="_blank">SendGrid API Keys</a> page.

## Supported actions

Use these actions within prompt configurations to drive SendGrid workflows:

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Action</td><td>Description</td><td>User dependencies</td><td>Additional instructions</td><td>Form inputs</td></tr>
  <tr><td><strong>Send dynamic template email</strong></td><td>Sends a selected dynamic template to the user</td><td><code>email_address</code> (optional)</td><td>Select your SendGrid dynamic template on the prompt editor. Templates must be pre-configured in SendGrid.</td><td>optional</td></tr>
  <tr><td><strong>Add user to list</strong></td><td>Adds the user to a specified SendGrid list</td><td><code>email_address</code></td><td>Choose the target SendGrid list on the prompt editor. Lists must be created in SendGrid ahead of time.</td><td>n/a</td></tr>
</table>

## Additional information

Learn more about SendGrid lists in the official docs: <a href="https://www.twilio.com/docs/sendgrid/api-reference/lists/create-list" target="_blank">SendGrid Lists API Reference</a>.


<Image src="https://files.readme.io/b2d12bf-sendgrid-lists-1.png" align="center" width="75%" border={true} />



<Image src="https://files.readme.io/ea49a4a-sendgrid-dynamic-templates-2.png" align="center" width="75%" border={true} />
