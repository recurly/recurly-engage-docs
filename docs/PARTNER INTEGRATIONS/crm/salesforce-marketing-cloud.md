---
title: Salesforce
excerpt: >-
  Configuration guide for the Salesforce connector in Recurly Engage—setup,
  credentials, and supported actions for Support Cloud and Marketing Cloud.
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
  <div class="rp-overview">Connect Recurly Engage to Salesforce Support Cloud, Marketing Cloud, or both to handle support and marketing workflows directly from prompts.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available as an add-on for any Recurly Engage subscription plan</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have <strong>Company</strong> or <strong>App Administrator</strong> permissions in Recurly Engage.</li>
  <li>You must have active Salesforce Support Cloud licenses, Marketing Cloud licenses, or both.</li>
</ul>

# Definition

<div class="rp-definition">The Salesforce connector streams Recurly Engage prompt events and actions into Salesforce, so you can create cases, post feed items, send Marketing Cloud emails, and manage subscriber lists directly from prompts.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-headset" aria-hidden="true"></i></div>
    <strong>Real-time case creation</strong>
    <span>Automatically generate support cases from user interactions.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-rss" aria-hidden="true"></i></div>
    <strong>Feed updates</strong>
    <span>Log offer acceptances to existing case feeds for full context.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-envelope" aria-hidden="true"></i></div>
    <strong>Marketing Cloud sends</strong>
    <span>Trigger personalized email sends and list subscriptions without leaving the prompt UI.</span>
  </div>
</div>

# Key details

## Support Cloud credentials

Under **Settings → Connectors → Salesforce**, provide:

* **Username**
* **Password**
* **Security Token**
* **Client ID**
* **Client Secret**

## Marketing Cloud credentials

Provide:

* **Client ID**
* **Client Secret**
* **From Email Address**
* **Base URL**
* **Auth Base URL**
* **SOAP Base URL**

## Supported actions

Use these actions in your prompt configurations to drive Salesforce workflows:

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Action</td><td>Description</td><td>User dependencies</td><td>Additional instructions</td><td>Form inputs</td></tr>
  <tr><td><strong>Create a Case (Support)</strong></td><td>Creates a support case in Salesforce with user and prompt details</td><td>n/a</td><td>n/a</td><td>n/a</td></tr>
  <tr><td><strong>Post offer acceptance to feed of existing cases (Support)</strong></td><td>Adds a feed item to all cases associated with the user, detailing offer acceptance</td><td><code>salesforce_id</code> or <code>email_address</code></td><td>n/a</td><td>n/a</td></tr>
  <tr><td><strong>Triggered Send (Marketing Cloud)</strong></td><td>Sends a templated email to the user via Marketing Cloud</td><td><code>email_address</code> (optional)</td><td>Select an email template in the prompt editor; configure dynamic templates in Marketing Cloud.</td><td>optional</td></tr>
  <tr><td><strong>Add Subscriber to List (Marketing Cloud)</strong></td><td>Adds an existing subscriber to a specified list</td><td>n/a</td><td>Select the list in the prompt editor; ensure lists exist in Marketing Cloud dashboard.</td><td>n/a</td></tr>
  <tr><td><strong>Add User to List with Form Input (Marketing Cloud)</strong></td><td>Creates a subscriber based on prompt input and adds them to a specified list</td><td>n/a</td><td>Select the list in the prompt editor; configure form input field for email address.</td><td>required</td></tr>
</table>

## Install the Journey Builder Activity

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Create an installed package</h4><p>In Marketing Cloud Setup, navigate to <span style={{fontWeight: "bold"}}>Apps → Installed Packages</span>, and then select <span style={{fontWeight: "bold"}}>New</span>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Name the package</h4><p>Enter <span style={{fontWeight: "bold"}}>Name</span>: <code>Recurly Engage</code>, and then select <span style={{fontWeight: "bold"}}>Save</span>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Add a component</h4><p>Under <span style={{fontWeight: "bold"}}>Components</span>, select <span style={{fontWeight: "bold"}}>Add Component</span>, choose <span style={{fontWeight: "bold"}}>Journey Builder Activity</span>, and select <span style={{fontWeight: "bold"}}>Next</span>.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Provide the activity details</h4><p>Enter the following values.</p></div>
  </div>
</div>

<ul class="rp-list">
  <li><strong>Name</strong>: <code>Recurly Engage</code></li>
  <li><strong>Category</strong>: <code>Messages</code></li>
  <li><strong>Endpoint URL</strong>: <code>https://jbuilder.recurlyengage.com/&lt;appid&gt;/</code> (find your App ID under <strong>Settings → Application</strong>)</li>
</ul>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Save the activity</h4><p>Save the activity. Recurly Engage now appears as a Message activity in Journey Builder.</p></div>
  </div>
</div>

## Additional resources

<ul class="rp-list">
  <li><a href="https://developer.salesforce.com/forums/?id=906F0000000AfcgIAC" target="_blank">Salesforce Credentials reference</a></li>
  <li><a href="https://salesforce.stackexchange.com/questions/40346/where-do-i-find-the-client-id-and-client-secret-of-an-existing-connected-app/224659#224659" target="_blank">Finding Client ID and Secret</a></li>
</ul>
