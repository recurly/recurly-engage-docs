---
title: Triggers
excerpt: ''
deprecated: false
hidden: false
link:
  new_tab: true
  url: https://help.redfast.com/docs/triggers-1#/
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Triggers allow you to specify the required criteria to show a prompt. This guide will explain the different types of triggers and associated options. For the purposes of this guide, we will assume that Web prompts are in use. Triggers on device prompts require use of the SDKs ([link](https://help.redfast.com/docs/ios-sdk)).

# Page Trigger

The page trigger is the most common type of trigger that displays a prompt when visitors arrive on a screen with the matching URL path. You may set a timer that will show the prompt after specified number of seconds rather than immediately.

<Image align="center" className="border" border={true} src="https://files.readme.io/1227b33-Screenshot_2024-04-25_at_19.21.09.png" />

## Any Page

This basic option will trigger your prompt on any page of your site.

<Image align="center" className="border" border={true} src="https://files.readme.io/2c363a4-Screenshot_2024-04-25_at_19.22.59.png" />

## Wildcard URL Path

This option will trigger prompts on pages with the matching URL path. Below are a few examples; note to always include the first slash when specifying the URL path.

**Wildcard examples**

* `/categories/*` - matches any url path matching the wildcard, such as `/categories/123` or `/categories/123/detail`
* `/categories/movies/*`- matches url paths like`/categories/123/movies/456` or `/categories/movies/top-ten`
* `/movies/the-*`- matches `/movies/the-end`or `/movies/the-best/123`

<Image align="center" src="https://files.readme.io/929942b-Screenshot_2024-04-25_at_19.27.22.png" />

### Query Parameters

Triggers may also include matches against query parameters. Wildcard expressions may be used. 

Examples:

* `campaignid=*`
* `id=*&referrer_id=456`
* `utm=mycampaign`

### URL Hash

Triggers may include matches against URL hash properties containing the `#` character and is typically used to jump to various page anchors.

Examples:

* `#anchor1`
* `#category*`

Wildcard URL, Query Parameter and URL Hash options may be combined per the below example. Leave the appropriate input field blank if you do not want to utilize one or more of these options.

<Image align="center" src="https://files.readme.io/25bec36-Screenshot_2024-04-25_at_21.36.00.png" />

## Regular Expression URL Path

This option also allows you specify matching URL paths with a regular expression. A common use case is specifying a regular expression to exclude specific groups of URL paths.

### Exclude URL Paths

Examples:

`^(?!\/accounts).*`- Includes all URL paths except for anything starting with `/accounts/`\
`^(?!\/category\/live-news).*`- Include all URL paths except for anything starting with `/category/live-news`

### Query Parameters

Example:

* `^(?!campaign_id).*` - Excludes URLs which contain the `campaign_id` parameter

### URL Hash

Example:

* `^(?!#section_5).*` - Excludes hash property `section_5`

### Complex Regular Expressions

Please reach out to your Customer Success Manager for help creating regular expressions for your use case.

Examples:

* `\/skus\/123[a-z]{3,}456` - Match all SKUs in your catalog that start with 123 and end with 456 that have 3 or more letters in between, for example, `/skus/123abc456` and `/skus/123wxyz456`
* `\/series\/.+-episode-[246]`- Match all episodes in the catalog that end with episode 2, 4, 6, for example,  `/series/the-last-pumpkin-episode-2` and `/series/fav-widget-show-episode-6`

<Image align="center" className="border" border={true} src="https://files.readme.io/a7d9477-Screenshot_2024-04-29_at_18.00.48.png" />

### Regular Expression Tester

Use the tester to determine whether sample URL paths match the specified regular expression.

<Image align="center" className="border" border={true} src="https://files.readme.io/a61d37b-Screenshot_2024-04-29_at_18.04.25.png" />

<Image align="center" className="border" border={true} src="https://files.readme.io/ddfd19c-Screenshot_2024-04-29_at_18.06.00.png" />

# Click Trigger

Click triggers will show a prompt after a specified number of clicks have occurred on a specific element of a page. CSS query selectors are utilized to identify the element. Your web designer or web developer can help you determine the appropriate CSS query selector, or you may reach out to your Customer Success Manager for assistance.

Here are some examples:

* The prompt will be shown after 5 clicks on anything on any page. The CSS query selector `*` indicates that all page elements will be monitored for clicks.

<Image align="center" className="border" border={true} src="https://files.readme.io/66db085-Screenshot_2024-04-29_at_18.08.12.png" />

* The prompt will be shown after a single click of the Cancel Subscription button on the `/accounts` page. The CSS query selector `#cancel-subscription` references the appropriate button on the Account page.

<Image align="center" className="border" border={true} src="https://files.readme.io/001f9ed-Screenshot_2024-04-29_at_18.10.37.png" />

# Advanced Trigger

Advanced Triggers utilize custom client side code to determine when a prompt should be shown. This is utilized when the triggering criteria includes additional logic that is not satisfied by the normal Page URL and Click Trigger options.

This option is only available for clients utilizing the Javascript SDK (desktop/mobile browser, HTML5 smart TV devices).

## Create New Advanced Trigger

**Add Custom Javascript Code**

1. Visit Settings → Triggers → Advanced Triggers
2. Create a new Advanced Trigger. Specify the Name and include the Javascript implementation of your custom logic. The code should return a Boolean (`true` when custom criteria have been met, `false` otherwise).
3. Save the Advanced Trigger. It may take a few minutes for the new changes to be deployed.

## Examples

Below are examples of Advanced Triggers to get you started. You may utilize existing Recipes of Advanced Triggers already included in your app, which may be deployed after small modifications.

### Polling Based

Polling based advanced triggers check on a periodic basis (default: every 2 seconds) to determine whether the condition of your logic has been met.

1. Specified element exists on page (See [Recipe](https://help.redfast.com/recipes/advanced-trigger-element-exists-on-page))
2. Specified text exists on page (See [Recipe](https://help.redfast.com/recipes/advanced-trigger-text-exists-on-page))
3. User has scrolled X percent of the page (See [Recipe](https://help.redfast.com/recipes/advanced-trigger-scroll-depth))
4. User watches X percent of video (assuming standard HTML5 Video element)

```javascript
const video = document.querySelector("video[data-html5-video]");
if (!video) return false;
const decimalPercent = video.currentTime / video.duration;
const currPercent = decimalPercent \* 100;
const activationPercent = 90;
const isActive = currPercent >= activationPercent;
return isActive;
```

### Event Based

Event based advanced triggers are set once and respond to events like click, keypress and scroll.

1. User attempts to leave the current page

```javascript
const isLeaving = await new Promise((res, reject) => {  
  document.addEventListener("mouseout", function userLeaves(e) {  
	if (!e.toElement && !e.relatedTarget) {  
	  document.removeEventListener("mouseout", userLeaves);  
	  res(true);  
	}  
  });  
});

return isLeaving;
```

2. User has become inactive (30 seconds idle time).

```javascript
if (!window.loaded) {  
  window.lastActiveTs = +new Date();  
  function updateLastTs() {  
    window.lastActiveTs = +new Date();  
    console.log("updated lastTs", window.lastActiveTs);  
  }  
  document.onmousemove = updateLastTs;  
  document.onkeypress = updateLastTs;  
  console.log("loaded");  
  window.loaded = true;  
}  
const minuteElapsed = +new Date() - window.lastActiveTs > 30 \* 1000; //e.g. change the 30 here to 120 for 2 seconds  
console.log(  
  minuteElapsed,  
  +new Date(),  
  window.lastActiveTs,  
  +new Date() - window.lastActiveTs,  
);  
return minuteElapsed;
```

## Using Advanced Triggers

Update a trigger and select the Advanced Trigger from the dropdown. Note that all options of the trigger, including the advanced trigger criteria, must be satisfied before the prompt is shown.

If the Advanced Trigger is to be polled, set the polling interval. In most cases the default setting of 2 seconds is sufficient.

If the Advanced Trigger is event based, select "Event-based" option.

<Image align="center" className="border" border={true} src="https://files.readme.io/49ebd62-Screenshot_2024-04-29_at_18.12.52.png" />

# Help

Don't hesitate to reach out to your Customer Success team if you need assistance with your triggers.