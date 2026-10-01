---
title: Actions
excerpt: >-
  Overview of prompt actions—triggered events tied to user interactions,
  built-in connectors, and custom integrations in Recurly Engage.
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
  <div class="rp-overview">Actions define what happens when a user interacts with a prompt. Attach built-in, connector, API, or website actions to personalize the experience and connect Recurly Engage to your other systems.</div>
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

### Limitations

<ul class="rp-list">
  <li>For connector actions, you must supply third-party credentials.</li>
  <li>Website actions require custom JavaScript knowledge.</li>
</ul>

# Definition

<div class="rp-definition">An action is a task that runs when a user interacts with a prompt: Accept, Decline, Secondary Accept, Dismiss, or Timeout. Actions enable personalized flows and integrations.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-link" aria-hidden="true"></i></div>
    <strong>Custom workflows</strong>
    <span>Chain multiple actions, such as redirects, emails, and API calls, on a single interaction.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-plug" aria-hidden="true"></i></div>
    <strong>Prebuilt integrations</strong>
    <span>Connect to billing, marketing, or support systems with prebuilt connectors.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-bolt" aria-hidden="true"></i></div>
    <strong>Immediate responses</strong>
    <span>Trigger website JavaScript actions for in-app behavior without page reloads.</span>
  </div>
</div>

# Key details

## User interactions

You can tie actions to any of these five prompt events:

<ul class="rp-list">
  <li><strong>Accept</strong>: User clicks the primary button.</li>
  <li><strong>Secondary Accept</strong>: User clicks the secondary button (if configured).</li>
  <li><strong>Decline</strong>: User clicks a Decline option.</li>
  <li><strong>Dismiss</strong>: User closes the prompt with the X icon.</li>
  <li><strong>Timeout</strong>: Prompt closes automatically after a timer.</li>
</ul>

Use the two buttons (Accept and Decline) for complementary actions, such as "Sign me up" on Accept and "Add to watchlist" on Decline.


<Image src="https://files.readme.io/dbba980-image.png" align="center" width="75%" border={true} />



<Image src="https://files.readme.io/ae7b5ec-image.png" align="center" width="75%" border={true} />


## Configure actions on a prompt

You can attach one or more actions to each interaction. For example, you might apply a discount through an API call and then send a confirmation email on Accept.


<Image src="https://files.readme.io/48dd9f9-image.png" align="center" width="75%" border={true} />


### Built-in actions

These actions are available by default on every prompt:

<ul class="rp-list">
  <li><strong>Send an email</strong>: Dispatch an email to a specified address on Accept.</li>
  <li><strong>Send an SMS</strong>: Send an SMS to a specified number on Accept.</li>
  <li><strong>Redirect the user</strong>: Navigate the user to a URL when they accept.</li>
</ul>

### Connector actions

Integrate with external systems, such as billing, CRM, and support, using prebuilt connectors. Supply your credentials in <span style={{fontWeight: "bold"}}>Settings &gt; Connectors</span> before you use one.


<Image src="https://files.readme.io/87d7647-image.png" align="center" width="75%" border={true} />


#### Add a connector action

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open your prompt</h4><p>Open your prompt under <span style={{fontWeight: "bold"}}>Prompts</span>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/aace646-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Add an action</h4><p>Select <span style={{fontWeight: "bold"}}>Add action</span> next to the interaction you want (for example, Accept).</p></div>
  </div>
</div>


<Image src="https://files.readme.io/d186553-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Configure the connector action</h4><p>In the action modal, select <span style={{fontWeight: "bold"}}>Connector Actions</span>, choose a connector (for example, Zuora) and an action (for example, Subscribe a user to a plan), set <span style={{fontWeight: "bold"}}>Error Behavior</span> to Stop or Continue, and then select <span style={{fontWeight: "bold"}}>Add Action</span>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/4b6e880-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Reorder your actions</h4><p>Drag actions to reorder them. Add multiple actions per interaction as needed.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/09969e8-image.png" align="center" width="75%" border={true} />


<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Error behavior</strong><ul><li><span style={{fontWeight: "bold"}}>Stop</span>: Halts downstream actions if this action fails.</li><li><span style={{fontWeight: "bold"}}>Continue</span>: Proceeds to the next actions even if this one errors.</li></ul></div>
</div>

## Custom actions

Build your own actions for advanced scenarios:

<div class="rp-nav-grid">

<Cards>
  <Card title="Connector actions" href="/recurly-engage/docs/connector-actions" target="_blank">
    Integrate additional business systems.
  </Card>
  <Card title="API actions" href="/recurly-engage/docs/api-actions" target="_blank">
    Call your custom endpoints.
  </Card>
  <Card title="Website actions" href="/recurly-engage/docs/website-actions" target="_blank">
    Run custom JavaScript in the user's browser.
  </Card>
</Cards>
</div>

For complex setups, like 1-click save offers, our technical team can help. Reach out on Slack or contact <a href="mailto:support@recurly.com">[support@recurly.com](mailto:support@recurly.com)</a> for hands-on support.

<br />
