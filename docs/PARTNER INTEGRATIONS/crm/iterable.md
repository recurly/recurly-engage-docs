---
title: Iterable
excerpt: >-
  Configuration guide for the Iterable connector in Recurly Engage—setup and
  supported messaging and lifecycle actions for cross-channel marketing.
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
  <div class="rp-overview">Iterable is a customer engagement platform that helps you segment audiences and automate personalized messaging. By integrating it with Recurly Engage, you can trigger real-time lifecycle events, manage list memberships, and send targeted email campaigns directly from your recovery and engagement prompts.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

# Definition

<div class="rp-definition">The Iterable connector integrates Recurly Engage with the Iterable API to track custom user behavior, manage audience segmentation through lists, and trigger immediate email communications during the customer journey.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-gears" aria-hidden="true"></i></div>
    <strong>Behavioral automation</strong>
    <span>Post events to Iterable to trigger complex journeys or "Workflows" based on subscription status changes.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-users" aria-hidden="true"></i></div>
    <strong>Dynamic segmentation</strong>
    <span>Automatically add users to specific "Win-back" or "Retention" lists when they interact with a prompt.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-envelope" aria-hidden="true"></i></div>
    <strong>Instant communication</strong>
    <span>Send targeted campaign emails immediately to users (or specified alternative emails) to improve recovery rates.</span>
  </div>
</div>

# Key details

## Connect Iterable

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open the Iterable integration</h4><p>In Recurly Engage, navigate to <span style={{fontWeight: "bold"}}>Settings &gt; Integrations &gt; Iterable</span>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Enter your API key</h4><p>Use your Iterable API key to connect to Recurly Engage.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/779767b48a8ef353dfd317d14e6d942971ce1a19b769f97024bee940ada28cc9-image.png" align="center" width="75%" border={true} />


## Supported actions

Use these actions within prompt configurations (such as Accept and Secondary Accept) to drive Iterable workflows:

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Action</td><td>Description</td><td>API method</td></tr>
  <tr><td>Post an event to Iterable</td><td>Record a custom action (for example, "Prompt Viewed") to a user's profile.</td><td><code>POST /api/events/track</code></td></tr>
  <tr><td>Add user to Iterable list</td><td>Subscribe the current user to a specific static list ID.</td><td><code>POST /api/lists/subscribe</code></td></tr>
  <tr><td>Send campaign email to user</td><td>Trigger a specific email campaign to the user's primary email.</td><td><code>POST /api/email/target</code></td></tr>
  <tr><td>Send email to inputted email</td><td>Send a campaign to an email address provided via a form input.</td><td><code>POST /api/email/target</code></td></tr>
  <tr><td>Add user to list by email</td><td>Add a user to a list using a manually mapped email address.</td><td><code>POST /api/lists/subscribe</code></td></tr>
</table>
