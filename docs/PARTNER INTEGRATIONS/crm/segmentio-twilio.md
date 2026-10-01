---
title: Segment
excerpt: >-
  Configuration guide for syncing Segment traits into Recurly Engage via Segment
  Unify or Amazon Lambda
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
  <div class="rp-overview">Sync your Segment user traits to Recurly Engage, so you can target prompts based on the profile data you already collect. You can connect through Segment Unify or through an Amazon Lambda destination.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly Engage subscription plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have access to your Segment workspace, with permission to add destinations.</li>
  <li>You must have access to your Segment Unify space, with permission to retrieve the Unify Access Token and Space ID.</li>
</ul>

# Definition

<div class="rp-definition">By setting up an integration with Segment Unify, or by routing Segment events to an Amazon Web Services (AWS) Lambda destination, Recurly Engage syncs each user's traits as they arrive on your site. You can then target prompts based on all the profile data available in your Segment account.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-code" aria-hidden="true"></i></div>
    <strong>No additional instrumentation</strong>
    <span>Use your existing Segment calls. No new software development kits (SDKs) or code changes are required.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-bolt" aria-hidden="true"></i></div>
    <strong>Real-time targeting</strong>
    <span>Segment events can be available in Recurly Engage within minutes for immediate prompt personalization.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-sliders" aria-hidden="true"></i></div>
    <strong>Flexible trait mapping</strong>
    <span>Sync any profile trait without rebuilding your analytics stack.</span>
  </div>
</div>

# Key details

## Set up Segment Unify sync

If you use Segment Unify (formerly known as Profiles), Recurly Engage can automatically sync traits when a user starts a new session on your site or app.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open Unify</h4><p>In your Segment console, select the <span style={{fontWeight: "bold"}}>Unify</span> tab in the left nav.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Select the space</h4><p>Select the space that should be synced (for example, production or staging).</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Open Unify Settings</h4><p>Select <span style={{fontWeight: "bold"}}>Unify Settings</span> in the subnav.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Open API Access</h4><p>Select <span style={{fontWeight: "bold"}}>API Access</span>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Note the Space ID</h4><p>Note the <span style={{fontWeight: "bold"}}>Space ID</span>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">6</div>
    <div><h4>Generate a token</h4><p>If an access token hasn't been created yet, select <span style={{fontWeight: "bold"}}>Generate Token</span> and assign a name (for example, Recurly Engage Token). Save the token, because it's displayed only once.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">7</div>
    <div><h4>Add the values to Pulse</h4><p>Copy the <span style={{fontWeight: "bold"}}>Unify Access Token</span> and <span style={{fontWeight: "bold"}}>Unify Space ID</span> into the <span style={{fontWeight: "bold"}}>Settings &gt; Integrations &gt; Segment</span> modal in Pulse. Then contact your Customer Success Manager or <a href="mailto:support@recurly.com">support@recurly.com</a> to activate this functionality.</p></div>
  </div>
</div>

Newly synced traits appear on the **Settings > User Traits** screen 5–10 minutes after syncing starts.

## Set up an Amazon Lambda destination

As an alternative to Segment Unify, you can set up an Amazon Lambda destination for events processed by Segment. "Identify" events trigger a real-time sync of the associated user traits to Recurly Engage.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Log in to Segment</h4><p>Log in to Segment.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Go to your workspace</h4><p>Go to the correct app workspace.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/f5c742b-Segment_configure.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Add a destination</h4><p>Add a new destination.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/125929e-Segment_configure_2.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Search for Lambda</h4><p>Type "lambda" in the search box and select the tile that appears.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/cfe1f2f-Segment_configure_3.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Configure Amazon Lambda</h4><p>Select <span style={{fontWeight: "bold"}}>Configure Amazon Lambda</span>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/8baf8c6-Segment_configure_4.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">6</div>
    <div><h4>Confirm the source</h4><p>Select your app and select <span style={{fontWeight: "bold"}}>Confirm Source</span>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/ffd3c94-Segment_configure_5.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">7</div>
    <div><h4>Find the credentials</h4><p>Go to <span style={{fontWeight: "bold"}}>Usage Tracking</span> and locate the credentials to enter.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/58f7707-Segment_Configure_6.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">8</div>
    <div><h4>Copy the values</h4><p>Copy the <code>Region</code>, <code>Role Address</code>, and <code>Lambda ARN</code> values.</p></div>
  </div>
</div>

As the final step, provide the read-only `External ID` to your Customer Success Manager. `Client Context` and `Log Type` don't need any special configuration.


<Image src="https://files.readme.io/a036acc-Segment_configure_7.png" align="center" width="75%" border={true} />



<Image src="https://files.readme.io/a6f4a75-Segment_Configure_8.png" align="center" width="75%" border={true} />


<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>New traits may take up to 10 minutes before they appear in Recurly Engage.</div>
</div>
