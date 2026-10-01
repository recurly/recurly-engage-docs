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
<div class="rp-page">
  <div class="rp-overview">Triggers set the exact criteria for when a prompt appears. This guide covers the trigger types and options available for Web prompts in Recurly Engage. For device prompts, refer to the software development kit (SDK) docs: <a href="https://help.redfast.com/docs/ios-sdk" target="_blank">iOS SDK</a> and <a href="https://help.redfast.com/docs/android-sdk" target="_blank">Android SDK</a>.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly Engage subscription plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites and limitations

<ul class="rp-list">
  <li>You must have <strong>Company</strong>, <strong>App Administrator</strong>, or <strong>App Member</strong> permissions in Recurly Engage.</li>
  <li>Collaborate with your development or product team to identify URLs, Cascading Style Sheets (CSS) selectors, or custom logic.</li>
</ul>

# Definition

<div class="rp-definition">A trigger is a rule that opens a prompt when a visitor views a specified page, clicks a designated element, or meets custom criteria you define with JavaScript. Triggers control when and where a prompt appears.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-bullseye" aria-hidden="true"></i></div>
    <strong>Precision targeting</strong>
    <span>Show prompts exactly when and where they matter.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-recycle" aria-hidden="true"></i></div>
    <strong>Reusable rules</strong>
    <span>Define a trigger once and apply it across multiple prompts.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-code" aria-hidden="true"></i></div>
    <strong>Advanced flexibility</strong>
    <span>Use wildcards, regular expressions, or custom code for sophisticated scenarios.</span>
  </div>
</div>

# Key details

Triggers set the criteria for when a prompt displays. To configure triggers in the console:

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open Prompt Details</h4><p>Under <span style={{fontWeight: "bold"}}>Prompts</span>, open the prompt to view <span style={{fontWeight: "bold"}}>Prompt Details</span>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Edit the triggers</h4><p>Select the <span style={{fontWeight: "bold"}}>Edit</span> (pencil) icon beside <span style={{fontWeight: "bold"}}>Triggers</span>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Create or reuse a trigger</h4><p>Select <span style={{fontWeight: "bold"}}>Create new trigger</span> to define a new rule, or <span style={{fontWeight: "bold"}}>Select &amp; Add trigger</span> to reuse an existing one.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/0e913f0-image.png" align="center" width="75%" border={true} />



<Image src="https://files.readme.io/b54e824-image.png" align="center" width="75%" border={true} />


<div class="rp-callout rp-callout-warning">
  <div><strong><i class="fa-solid fa-triangle-exclamation" aria-hidden="true"></i> Warning</strong>Any edits to a saved trigger in Prompt Details apply to all prompts that use that trigger. Create a new trigger for prompt-specific behavior.</div>
</div>

## Page trigger

The page trigger displays a prompt when visitors arrive on a screen that matches the specified URL path. Set a delay timer to show the prompt after a number of seconds instead of immediately.


<Image src="https://files.readme.io/1227b33-Screenshot_2024-04-25_at_19.21.09.png" align="center" width="75%" border={true} />


### Any page

This option triggers your prompt on every page of your site.


<Image src="https://files.readme.io/2c363a4-Screenshot_2024-04-25_at_19.22.59.png" align="center" width="75%" border={true} />


### URL path

<div class="rp-callout rp-callout-important">
  <div><strong><i class="fa-solid fa-circle-exclamation" aria-hidden="true"></i> Important</strong>The trigger builder matches only against the path of the URL, not the full domain. Including the highest-level domain (for example, <code>https://www.example.com</code>) in your trigger rule prevents the trigger from firing correctly.</div>
</div>

For example, to match `https://www.example.com/path/`, enter only `/path/` in the trigger URL Path field.

### Wildcard URL path

Match URL patterns using `*`. Always include a leading slash.

**Examples:**

* `/categories/*` matches `/categories/123` or `/categories/123/detail`
* `/categories/movies/*` matches `/categories/movies/top-ten`
* `/movies/the-*` matches `/movies/the-end` or `/movies/the-best/123`


<Image src="https://files.readme.io/929942b-Screenshot_2024-04-25_at_19.27.22.png" align="center" width="75%" border={true} />


#### Match query parameters

Match URL query parameters. Wildcards are allowed.

* `campaignid=*`
* `id=*&referrer_id=456`
* `utm=mycampaign`

#### Match URL hash

Match URL fragments after `#`.

* `#anchor1`
* `#category*`

Combine Wildcard URL Path, Query Parameters, and URL Hash. Leave fields blank if you don't use them.


<Image src="https://files.readme.io/25bec36-Screenshot_2024-04-25_at_21.36.00.png" align="center" width="75%" border={true} />


### Regular expression URL path

Use regular expressions (regex) for complex include and exclude patterns.

#### Exclude URL paths

* `^(?!\/accounts).*` excludes any path starting with `/accounts/`
* `^(?!\/category\/live-news).*` excludes `/category/live-news`

#### Exclude query parameters

* `^(?!campaign_id).*` excludes URLs containing `campaign_id`

#### Exclude URL hash

* `^(?!#section_5).*` excludes hash `#section_5`

#### Complex regular expressions

For complex regular expressions, contact your Customer Success team or <a href="mailto:support@recurly.com">[support@recurly.com](mailto:support@recurly.com)</a> for assistance.

**Examples:**

* `/skus/123[a-z]{3,}456` matches stock keeping unit (SKU) paths like `/skus/123abc456`
* `/series/.+-episode-[246]` matches episodes ending in 2, 4, or 6


<Image src="https://files.readme.io/a7d9477-Screenshot_2024-04-29_at_18.00.48.png" align="center" width="75%" border={true} />


### Regular expression tester

Validate sample paths against your regular expression.


<Image src="https://files.readme.io/a61d37b-Screenshot_2024-04-29_at_18.04.25.png" align="center" width="75%" border={true} />



<Image src="https://files.readme.io/ddfd19c-Screenshot_2024-04-29_at_18.06.00.png" align="center" width="75%" border={true} />


## Click trigger

A click trigger displays a prompt after a set number of clicks on a specific element, which you identify with a CSS selector.

**Examples:**

* After five clicks on any element (`*`).


<Image src="https://files.readme.io/66db085-Screenshot_2024-04-29_at_18.08.12.png" align="center" width="75%" border={true} />


* After one click on the Cancel Subscription button (`#cancel-subscription`) on `/accounts`.


<Image src="https://files.readme.io/001f9ed-Screenshot_2024-04-29_at_18.10.37.png" align="center" width="75%" border={true} />


## Advanced trigger

Use custom client-side code when the built-in triggers aren't enough. Advanced triggers are available for Web SDK clients.

### Create a new advanced trigger

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open Advanced Triggers</h4><p>Navigate to <span style={{fontWeight: "bold"}}>Settings &gt; Triggers &gt; Advanced Triggers</span>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Add your function</h4><p>Select <span style={{fontWeight: "bold"}}>New Advanced Trigger</span>, give it a name, and paste your JavaScript function that returns <code>true</code> or <code>false</code>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Save the trigger</h4><p>Save your changes. They deploy within minutes.</p></div>
  </div>
</div>

### Polling-based examples

Polling-based triggers evaluate conditions every two seconds by default:

1. Specified element exists (<a href="https://help.redfast.com/recipes/advanced-trigger-element-exists-on-page" target="_blank">Recipe</a>)
2. Specified text exists (<a href="https://help.redfast.com/recipes/advanced-trigger-text-exists-on-page" target="_blank">Recipe</a>)
3. User scroll depth (<a href="https://help.redfast.com/recipes/advanced-trigger-scroll-depth" target="_blank">Recipe</a>)
4. Video watched percentage

```javascript
const video = document.querySelector("video[data-html5-video]");
if (!video) return false;
const percent = (video.currentTime / video.duration) * 100;
return percent >= 90;
```

### Event-based examples

Event-based triggers react to specific events once:

#### User attempts to leave the page

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

#### User is idle for more than 30 seconds

```javascript
if (!window.lastActiveTs) {
  window.lastActiveTs = Date.now();
  document.onmousemove = document.onkeypress = () => window.lastActiveTs = Date.now();
}
return (Date.now() - window.lastActiveTs) > 30000;
```

### Use an advanced trigger

When you edit a prompt, select your advanced trigger.

* For polling-based triggers, set the polling interval (default two seconds).
* For event-based triggers, choose <span style={{fontWeight: "bold"}}>Event-based</span> mode.


<Image src="https://files.readme.io/49ebd62-Screenshot_2024-04-29_at_18.12.52.png" align="center" width="75%" border={true} />


<div class="rp-card">For help configuring triggers, contact your Customer Success team or <a href="mailto:support@recurly.com">support@recurly.com</a>.</div>
