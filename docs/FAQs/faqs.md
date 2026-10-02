---
title: Debugging a prompt that is not showing
excerpt: >-
  Configuration guide for debugging prompts that fail to display in Recurly
  Engage.
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
  <div class="rp-overview">When a prompt doesn't show, work through a short checklist to find out why. It covers your tag and segment setup, triggers, experiments, and limits.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
</div>

# How do I debug a prompt that isn’t showing?

Work through these checks in order:

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Verify your basic setup</h4><p>Make sure the Recurly Engage tag is loaded on the page (check for ping calls in your network inspector), the prompt status is <span style={{fontWeight: "bold"}}>Active</span>, and the correct segment is applied and enabled.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Confirm you’re targeting the right user</h4><p>Ensure the User ID you’re testing with belongs to the prompt’s segment (impersonate in Preview or use User Lookup), and check the ping payload’s <code>segments</code> array.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Double-check your trigger criteria</h4><p>Check the criteria for your trigger type:</p></div>
  </div>
</div>

* **Page-based:** Make sure you’re on the exact URL defined.
* **Click-based:** Verify the element’s Cascading Style Sheets (CSS) selector matches your trigger settings.
* **Survey or multi-step guides:** Ensure any prerequisite prompt is also **Active** and has fired.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Check the ping response</h4><p>Once those are correct, look in the ping response under <code>paths</code> to see if the prompt was delivered.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/73b7658-image.png" align="center" width="75%" border={true} />


## If the prompt is delivered but doesn’t render

If the prompt appears under `paths` but doesn’t render, check for an active experiment control group. Open the corresponding `path` object in the payload and inspect its `action_group_name`. If it’s set to **Control**, that User ID is held out by design.


<Image src="https://files.readme.io/67a6aa2-image.png" align="center" width="75%" border={true} />


## If no path is delivered

Review any limits or interaction settings. Make sure impression limits, frequency caps, or “Show prompt again after button click” options aren’t preventing display.

## Reset suppression and re-test

To reset any suppression, clear the user’s prompt state and re-test.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Clear the user’s prompt state</h4><p>Reset goals in Live or in the console.</p></div>
  </div>
</div>

**In Live:** Go to **Settings > Users > Test Users > Reset Goals**.

**In the console:**

```js
RecurlyEngage.resetGoals(true);
```

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Refresh the page</h4><p>Refresh the page a few times to restore eligibility.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/89184dd-image.png" align="center" width="75%" border={true} />
