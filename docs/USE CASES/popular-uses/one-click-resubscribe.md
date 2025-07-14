---
title: 1-click resubscribe
excerpt: >-
  Configuration guide for the 1-Click Resubscribe use case, which enables
  churned users to reactivate their subscription with a single click.
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

### Prerequisites & limitations

* You must have **Company**, **App Administrator**, or **App Member** permissions in Recurly Engage.

# Definition

The **1-Click Resubscribe** use case targets churned users visiting your site with a re-activation prompt. When their payment information is on file, they can restart their subscription instantly. Optionally, you can configure a second confirmation prompt (double opt-in) to verify intent.

# Key benefits

* **Effortless reactivation**: Allow users to resume subscriptions with a single click.
* **Revenue recovery**: Recover 10%+ of churned users through on-site prompts.
* **Flexible flow**: Add an optional double opt-in step to confirm reactivation.

# Key details

Churned users visiting your website can be targeted in real time with a re-activation prompt. If their card data is available in your subscriber system, they can reactivate in one click. Configure an optional confirmation prompt to double-check intent.

<Image align="center" className="border" border={true} src="https://files.readme.io/c958740-Screenshot_2024-04-30_at_12.18.40_PM.png" />

> 👍 For best results, consider providing an incentive to the user for resubscribing.

***

## Step-by-step

1. **Create** a **Churned Users** segment. Optionally create a separate Dunning segment.
2. **Create** a **Notification Prompt** (Settings > Prompts).
3. **Customize** the headline, message, and dynamic variables (e.g., first name).
4. Under **Add Action**, **select** your billing platform and specify the reactivation plan.
5. Optionally **set** the effective date for the plan change.
6. **Target** the prompt to the **Test Users** segment.
7. **Set** the trigger to fire on your homepage (e.g., URL `/`).
8. **Launch** the prompt.
9. **Add** your User ID to **Test Users** (Settings > Users > Test Users).
10. **Verify** the prompt appears when visiting the homepage.
11. **Update** the targeting to include the **Churned Users** segment for production.

## Example

<HTMLBlock>{`
<div style="position: relative; padding-bottom: 62.5%; height: 0;">
  <iframe src="https://www.loom.com/embed/42ea0c623c0e48b98d77e1d992ed0686?sid=fb0b44f8-127c-4072-a45a-8e0fa757f6a2"
    frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen
    style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;">
  </iframe>
</div>
`}</HTMLBlock>