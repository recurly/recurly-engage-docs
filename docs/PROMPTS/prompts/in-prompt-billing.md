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
# Overview

In-Prompt Billing is a feature of Recurly Engage that lets your customers update their payment information without ever leaving the page they're on. Instead of navigating to a separate billing portal, the payment update experience is surfaced inline — inside a prompt or modal within your application.

Under the hood, In-Prompt Billing uses Recurly.js to tokenize sensitive payment data client-side, keeping your integration PCI DSS compliant without additional overhead on your end. It's designed to fit naturally into your existing prompt workflows and can be triggered by events like a failed payment or an upcoming renewal.

# Key Benefits

* **Fewer drop-offs.** Keeping customers in-context during a payment update removes friction and reduces the chance they abandon the process mid-flow.
* **Faster updates.** Billing fields are surfaced inline — customers can update their card in seconds, without a page redirect.
* **PCI DSS compliance, built in.** Payment data is captured and tokenized client-side via Recurly.js, so sensitive card information never touches your servers.
* **Fits your existing UI.** The payment form supports your prompt's Custom CSS configuration, so it inherits your existing styles with no extra work.
* **Prefilled for convenience.** Where possible, existing billing name and address details are pre-populated so customers only need to enter updated card information.

# How It Works

## 1. Configure a Billing Info Update prompt

Create a new prompt and open the Recurly Engage creative editor. Set the **Form Type** to **Billing Info Update**. This option is available for merchants who have already integrated with Recurly Subscriptions.

> **Best practice:** Set "Show prompt again" to **after 1 day** to ensure customers who dismiss the prompt without completing their update are reminded the following day.

## 2. Trigger the prompt at the right moment

In-Prompt Billing prompts work best when surfaced in response to a billing event — for example, a failed payment or an expiring card. You can tie prompt delivery to Recurly's dunning event webhooks to ensure customers see the update request at the most relevant moment.

## 3. Secure identity verification (JWT signing)

To protect your customers' billing information, In-Prompt Billing requires **JWT (JSON Web Token) signing** as part of the integration. Before any billing update is processed, your backend generates a signed JWT using a shared secret provided by Recurly Engage. This token is passed through the Brick SDK and validated server-side, ensuring that only authenticated users can initiate a billing info update.

Boilerplate implementation code is provided to make this straightforward to set up. See [JWT Signing Setup](#) for step-by-step instructions.

## 4. The customer updates their payment method

When the prompt appears, the customer is shown a secure payment form powered by Recurly.js. Their existing billing name and address are prefilled where available. If they need to update those details, they can expand the form to do so.

Once they submit, the new payment information is tokenized client-side and sent to Recurly's API to update their billing profile. The customer sees your configured confirmation message and the prompt closes automatically.

<br />

<Image align="center" src="https://files.readme.io/f58bf86f250282509146243103e7556df8ef0e3d7f0a981ea2857794ffd16560-Screenshot_2026-04-02_at_8.48.16_AM.png" />
