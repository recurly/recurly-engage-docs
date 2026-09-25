---
title: Invisible prompts
excerpt: >-
  Configure and trigger background behaviors in your application without any
  user-facing UI using Invisible Prompts.
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
<div class="rp-overview">Invisible Prompts run automations behind the scenes—no banner, no pop-up, nothing your users ever see. Define a trigger, and Recurly Engage fires off API calls, toggles UI elements, or applies discounts the moment it matches. It's the same prompt-building flow you already know, just without the visual layer.</div>
<div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly Engage plans</div>
<div class="rp-toc">
<a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
<a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
<a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
</div>
</div>

### Prerequisites

<ul class="rp-list">
<li>Company, App Administrator, or App Member permissions in Recurly Engage.</li>
</ul>

# Definition

<div class="rp-definition">An Invisible Prompt is a hidden rule that runs a server-side or client-side action automatically when its trigger matches—it never presents anything to the user.</div>

# Key benefits

<div class="rp-benefits">
<div class="rp-benefit"><div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div><strong>Automate background tasks</strong><span>Launch API calls, hide or show UI elements, or apply discounts without user clicks.</span></div>
<div class="rp-benefit"><div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div><strong>Seamless user experience</strong><span>Modify behavior or content without interrupting the user.</span></div>
<div class="rp-benefit"><div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div><strong>Flexible triggers</strong><span>Fire on page load, custom events, or segment entry to suit any workflow.</span></div>
</div>

# Key details

This prompt type shares its configuration flow with a <a href="overlays#how-to-video" target="_blank">pop-up</a>, but with no visual component—every action runs immediately when the trigger fires.


<Image src="https://files.readme.io/c386e48-image.png" align="center" width="75%" border={true} />


#### Example use cases

<ul class="rp-list">
<li>Automatically add a show to a user's watchlist on page load.</li>
<li>Hide competing ads for premium subscribers.</li>
<li>Trigger a fulfillment API or apply a discount coupon.</li>
</ul>

## Configuring metadata

Use metadata tags to pass custom key-value pairs into your Invisible Prompt for advanced behaviors.

<div class="rp-steps">
<div class="rp-step"><div class="rp-step-num">1</div><div><h4>Open the Metadata modal</h4><p>Select the <strong>Edit</strong> (pencil) icon on your Invisible Prompt.</p></div></div>
</div>


<Image src="https://files.readme.io/e45aa27-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
<div class="rp-step"><div class="rp-step-num">2</div><div><h4>Add key-value pairs</h4><p>Add one or more key-value pairs to tailor your action logic.</p></div></div>
</div>


<Image src="https://files.readme.io/7db1c7e-image.png" align="center" width="75%" border={true} />


### Retrieving metadata in code

```javascript
Redfast.getMetas()
// returns { 'meta1': 'val1', 'meta2': 'val2' }
```

## Test the prompt

Validate your trigger and actions before full deployment by assigning the <strong>Test Users</strong> segment. See the <a href="test-users" target="_blank">test user guide</a> for details.
