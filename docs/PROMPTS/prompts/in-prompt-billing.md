---
title: In prompt billing
excerpt: >-
  Update your customers' payment methods without redirecting them away from your
  app. Recurly Engage's In-Prompt Billing embeds secure, PCI-compliant payment
  fields directly into your existing user experience.
deprecated: false
hidden: false
metadata:
  robots: index
---
<div class="rp-page">
<div class="rp-overview">In-Prompt Billing lets your customers update their payment information without ever leaving the page they're on—no separate billing portal, no redirect. Under the hood, it uses Recurly.js to tokenize sensitive payment data client-side, keeping your integration PCI DSS compliant with no extra overhead. It fits naturally into your existing prompt workflows and can be triggered by events like a failed payment or an upcoming renewal.</div>
<div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly Engage plans</div>
<div class="rp-toc">
<a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
<a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
<a class="rp-toc-pill" href="#step-by-step-guide"><span class="rp-toc-num">3</span>Step-by-step guide</a>
</div>
</div>

# Definition

<div class="rp-definition">In-Prompt Billing is a Recurly Engage feature that surfaces a payment update form inline, inside a prompt or modal within your application, instead of sending customers to a separate billing portal.</div>

# Key benefits

<div class="rp-benefits">
<div class="rp-benefit"><div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div><strong>Fewer drop-offs</strong><span>Keeping customers in context during a payment update removes friction and reduces the chance they abandon the process mid-flow.</span></div>
<div class="rp-benefit"><div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div><strong>Faster updates</strong><span>Billing fields are surfaced inline—customers can update their card in seconds, without a page redirect.</span></div>
<div class="rp-benefit"><div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div><strong>PCI DSS compliance, built in</strong><span>Payment data is captured and tokenized client-side via Recurly.js, so sensitive card information never touches your servers.</span></div>
<div class="rp-benefit"><div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div><strong>Fits your existing UI</strong><span>The payment form supports your prompt's Custom CSS configuration, so it inherits your existing styles with no extra work.</span></div>
<div class="rp-benefit"><div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div><strong>Prefilled for convenience</strong><span>Existing billing name and address details are pre-populated where possible, so customers only need to enter updated card information.</span></div>
</div>

# Step-by-step guide

<div class="rp-steps">
<div class="rp-step"><div class="rp-step-num">1</div><div><h4>Secure identity verification (JWT signing)</h4><p>In-Prompt Billing requires JWT (JSON Web Token) signing as part of the integration to protect your customers' billing information.</p></div></div>
</div>

Before any billing update is processed, your backend generates a signed JWT using a shared secret provided by Recurly Engage. This token passes through the Brig SDK and is validated server-side, so only authenticated users can initiate a billing info update. Boilerplate implementation code is provided to make this straightforward—contact your Customer Success Manager to get your JWT signing configured.

<div class="rp-steps">
<div class="rp-step"><div class="rp-step-num">2</div><div><h4>Configure a billing info update prompt</h4><p>Create a new prompt, open the Recurly Engage creative editor, and set the <strong>Form Type</strong> to <strong>Billing Info Update</strong>. This option is available for merchants who have already integrated with Recurly Subscriptions.</p></div></div>
</div>

<div class="rp-callout rp-callout-tip">
<div><strong><i class="fa-solid fa-lightbulb" aria-hidden="true"></i> Best practice</strong>Set "Show prompt again" to <span style={{fontWeight: "bold"}}>after 1 day</span> so customers who dismiss the prompt without completing their update are reminded the following day.</div>
</div>

<div class="rp-steps">
<div class="rp-step"><div class="rp-step-num">3</div><div><h4>Trigger the prompt at the right moment</h4><p>In-Prompt Billing prompts work best when surfaced in response to a billing event—for example, a failed payment or an expiring card.</p></div></div>
</div>

Tie prompt delivery to Recurly's dunning event webhooks so customers see the update request at the most relevant moment.

<div class="rp-steps">
<div class="rp-step"><div class="rp-step-num">4</div><div><h4>The customer updates their payment method</h4><p>When the prompt appears, the customer sees a secure payment form powered by Recurly.js, with their existing billing name and address prefilled where available. If they need to update those details, they can expand the form to do so.</p></div></div>
</div>

Once they submit, the new payment information is tokenized client-side and sent to Recurly's API to update their billing profile. The customer sees your configured confirmation message, and the prompt closes automatically.


<Image src="https://files.readme.io/f58bf86f250282509146243103e7556df8ef0e3d7f0a981ea2857794ffd16560-Screenshot_2026-04-02_at_8.48.16_AM.png" align="center" width="75%" border={true} />
