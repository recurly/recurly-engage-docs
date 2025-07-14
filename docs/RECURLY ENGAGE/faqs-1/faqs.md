---
title: Debugging a prompt that is not showing
excerpt: >-
  Configuration guide for debugging prompts that fail to display in Recurly
  Engage.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# How do I debug a prompt that isn’t showing?

First, verify your basic setup: the Recurly Engage tag must be loaded on the page (check for ping calls in your network inspector), the prompt status must be **Active**, and the correct segment must be applied and enabled.

Next, confirm you’re targeting the right user: ensure the User ID you’re testing with belongs to the prompt’s segment (impersonate in Preview or use User Lookup) and check the ping payload’s `segments` array.

Then, double-check your trigger criteria:

* If it’s page-based, make sure you’re on the exact URL defined.
* If it’s click-based, verify the element’s CSS selector matches your trigger settings.
* For survey or multi-step guides, ensure any prerequisite prompt is also **Active** and has fired.

Once those are correct, look in the ping response under **paths** to see if the prompt was delivered:

<Image align="center" className="border" border={true} src="https://files.readme.io/73b7658-image.png" />

If the prompt appears under `paths` but doesn’t render, check for an active experiment control group. Open the corresponding `path` object in the payload and inspect its `action_group_name`—if it’s set to **Control**, that User ID is held out by design:

<Image align="center" className="border" border={true} src="https://files.readme.io/67a6aa2-image.png" />

If no path is delivered, review any limits or interaction settings: make sure impression limits, frequency caps, or “Show prompt again after button click” options aren’t preventing display.

> 📘 To reset any suppression, clear the user’s prompt state and re-test:
>
> * In Live: **Settings > Users > Test Users > Reset Goals**
> * In Console:
>
> ```js
> RecurlyEngage.resetGoals(true);
> ```
>
> Then refresh the page a few times to restore eligibility:
>
> <Image align="center" className="border" border={true} src="https://files.readme.io/89184dd-image.png" />