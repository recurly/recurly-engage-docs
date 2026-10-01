---
title: Tours
excerpt: >-
  Build a Tour in Recurly Engage — a multi-step, element-anchored tooltip
  walkthrough that guides subscribers through your site.
deprecated: false
hidden: false
metadata:
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">Tours guide subscribers through your site with floating tooltips, configured natively in Pulse. This page explains how a Tour works and how to build one.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have the <strong>Company</strong>, <strong>App Administrator</strong>, or <strong>App Member</strong> permission in Recurly Engage.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>Tours run in standard web browsers only. They don't support connected TV (CTV), mobile, or other device platforms.</li>
</ul>

# Definition

<div class="rp-definition">A Tour is a guide type that walks subscribers through your site with a sequence of floating tooltips, each anchored to a specific element on the page. It's built for onboarding, feature discovery, and guided navigation, helping new subscribers find value quickly without a third-party onboarding tool.</div>

Subscribers move through the steps in a fixed, sequential order, and they can go backward to revisit a step they've already seen. Because steps can span multiple pages, you can guide a subscriber from, say, a homepage to an account page within a single flow. Everything is configured natively in Pulse.

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-route" aria-hidden="true"></i></div>
    <strong>Native onboarding</strong>
    <span>Guide subscribers through your product without adding a separate onboarding tool or contract.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-thumbtack" aria-hidden="true"></i></div>
    <strong>Element-anchored guidance</strong>
    <span>Attach each tooltip to the exact element it describes, so guidance lands in context.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-chart-column" aria-hidden="true"></i></div>
    <strong>One place for data</strong>
    <span>Tour impressions, step completions, and exits flow into your existing Engage analytics alongside your other prompts.</span>
  </div>
</div>

# Key details

## How a Tour works

Each Tour step is a web notification prompt with two capabilities specific to Tours:

* **Pin to element**: Anchor the prompt to a page element with a Cascading Style Sheets (CSS) selector, then place it above, below, to the left, or to the right of that element. Pinning overrides the size and position in the prompt's standard settings.
* **Scroll into view**: When the anchored element is off-screen, scroll it to the top, center, or bottom of the viewport. You can also turn off automatic scrolling.

**Button 1** advances to the next step, and **Button 2** acts as the **Back** button. Dismissing a step with the X exits the entire Tour. Subscribers can't skip ahead, but they can move backward and forward among the steps they've reached.

Tour steps inherit the guide's **Limits**, **Segments**, and **Schedule** settings. Tour impressions, step completions, and exits appear in Engage analytics.

## Build a Tour

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Start a new guide</h4><p>Go to <span style={{fontWeight: "bold"}}>Guides &gt; New Guide</span>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Name the guide and select Tour</h4><p>Enter a <span style={{fontWeight: "bold"}}>Name</span> and, optionally, a <span style={{fontWeight: "bold"}}>Description</span>. Select the <span style={{fontWeight: "bold"}}>Tour</span> guide type.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Configure segments and triggers</h4><p>Configure your <span style={{fontWeight: "bold"}}>Segments</span> and the guide's trigger conditions (audience segment, page URL, event, and schedule) using the standard Engage targeting options.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Add Tour steps</h4><p>Add Tour steps in the order subscribers should see them. Each step is a web notification prompt with its own content, targeting, and placement.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Pin each step to an element</h4><p>For each step, navigate to the prompt design editor and configure the <span style={{fontWeight: "bold"}}>Pin to</span> section.</p></div>
  </div>
</div>

<ol>
  <li>Enter the CSS selector of the element you want to anchor the tooltip to.</li>
  <li>Choose the placement relative to that element: top, bottom, left, or right.</li>
</ol>


<Image src="https://files.readme.io/2db5e0e07a32e8f264ba7228c91838e40f360beb1b2cb1c806e11f54791622a2-Screenshot_2026-07-20_at_1.23.05_PM.png" align="center" width="40%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">6</div>
    <div><h4>Set the scroll behavior (optional)</h4><p>Set the <span style={{fontWeight: "bold"}}>scroll into view</span> behavior so the page scrolls the anchored element into view (top, center, or bottom of the viewport) when the step triggers.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">7</div>
    <div><h4>Configure user interactions</h4><p>Under <span style={{fontWeight: "bold"}}>User interactions</span>, set <span style={{fontWeight: "bold"}}>Show prompt again after Button 1 click</span> and <span style={{fontWeight: "bold"}}>Show prompt again after Button 2 click</span> to <span style={{fontWeight: "bold"}}>Amount of time: 0 minutes</span>. Set the <span style={{fontWeight: "bold"}}>Fadeout timer</span> to <span style={{fontWeight: "bold"}}>0 seconds</span>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">8</div>
    <div><h4>Configure transitions</h4><p>Return to the guide page to configure the optional <span style={{fontWeight: "bold"}}>transition</span> settings.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">9</div>
    <div><h4>Set transition URLs</h4><p>Set the <span style={{fontWeight: "bold"}}>transition URL</span> for any step that moves the subscriber to a different page. This tells Engage where to navigate next as the subscriber moves forward or backward through the Tour.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">10</div>
    <div><h4>Set limits and a schedule (optional)</h4><p>Set <span style={{fontWeight: "bold"}}>Limits</span> and a <span style={{fontWeight: "bold"}}>Schedule</span> for the entire Tour.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">11</div>
    <div><h4>Preview and start the Tour</h4><p>Preview the Tour against your site to confirm positioning and copy, then select <span style={{fontWeight: "bold"}}>Start</span> to make it live.</p></div>
  </div>
</div>

<br />

<br />
