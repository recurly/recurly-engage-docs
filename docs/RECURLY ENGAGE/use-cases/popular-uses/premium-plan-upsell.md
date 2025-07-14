---
title: Premium plan adoption
excerpt: >-
  Configuration guide for the Premium Plan Adoption use case, which targets
  engaged users with contextual prompts to upgrade to premium plans or add-ons.
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

Most subscription businesses use outbound email campaigns to inform users about premium plans and add-ons. While effective for highly engaged users, casual visitors need context to understand the value of upgrading. Recurly Engage offers an on-site, personalized approach: prompt users who haven’t purchased an add-on or premium plan, using screen- or event-based triggers to deliver relevant upgrade messaging precisely when it matters.

### Prerequisites & limitations

* You must have **Company**, **App Administrator**, or **App Member** permissions in Recurly Engage.

# Definition

The **Premium Plan Adoption** use case delivers targeted on-site prompts to users who meet engagement criteria but haven’t yet upgraded, leveraging contextual triggers (page views or events) for maximum relevance.

# Key benefits

* **Increased conversions**: Reach users in context to motivate plan upgrades.
* **Personalized offers**: Dynamically tailor messaging based on user behavior and variables (e.g., first name).
* **Optimized timing**: Trigger upgrade prompts on key screens or after specific actions to maximize impact.

# Key details

This scenario prompts users on your site who have not yet purchased the add-on or premium plan, providing them with contextual upgrade offers. By configuring the trigger on relevant screens or events, you ensure users see the right message at the right time.

<Image align="center" className="border" border={true} src="https://files.readme.io/b953f97-Screenshot_2024-04-22_at_4.48.39_PM.png" />

***

## Guide

1. **Modify** the **Engaged Users** segment to include users on the target subscription plan.
2. **Create** a **Popup Prompt** (Settings > Prompts) and **customize** the headline, message, and dynamic variables (e.g., first name).
3. Under **Add Action**, **select** your [Billing](billing) platform and specify the plan to which users should upgrade.
4. Optionally **set** the effective date for the plan change.
5. **Target** the prompt to the **Test Users** segment.
6. **Set** the trigger to fire on the homepage (e.g., URL `/`), or other key pages.
7. **Start** the prompt.
8. **Add** your User ID to **Test Users** (Settings > Users > Test Users).
9. **Verify** the prompt launches when you visit the homepage.
10. **Update** the prompt’s targeting to include **Engaged Users** for production roll-out.

## Example

<HTMLBlock>{`
<div style="position: relative; padding-bottom: 62.5%; height: 0;">
  <iframe src="https://www.loom.com/embed/c977818bce834868ae954663a38083f2?sid=6e1c0360-be70-4276-ba3e-38d96ed60a1b"
    frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen
    style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;">
  </iframe>
</div>
`}</HTMLBlock>