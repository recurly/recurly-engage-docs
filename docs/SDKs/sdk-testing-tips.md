---
title: Testing tips
excerpt: >-
  Testing best practices for validating prompt delivery and user state in
  Recurly Engage.
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
  <div class="rp-overview">These recommendations help you test prompts accurately and reliably using the Test Users segment. They also cover reset and propagation considerations.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

# Definition

<div class="rp-definition">This guide outlines the steps and considerations for effectively testing prompt configurations, including allowlisting test users, running reset workflows, and allowing time for changes to propagate.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Reliable validation</strong>
    <span>Confirm that prompts render correctly under production-like conditions.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-bug" aria-hidden="true"></i></div>
    <strong>Efficient troubleshooting</strong>
    <span>Quickly reset and re-test user states to isolate issues.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-equals" aria-hidden="true"></i></div>
    <strong>Consistent results</strong>
    <span>Mitigate network and caching delays for standardized test outcomes.</span>
  </div>
</div>

# Key details

## Set up test users

You can add specific user IDs to the **Test Users** segment, which lets you test prompts that are visible only to users in this group. See <a href="/recurly-engage/docs/test-users" target="_blank">Test users</a> for instructions on configuring your Test Users.

## Test cases

When you run test cases, we recommend the following.

### Allow SDK initialization

Wait at least five seconds after launching the app before testing. Network latency can delay prompt retrieval.

### Reset and retest

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Reset the Test User</h4><p>Reset the Test User through the web interface.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Launch and close the app</h4><p>Launch the app, wait a few seconds, and then close it. This ensures the software development kit (SDK) fully resets the user state.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Relaunch and test</h4><p>Relaunch the app, wait a few seconds, and then perform your test.</p></div>
  </div>
</div>

### Allow for propagation delay

Changes such as pausing or starting prompts may take a few minutes to propagate. Keeping the test app open helps reduce the delay and stabilizes test conditions.

<br />

<br />
