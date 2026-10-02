---
title: Test users
excerpt: >-
  Configuration guide for the Test Users feature, which allows whitelisted users
  to preview active prompts in a production environment.
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
  <div class="rp-overview">Test users let you preview prompts in production before your real audience sees them. Recurly Engage creates a Test Users segment for every app, and you decide which user IDs belong to it.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly Engage plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#set-up-test-users"><span class="rp-toc-num">3</span>Set up test users</a>
    <a class="rp-toc-pill" href="#preview-with-live-preview"><span class="rp-toc-num">4</span>Preview with Live Preview</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have <span style={{fontWeight: "bold"}}>Company</span> or <span style={{fontWeight: "bold"}}>App Administrator</span> permissions in Engage.</li>
</ul>

# Definition

<div class="rp-definition">The <span style={{fontWeight: "bold"}}>Test Users</span> segment is an automatically provisioned group that lets you restrict prompt visibility to a curated list of user IDs for quality assurance (QA) and preview purposes.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Safe testing environment</strong>
    <span>Preview prompts in production without impacting all users.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Rapid iteration</strong>
    <span>Validate creative, triggers, and actions with a controlled audience.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Granular control</strong>
    <span>Whitelist or remove specific test accounts on demand.</span>
  </div>
</div>

# Set up test users

Engage automatically creates a **Test Users** segment for each app when you create it. To choose which users belong to this segment:

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open Test Users</h4><p>Go to <span style={{fontWeight: "bold"}}>Settings &gt; Users &gt; Test Users</span>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/9c4e603-Screenshot_2024-05-22_at_15.20.44.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Enter a User ID</h4><p>Enter the <span style={{fontWeight: "bold"}}>User ID</span> of a test account. User IDs can be long alphanumeric or globally unique identifier (GUID) strings, so make sure you copy the exact value from your source system.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Add the user</h4><p>Click <span style={{fontWeight: "bold"}}>Add</span>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/85a7cff-Screenshot_2024-05-22_at_15.22.28.png" align="center" width="75%" border={true} />


Once added, this user sees all active prompts targeted to **Test Users** when they log in.

# Preview with Live Preview

You can also simulate a test user using the Live Preview feature:

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Start Live Preview</h4><p>Click the <span style={{fontWeight: "bold"}}>Live Preview</span> button in the console. This opens your site and impersonates the selected test user.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/2714f17-Screenshot_2024-05-22_at_15.23.56.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Open the Preview tool</h4><p>Open the <span style={{fontWeight: "bold"}}>Recurly Engage Preview</span> tool on your site.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/0543e15-Screenshot_2024-05-22_at_15.25.01.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Confirm the User ID</h4><p>Check that the <span style={{fontWeight: "bold"}}>User ID</span> field auto-populates with your test user’s ID.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Go to the prompt's page</h4><p>If the prompt status is <span style={{fontWeight: "bold"}}>Inactive</span>, navigate to the page where the prompt should appear.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/5deb9c6-Screenshot_2024-05-22_at_15.35.23.png" align="center" width="75%" border={true} />



<Image src="https://files.readme.io/a7583fa-Screenshot_2024-05-22_at_15.39.40.png" align="center" width="75%" border={true} />



<Image src="https://files.readme.io/0eb2ab1-Screenshot_2024-05-22_at_15.40.24.png" align="center" width="75%" border={true} />
