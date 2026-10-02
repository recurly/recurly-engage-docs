---
title: Testing a prompt before launching
excerpt: >-
  Guidance on how to safely test prompts before launching to production
  audiences in Recurly Engage.
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
  <div class="rp-overview">Test a prompt in production without showing it to live users. Validate it with a small test audience, then switch it to your real audience when you're ready.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
</div>

# How can I test a prompt without affecting live users and ensure it can be re-displayed for repeated testing?

Activate the prompt for a test audience first. Only the user IDs you designate can see and validate it in your production environment.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Target a test audience</h4><p>Activate the prompt on the internal <a href="test-users" target="_blank">Test Users</a> segment. If you need more granular control, create a custom segment that targets individual test user IDs.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/ba8c882-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Validate and adjust</h4><p>Confirm the prompt's behavior and make any necessary adjustments.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Go live</h4><p>Update the prompt's segment to your intended audience, and the prompt goes live accordingly.</p></div>
  </div>
</div>

## If the test prompt only displays once

Check the following:

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Check</td><td>What to do</td></tr>
  <tr><td>Interaction settings</td><td>Make sure “Show prompt again after button 1 click or button 2 click” and/or “Show prompt again after button 3 click” under <span style={{fontWeight: "bold"}}>User Interaction</span> is set to “On the next visit” or “After X minutes/hours/days.”</td></tr>
  <tr><td>Prompt limits</td><td>Verify that impression limits, frequency caps, or delivery limits aren't preventing repeated displays.</td></tr>
  <tr><td>Reset goals</td><td>To simulate a fresh user state, reset goals via <span style={{fontWeight: "bold"}}>Settings &gt; Users &gt; Test Users &gt; Reset Goals</span> in the Live tool, or run <code>RecurlyEngage.resetGoals();</code> in your browser console.</td></tr>
</table>
