---
title: Prompts
excerpt: >-
  An introduction to in-app messaging prompts in Recurly Engage and quick access
  to their management console.
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

Prompts are versatile in-app messages designed to engage users with timely calls to action. Whether you want to announce a feature, offer a discount, or gather feedback, prompts help drive the actions that matter most.

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

# Definition

A **prompt** is an in-app message that appears when a user visits your application or website. It consists of a headline, body copy, background, and up to three call-to-action buttons. Recurly Engage supports multiple prompt types—overlay and inline—across desktop, mobile, tablet, and TV devices.

# Key benefits

* **Contextual engagement**: Reach users at the right moment with targeted in-app messages.
* **Flexible customization**: Choose from various prompt types, designs, triggers, and schedules to match your brand and objectives.
* **Data-driven optimization**: Leverage segments, limits, and A/B experiments to refine and improve performance.

# Prompt types

Recurly Engage supports a variety of in-app message formats, all designed in accordance with the [IAB Guidelines](https://www.iab.com/guidelines/iab-new-ad-portfolio/):

* [Inlines](inlines) (horizontal, vertical, tile, text-only): Prompts embedded directly within your page layout.
* [Overlays](overlays) (notification, interstitial, pop up, video, bottom banner): Floating prompts that appear above your content.
* [Invisible](invisible-1): Silent prompts delivered via tracking pixels or JavaScript callbacks for analytics.
* [Email](other): Messages sent outside the page—email campaigns.
* [Push](push): Scheduled notifications sent to users’ devices (ADM, APNs, FCM) to drive re-engagement.
* [Video](video): Rich-media overlays that play video content with text and call-to-action buttons in a popup modal.
* [Mobile interstitial](mobile-interstitial): Full-screen native prompts on iOS and Android, rendered via the SDK for immersive mobile experiences.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/b91dfe4-image.png" />

A prompt can be targeted to one or more [Segments](segments) and set to [Trigger](triggers) on events like button clicks, page visits, or time spent on a page. You can [Schedule](schedule-1) prompts for specific dates and times and [Limit](limits) their delivery by user count or budget. For use-case inspiration, explore our [Popular Use Cases](popular-uses).

It’s also possible to run A/B tests with our built-in [Experiments](experiments-1), helping you choose the most effective variation before a full rollout.

Creating prompts is core to what your customers experience. In this section, you’ll find detailed how-to guides for building and managing every prompt type. If you need hands-on support or want us to manage campaigns on your behalf, chat with us to learn about our Managed Campaign options.

The **Prompts** page provides a quick view of all prompts in your account, displaying their status, design preview, target segments, schedule, and high-level performance metrics (impressions, clicks, CTR). Use the **Search** bar or filters (Status, Device/type, Segment) to find what you need.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/b2e10b0-Screenshot_2024-04-18_173049.png" />