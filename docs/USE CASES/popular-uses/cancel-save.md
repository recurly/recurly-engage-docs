---
title: Cancel save
excerpt: >-
  Configuration guide for the “Cancel Save” use case, which intercepts
  cancellation flows to offer retention prompts.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  pages:
    - slug: popular-uses
      title: Popular Uses
      type: basic
---
# Overview

### Video

Here is a video tutorial that shows how to set this up for your website and app.

<Embed url="https://www.loom.com/embed/37d0ba60b71e4444be6ddcfe14e56add?sid=77dddded-5f13-4cd0-899b-9105cde9f286" href="https://www.loom.com/embed/37d0ba60b71e4444be6ddcfe14e56add?sid=77dddded-5f13-4cd0-899b-9105cde9f286" typeOfEmbed="iframe" height="480px" width="100%" iframe="true" />

> 🚧 Note:
>
> Conversions are significantly lower when using a redirect URL instead of 1-Click Actions.

### Prerequisites & limitations

* You must have **Company**, **App Administrator**, or **App Member** permissions in Recurly Engage.

# Definition

The **Cancel Save** use case intercepts the cancel button click and presents users with a personalized retention offer instead of immediately canceling.

# Key benefits

* **Reduced churn**: Present targeted offers at the moment of intent to cancel.
* **Improved satisfaction**: Allow users to choose alternatives rather than forcing cancellation.
* **Data-driven insights**: Capture cancellation reasons to optimize retention strategies.

# Key details

One of the most popular uses of Recurly Engage is intercepting the cancel button click and presenting the user with a personalized offer.

<Image align="center" className="border" border={true} src="https://files.readme.io/ba41c6a-Screenshot_2024-04-05_at_2.52.10_PM.png" />

> 📘 When combined with [1-Click Actions](actions-1), you can expect significant reductions in cancellations with improved customer satisfaction.

## Guide

1. **Enable** [1-Click Actions](actions-1) by activating the connector to your [Billing](billing) platform.
2. Alternatively, **specify** a redirect URL to an existing cancellation confirmation screen.
3. **Create** a Guide (Settings > Guides) and set the type to **survey**.
4. **Define** the cancellation reasons options with corresponding CTAs:

* Too expensive → CTA to a save offer
* Not enough content → CTA to latest content or save offer
* Technical issues → CTA to support

5. **Create** an A/B experiment on any prompt variation to test different offers or designs.
6. **Set** the segment to **Test Users**.
7. **Set** the trigger to fire on the cancel button click:

* Use the Live Preview tool to detect and capture the cancel click event.
* Or have your developers specify the click event via regex or custom JavaScript.

8. **Start** the **Guide**.
9. **Add** your User ID to the Test Users segment (Settings > Users > Test Users).
10. **Confirm** that the **Guide** launches when you click the cancel button.

## Example

<HTMLBlock>{`
<div style="position: relative; padding-bottom: 62.5%; height: 0;">
  <iframe  
    src="https://www.loom.com/embed/3a55570da3084432bf8516b442ab5590?sid=80617f1e-c3be-4bc3-b322-99d6ad886dee"  
    frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen  
    style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;">
  </iframe>
</div>
`}</HTMLBlock>