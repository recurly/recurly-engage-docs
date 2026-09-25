---
title: Paywall and hardwall prompts
excerpt: >-
  Set up an Engage dynamic paywall to limit free content and convert readers
  into subscribers.
deprecated: false
hidden: false
link:
  new_tab: false
metadata:
  robots: index
---
<div class="rp-page">
<div class="rp-overview">Dynamic Paywall and hardwall prompts help publishers and content providers control and monetize access to their digital content. Let readers view a set number of complimentary articles or paragraphs, then require sign-up or subscription before they can keep reading—no intrusive blocking required.</div>
<div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly Engage plans</div>
<div class="rp-toc">
<a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
<a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
<a class="rp-toc-pill" href="#step-by-step-guide"><span class="rp-toc-num">3</span>Step-by-step guide</a>
</div>
</div>

# Definition

<div class="rp-definition">A Dynamic Paywall or hardwall prompt limits how much content a reader can access for free. Once a user reaches that limit, the prompt visually obscures the remaining content and blocks further scrolling until they sign up or subscribe.</div>

# Key benefits

<div class="rp-benefits">
<div class="rp-benefit"><div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div><strong>Maximized content value</strong><span>Convert frequent readers into paying subscribers by blocking the remainder of premium article content.</span></div>
<div class="rp-benefit"><div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div><strong>Flexible access control</strong><span>Define the precise number of complimentary visits a user is permitted, with granular control over the pre-access experience.</span></div>
<div class="rp-benefit"><div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div><strong>Customizable blocking</strong><span>Block content by hiding, blurring, or custom CSS, with precise control over complimentary paragraphs or elements.</span></div>
<div class="rp-benefit"><div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div><strong>Drives user registration</strong><span>Create a clear incentive for users to sign up once they've used their introductory content quota.</span></div>
<div class="rp-benefit"><div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div><strong>Optimize with experiments</strong><span>A/B test any part of the experience over time to improve conversion.</span></div>
</div>

# Step-by-step guide

<div class="rp-steps">
<div class="rp-step"><div class="rp-step-num">1</div><div><h4>Add a new usage tracker</h4><p>Navigate to <strong>Settings > Usage Tracking</strong> and select <strong>+ Add new tracker</strong>.</p></div></div>
</div>

<ul class="rp-list">
<li>Fill out the required fields for Name, Label, and Description. Select the <strong>Page</strong> tracker type, then enter the relevant URL path.</li>
<li>Check the <strong>Use as paywall tracker</strong> checkbox.</li>
</ul>


<Image src="https://files.readme.io/561bbcb28f9202306e6c0e2a1b687e67798a766f508e25df00b1b35c85fd0681-paywall_tracker.png" align="center" width="75%" border={true} />


<div class="rp-steps">
<div class="rp-step"><div class="rp-step-num">2</div><div><h4>Create a zone</h4><p>Create a zone to define the article that contains the content you want to block—your Article Zone.</p></div></div>
</div>

If you're using an inline prompt, you can create a new zone to control where the prompt displays, or reuse the same zone. If you reuse the Article Zone, the prompt is appended to the end of it.

<ul class="rp-list">
<li>Navigate to <strong>Settings > Zones</strong> and select <strong>New Zone</strong>.</li>
<li>Enter the information for your zone—the parent element containing the content you want to block or hide.</li>
</ul>

<div class="rp-steps">
<div class="rp-step"><div class="rp-step-num">3</div><div><h4>Create a new prompt</h4><p>Navigate to the main Prompts screen in your dashboard, select <strong>+ New Prompt</strong>, and choose your desired prompt type.</p></div></div>
</div>

<ul class="rp-list">
<li>In the Edit Prompt Design view, scroll to the <strong>Paywall</strong> accordion menu.</li>
<li>Check <strong>Enable paywall</strong>, then select the zone that defines the article—your Article Zone.</li>
</ul>

<div class="rp-callout rp-callout-note">
<div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>Configure the following paywall settings before you save.</div>
</div>

<ul class="rp-list">
<li><strong>Paywall tracker</strong>: the usage tracker you created in Step 1.</li>
<li><strong>Free visits</strong>: how many visits a user gets before the paywall activates.</li>
<li><strong>Zone to block</strong>: the area that will be obscured.</li>
</ul>

Choose a block method—how the content will be removed or obscured from the page:

<ul class="rp-list">
<li><strong>Blur</strong>: the content stays on the page, but CSS styling prevents it from being readable.</li>
<li><strong>Hide</strong>: the content is hidden, but not removed from the page.</li>
<li><strong>Strip text</strong>: the text is removed from the DOM, but the DOM elements remain, so you don't break any JavaScript.</li>
<li><strong>Custom CSS</strong>: enter your own CSS to block the content.</li>
</ul>

<ul class="rp-list">
<li><strong>Apply to elements</strong>: choose which elements in the Article Zone the block method applies to. You can specify a custom CSS selector for precise control.</li>
<li><strong>Elements to allow</strong>: set how many paragraphs or child elements in the Article Zone stay unblocked, if you're not using a CSS selector above.</li>
<li><strong>Save and activate</strong>: once your limits are set and your copy is finalized, save the prompt to apply the paywall logic to your site.</li>
</ul>


<Image src="https://files.readme.io/302f616bd65719d846476778ae5d4ab3ee543349ef49b89b1755c179c7bf2b8a-paywall_config.png" align="center" width="75%" border={true} />
