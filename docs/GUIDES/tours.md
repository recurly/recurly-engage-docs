---
title: Tours
excerpt: >-
  Build a Tour in Recurly Engage — a multi-step, element-anchored tooltip
  walkthrough that guides subscribers through your site.
deprecated: false
hidden: false
metadata:
  robots: index
---
Create a Tour in Recurly Engage to guide subscribers through your site with a sequence of element-anchored tooltips.

## Prerequisites

Confirm that you have Company, App Administrator, or App Member permissions in Recurly Engage.

## Supported devices

Tours run in standard web browsers only. They do not support connected TV (CTV), mobile, or other device platforms.

## How Tours work

A Tour is a guide type that presents floating tooltips anchored to specific elements on your site. Use Tours for onboarding, feature discovery, and guided navigation without a third-party onboarding tool.

Subscribers move through steps in a fixed sequence. They can return to steps they have already viewed, and steps can span multiple pages—for example, from a homepage to an account page.

Each Tour step is a web notification prompt with these Tour-specific capabilities:

- **Pin to element:** Anchor the prompt to a page element with a CSS selector, then position it above, below, to the left, or to the right of that element. Pinning overrides the size and position in the prompt's standard settings.
- **Scroll into view:** When the anchored element is off-screen, scroll it to the top, center, or bottom of the viewport. You can also turn off automatic scrolling.

**Button 1** advances to the next step, and **Button 2** acts as the **Back** button. Dismissing a step with the X exits the entire Tour. Subscribers cannot skip ahead, but they can move backward and forward among steps they have reached.

Tour steps inherit the guide's Limits, Segments, and Schedule settings.

## Build a Tour

1. Go to **Guides** > **New Guide**.
2. Enter a **Name** and, optionally, a **Description**. Select the **Tour** guide type and your **Segments**.
3. Add Tour steps in the order subscribers should see them. Each step is a web notification prompt with its own content, targeting, and placement.
4. Configure **Pin to** for each step:
   1. Open the prompt design editor.
   2. In the **Pin to** section, enter the CSS selector for the element that should anchor the tooltip.
   3. Choose the tooltip placement: top, bottom, left, or right.
5. Under **User interactions**, set **Show prompt again after Button 1 click** and **Show prompt again after Button 2 click** to **Amount of time: 0 minutes**. Set the **Fadeout timer** to **0 seconds**.
6. Set a **transition URL** on each step that moves the subscriber to another page. This URL tells Engage where to navigate when the subscriber moves forward or backward in the Tour.
7. Preview the Tour on your site to confirm its positioning and copy, then click **Start** to make it live.

## Optional: Configure scrolling

For each step, configure **Scroll into view** to scroll the anchored element to the top, center, or bottom of the viewport when the step triggers. Turn off this setting when you do not want the page to scroll automatically.

## Optional: Set guide limits and schedule

Set **Limits** and a **Schedule** for the entire Tour.

After the Tour is live, monitor step completions and exits in Engage analytics. Update the copy or placement for steps where subscribers drop off.
