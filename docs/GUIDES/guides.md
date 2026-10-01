---
title: 'Overview: Guides'
excerpt: >-
  Overview and how-to for multi-step Guides in Recurly Engage, including
  wizards, surveys, journeys, and triggered flows.
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
  <div class="rp-overview">Guides turn individual prompts into guided experiences, such as onboarding flows, surveys, and feature tours. Choose the guide type that fits your goal and the platforms your users are on.</div>
  <div style={{position: "relative", paddingTop: "56.25%", marginBottom: "28px", borderRadius: "10px", overflow: "hidden"}}>
    <iframe src="https://www.loom.com/embed/936c535cfaf74ba2afcd89474b8a9d9b?sid=faff98b4-6cde-49fb-b205-f1df5dac4075"
      title="Guides overview"
      allow="autoplay; fullscreen"
      allowtransparency="true"
      frameBorder="0"
      scrolling="no"
      allowFullScreen
      style={{position: "absolute", top: 0, left: 0, width: "100%", height: "100%", border: "none"}}></iframe>
  </div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> This feature may not be included in all plans — contact <a href="https://recurly.com/demo/contact-sales/" target="_blank">Recurly Sales</a> to discuss upgrade options</div>
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
  <li>Guide type is fixed on creation and can't be changed later.</li>
</ul>

# Definition

<div class="rp-definition">A guide binds multiple prompts into a controlled flow, enabling sequential, branched, or conditional delivery based on user behavior and scheduling.</div>


<Image src="https://files.readme.io/bd78e59-image.png" align="center" width="75%" border={true} />


# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-list-ol" aria-hidden="true"></i></div>
    <strong>Structured interactions</strong>
    <span>Deliver step-by-step experiences to users.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-code-branch" aria-hidden="true"></i></div>
    <strong>Dynamic branching</strong>
    <span>Use survey logic or conditions to tailor the flow.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-laptop-mobile" aria-hidden="true"></i></div>
    <strong>Cross-device continuity</strong>
    <span>Maintain guide state as users switch devices.</span>
  </div>
</div>

# Key details

## Create a guide

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Start a new guide</h4><p>Go to <span style={{fontWeight: "bold"}}>Guides &gt; New Guide</span>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Select a guide type</h4><p>Select a guide type. See the sections below for details on each type.</p></div>
  </div>
</div>

## Guide types

### Wizard

Supported on Web and HTML5-based smart TVs.

Wizard guides present prompts immediately, in the defined order, within a single session. Only the first prompt requires a trigger. Subsequent prompts fire automatically when the user interacts with the previous prompt.

Items within a guide inherit the guide's configurations: <a href="/recurly-engage/docs/limits" target="_blank">Limits</a>, <a href="/recurly-engage/docs/segments" target="_blank">Segments</a>, and <a href="/recurly-engage/docs/schedule-1" target="_blank">Schedule</a>.


<Image src="https://files.readme.io/8a86d2f-image.png" align="center" width="75%" border={true} />


### Survey

Supported on Web and HTML5-based smart TVs.

Survey guides collect user input through branching prompts. Subsequent prompts appear based on the user's selection in earlier steps.


<Image src="https://files.readme.io/e09a8bd-image.png" align="center" width="75%" border={true} />


### Journey

Supported on all devices.

Journey guides onboard new users or deliver feature tours over time. You can configure them to show only unseen items or to enforce a strict order, triggering based on visits, interactions, or time delays.


<Image src="https://files.readme.io/9a5b99e-image.png" align="center" width="75%" border={true} />


Items within a guide can be connected based on:

* **Interactions**: Show an item only if another guide item was seen, accepted, declined, or dismissed.
* **Next Visit**: Trigger the next item on the user's next session.
* **Days**: Delay the next item by a set number of days across sessions.
* **Minutes**: Delay the next item by minutes within the same session.

### Triggered

Supported on all devices.

Triggered guides reinforce messages by delivering one of several prompts based on user eligibility and predefined conditions. You can prevent users from receiving multiple similar items by setting exclusion rules across guide items.


<Image src="https://files.readme.io/831f597-image.png" align="center" width="75%" border={true} />


### Tours

Supported on Web only.

Tour guides walk subscribers through your site with a sequence of floating tooltips, each anchored to a specific element on the page. Use them for onboarding, feature discovery, and guided navigation — configured natively in Pulse, with steps that can span multiple pages. <a href="/recurly-engage/docs/tours" target="_blank">Learn how to build a Tour</a>.


<Image src="https://files.readme.io/e1674c35bce8685ff830b9a209f8c9821aa3fa46cb207188d647b36445266bda-Screenshot_2026-07-20_at_1.23.50_PM.png" align="center" width="75%" border={true} />


<br />

<br />
