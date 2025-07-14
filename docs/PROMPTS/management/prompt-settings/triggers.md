---
title: Triggers
excerpt: >-
  Instructions for configuring when and where your prompts should appear using
  page, event, and advanced triggers—all within a single, comprehensive guide.
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

Triggers allow you to specify the required criteria to show a prompt. This guide explains the different types of triggers and associated options for Web prompts. For device prompts, refer to the SDK docs ([iOS SDK](https://help.redfast.com/docs/ios-sdk), [Android SDK](https://help.redfast.com/docs/android-sdk)).

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

### Prerequisites & limitations

* You must have **Company**, **App Administrator** or **App member** permissions in Recurly Engage.
* Collaboration with your development or product team to identify URLs, CSS selectors, or custom logic.

# Definition

A **trigger** is a rule that opens a prompt when a user visits a specified page, clicks a designated element, or when custom criteria are met via JavaScript.

# Key benefits

* **Precision targeting**: Show prompts exactly when and where they matter.
* **Reusable rules**: Define triggers once and apply them across multiple prompts.
* **Advanced flexibility**: Leverage wildcards, regex, or custom code for sophisticated scenarios.

# Key details

Triggers allow you to specify the criteria for when and what you want your prompt to display. To configure triggers in the console:

1. **Open** the prompt under **Prompts** to **view** **Prompt Details**.
2. **Click** the **Edit** (pencil) icon beside **Triggers**.
3. **Choose** **Create new trigger** to define a new rule, or **Select & Add trigger** to reuse an existing one.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/0e913f0-image.png" />

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/b54e824-image.png" />

> 🚧 Note:
>
> Any edits to a saved trigger in Prompt Details will apply to all prompts using that trigger. Create a new trigger for prompt-specific behavior.

***

## Page trigger

The page trigger displays a prompt when visitors arrive on a screen matching the specified URL path. You can set a delay timer to show the prompt after a number of seconds instead of immediately.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/1227b33-Screenshot_2024-04-25_at_19.21.09.png" />

### Any page

This option triggers your prompt on every page of your site.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/2c363a4-Screenshot_2024-04-25_at_19.22.59.png" />

### Wildcard URL path

Match URL patterns using `*`. Always include a leading slash.\
**Examples:**

* `/categories/*` matches `/categories/123` or `/categories/123/detail`
* `/categories/movies/*` matches `/categories/movies/top-ten`
* `/movies/the-*` matches `/movies/the-end` or `/movies/the-best/123`

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/929942b-Screenshot_2024-04-25_at_19.27.22.png" />

#### Query parameters

Match URL query parameters; wildcards allowed.

* `campaignid=*`
* `id=*&referrer_id=456`
* `utm=mycampaign`

#### URL hash

Match URL fragments after `#`.

* `#anchor1`
* `#category*`

Combine Wildcard URL Path, Query Parameters, and URL Hash; leave fields blank if unused.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/25bec36-Screenshot_2024-04-25_at_21.36.00.png" />

### Regular expression URL path

Use regex for complex include/exclude patterns.

#### Exclude URL paths

* `^(?!\/accounts).*` excludes any path starting with `/accounts/`
* `^(?!\/category\/live-news).*` excludes `/category/live-news`

#### Query parameters

* `^(?!campaign_id).*` excludes URLs containing `campaign_id`

#### URL hash

* `^(?!#section_5).*` excludes hash `#section_5`

#### Complex regular expressions

Contact Customer Success for assistance.

* `/skus/123[a-z]{3,}456` matches SKUs like `/skus/123abc456`
* `/series/.+-episode-[246]` matches episodes ending in 2, 4, or 6

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/a7d9477-Screenshot_2024-04-29_at_18.00.48.png" />

### Regular expression tester

Validate sample paths against your regex.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/a61d37b-Screenshot_2024-04-29_at_18.04.25.png" />

<Image align="center" width="80% " src="https://files.readme.io/ddfd19c-Screenshot_2024-04-29_at_18.06.00.png" />

***

## Click trigger

Display a prompt after a set number of clicks on a specific element, identified by a CSS selector.

**Examples:**

* After 5 clicks on any element (`*`).

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/66db085-Screenshot_2024-04-29_at_18.08.12.png" />

* After 1 click on the Cancel Subscription button (`#cancel-subscription`) on `/accounts`.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/001f9ed-Screenshot_2024-04-29_at_18.10.37.png" />

***

## Advanced trigger

Utilize custom client-side code when built-in triggers are not sufficient. Available for Web SDK clients.

### Create a new advanced trigger

1. Navigate to **Settings > Triggers > Advanced Triggers**.
2. Click **New Advanced Trigger**, give it a name, and paste your JavaScript function that returns `true` or `false`.
3. Save; changes deploy within minutes.

### Polling-based examples

Evaluate conditions every 2 seconds by default:

1. Specified element exists ([Recipe](https://help.redfast.com/recipes/advanced-trigger-element-exists-on-page))
2. Specified text exists ([Recipe](https://help.redfast.com/recipes/advanced-trigger-text-exists-on-page))
3. User scroll depth ([Recipe](https://help.redfast.com/recipes/advanced-trigger-scroll-depth))
4. Video watched percentage

```javascript
const video = document.querySelector("video[data-html5-video]");
if (!video) return false;
const percent = (video.currentTime / video.duration) * 100;
return percent >= 90;
```

### Event-based examples

React to specific events once:

1. **User attempts to leave page**

```javascript
const isLeaving = await new Promise(res => {
  document.addEventListener("mouseout", function onLeave(e) {
    if (!e.toElement && !e.relatedTarget) {
      document.removeEventListener("mouseout", onLeave);
      res(true);
    }
  });
});
return isLeaving;
```

2. **User idle >30s**

```javascript
if (!window.lastActiveTs) {
  window.lastActiveTs = Date.now();
  document.onmousemove = document.onkeypress = () => window.lastActiveTs = Date.now();
}
return (Date.now() - window.lastActiveTs) > 30000;
```

### Using an advanced trigger

When editing a prompt, select your Advanced Trigger.

* For polling-based triggers, set the polling interval (default 2s).
* For event-based triggers, choose **Event-based** mode.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/49ebd62-Screenshot_2024-04-29_at_18.12.52.png" />

***

# Help

For assistance configuring triggers, contact your Customer Success team.