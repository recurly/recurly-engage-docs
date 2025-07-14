---
title: Abandon cart
excerpt: >-
  Configuration guide for the Abandon Cart use case, which targets visitors who
  leave items in their cart and encourages them to complete checkout.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

More than 95% of visitors to your website won’t convert on their first visit. The **Abandon Cart** use case recovers lost revenue by prompting returning visitors to resume their checkout process—recovering 40% or more of abandoned carts.

### Prerequisites & limitations

* You must have **Company**, **App Administrator**, or **App Member** permissions in Recurly Engage.

# Definition

The **Abandon Cart** use case detects returning visitors who left items in their cart and displays a prompt guiding them back to complete their purchase.

# Key benefits

* **Revenue recovery**: Recover a significant portion of abandoned carts by re-engaging visitors.
* **Contextual prompts**: Trigger messages only when users exhibit exit intent during checkout.
* **Personalized messaging**: Use dynamic variables (e.g., first name) to enhance relevance.

# Key details

Using this approach, your business can recover 40% or more of users with abandoned carts when they return to the site.

<Image align="center" className="border" border={true} src="https://files.readme.io/50f04cb-Screenshot_2024-04-30_at_4.09.36_PM.png" />

> 👍 For best results, consider providing an incentive to complete the checkout process.

## Guide

1. **Sync** visitor attributes related to cart abandonment and create an **Abandoned Cart** segment; otherwise use the built-in **Anonymous Users** segment.
2. **Create** a **Popup Prompt** (Settings > Prompts) via [Create a Popup Prompt](create-a-pop-up) and customize the headline, message, and any dynamic variables.
3. Under **Add Action**, **configure** a redirect to your cart URL.
4. **Target** the prompt to the **Test Users** segment.
5. **Set** the trigger to fire on your checkout flow (e.g., URL pattern `/checkout/*`) and **enable** the **Exit Intent** advanced trigger.
6. **Launch** the prompt.
7. **Add** your User ID to **Test Users** (Settings > Users > Test Users).
8. **Verify** the prompt appears when exit intent is detected during the checkout flow.
9. **Update** the prompt’s targeting segment to **Abandoned Cart** for production deployment.