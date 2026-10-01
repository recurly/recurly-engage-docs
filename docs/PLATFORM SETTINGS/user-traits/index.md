---
title: User traits
excerpt: >-
  This article explains how to import, configure, and manage custom user traits
  in Recurly Engage to extend targeting beyond default behavior metrics.
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
  <div class="rp-overview">Usage tracking in Recurly Engage lets you record and normalize user interactions — like page views, button clicks, and time spent — so you can build dynamic segments and deliver personalized prompts at the right moment.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly Engage plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
    <a class="rp-toc-pill" href="#set-up-a-tracker"><span class="rp-toc-num">4</span>Set up a tracker</a>
    <a class="rp-toc-pill" href="#tracking-web-actions-from-other-sites"><span class="rp-toc-num">5</span>Tracking web actions from other sites</a>
    <a class="rp-toc-pill" href="#using-events-in-google-tag-manager"><span class="rp-toc-num">6</span>Using events in Google Tag Manager</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have <span style={{fontWeight: "bold"}}>Company</span> or <span style={{fontWeight: "bold"}}>App Administrator</span> permissions in Engage.</li>
</ul>

# Definition

<div class="rp-definition">Usage tracking in Engage captures quantitative user behaviors — visits, duration, and custom events — normalizes them, and makes them available as traits for segmentation and targeting.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Fine-grained targeting</strong>
    <span>Segment users by exact frequency and recency of actions, such as the top 10% of visitors by daily active minutes.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Real-time normalization</strong>
    <span>Metrics are normalized on a 0–10 scale as data arrives, making thresholds intuitive and adaptive.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div>
    <strong>Custom event support</strong>
    <span>Beyond pages and clicks, ingest backend or partner events to track off-site conversions.</span>
  </div>
</div>

# Key details

## Usage tracking

Engage usage tracking lets you track individual consumption of the value-creating elements of your app or site.

A trait is an individual user attribute or behavior that you can target, such as device, location, or even business metrics (for example, lifetime value or satisfaction score). Engage lets you track traits based on how often a user has engaged with a specific feature or section of your app, and target users by frequency and recency of engagement for maximum impact. By default, usage traits automatically track visits and minutes, but you can configure them to track additional behaviors in your apps, such as specific pages or screens visited or buttons clicked.

Usage traits can be normalized on a 0–10 scale, with the lowest value in the dataset normalized to 0 and the highest value normalized to 10. Normalization happens in real time as new low and high values are recorded. This lets business teams define “Heavy users” as users whose minutes per visit are growing by 30% or more week over week, without needing to understand site-wide averages or highs and lows.

## Understanding usage tracking

Below are the types of usage trackers that are available. A newly added tracker begins collecting information immediately, and it may take up to 24 hours before it can produce meaningful targeting options.

### Visit duration

Time spent by the user in the app in MM:SS. Visit duration is recorded at the user level on a daily, weekly, and monthly basis.

### Visits

The number of times a user visits your site or app. Visits are recorded on a daily, weekly, and monthly basis. The default visit length is 10 minutes, which is extended in 10-minute increments for as long as the user is using the app.


<Image src="https://files.readme.io/6af03f8-image.png" align="center" width="75%" border={true} />


For day-over-day comparison, Engage compares data from **midnight to midnight on one day versus the previous day**. For week-over-week comparison, Engage compares data from **midnight Sunday to midnight Sunday**.

### Traits tracked automatically

In addition to visits and minutes, Engage automatically tracks or creates:

- **Churn Score** — A number between 0–1 indicating the probability that a user will churn, derived using machine learning.
- **Device Type** — Phone, tablet, laptop, desktop, TV, watch. Also includes full user agent string.
- **Device OS** — iOS, Android, Windows, MacOS, other. Also includes full user agent string.
- **Device Browser** — Chrome, Chrome Mobile, Safari, Edge, other. Also includes full user agent string.
- **Device Manufacturer** — Apple iPhone, Apple iPad, Nexus, Samsung, other. Also includes full user agent string.
- **Device SDK** — Android Phone, Android Tablet, Google TV, Roku, other. Also includes full user agent string.

The following optional items require processing the end user's IP address. Engage never stores IP addresses.

- **Fraud score** — A number between 0–10 ranking the user's likelihood of being a fraudulent user, derived using machine learning.

See <a href="/docs/data-privacy" target="_blank">data privacy</a> for more information on how we process end-user information.

In addition, you can customize the tracker to collect information on specific pages or button clicks.

## Concurrent logins and password sharing

The Concurrent logins segment logic identifies when a single user account is actively logged in from multiple locations simultaneously.

- **Detection:** Generally, our proprietary, privacy-preserving algorithm detects concurrent logins from different locations within a single session.
- **Logic basis:** The system primarily uses different IP addresses (locations) to detect multiple concurrent logins. Multiple sessions originating from the same IP address are currently treated as a single concurrent login.
- **Segment setup:** You can set the number of concurrent logins you want to track in the Concurrent logins segment. It's one of our default segments, giving you a ready-made way to detect and prompt users who might be sharing their account credentials.
- **Security and compliance:** Helps flag potentially suspicious behavior, such as credential sharing or account takeover attempts, by monitoring access from geographically distinct locations.
- **Usage control:** Allows a merchant to enforce policies on where and how many times an account can be simultaneously active.

## Page tracker

A page tracker lets you track specific pages or groups of pages by using wildcards or regex. Here are two examples:


<Image src="https://files.readme.io/166e7b8-Screenshot_2024-04-25_at_15.03.06.png" align="center" width="75%" border={true} />


## Button tracker (web only)

A button tracker lets you track specific elements that a user clicks using Cascading Style Sheets (CSS):


<Image src="https://files.readme.io/ee7d53f-Screenshot_2024-04-25_at_15.06.07.png" align="center" width="75%" border={true} />


## Custom tracker

A custom tracker lets you send tracking information from any external system to Engage via API or software development kit (SDK), available on Roku, Apple TV, Android, and iOS. For example, if a user's payment has failed, you can send an event from your backend and target that user to update their credit card via Engage.


<Image src="https://files.readme.io/2db110e-image.png" align="center" width="75%" border={true} />


# Set up a tracker

Engage tracks your users' behaviors across your applications. By default, we automatically track user visits and minutes, but you can also add other trackers, such as button clicks and views. Once you've added a tracker, you can use it to target segments, such as the top 20% of users who have downloaded a video.

Here's how to set up a new tracker. Start by going to **Settings > Usage Tracking > Add New Tracker**:


<Image src="https://files.readme.io/4a51089-Screenshot_2024-04-25_at_15.40.54.png" align="center" width="75%" border={true} />


## Web usage

For web apps, you can create two types of trackers: **page** and **track**.

- **page** — Refers to visits to a particular page, such as `/settings` or `/signup`
- **track** — Refers to a CSS id such as `#download-btn` or a CSS class such as `.download-btn`

### Page example

To track a user's visits to the Settings page:

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Add a tracker</h4><p>Click <span style={{fontWeight: "bold"}}>“Add a tracker”</span> and change the value to match your app's URL path. In addition to actual URLs, you can use a regular expression to specify wildcard matches and other advanced URL configurations.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/1363ad0-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Save your changes</h4><p>Click <span style={{fontWeight: "bold"}}>“Save Changes.”</span></p></div>
  </div>
</div>


<Image src="https://files.readme.io/78b62f2-Screenshot_2024-04-25_at_15.46.49.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Add a new segment</h4><p>Go to add a new segment.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/4c6e5ea-Screenshot_2024-04-25_at_15.47.45.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Find your new trait</h4><p>Under the <span style={{fontWeight: "bold"}}>Usage</span> tab, you can see the newly added Engage trait you can target.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/dd7b0a2-Screenshot_2024-04-25_at_15.49.32.png" align="center" width="75%" border={true} />


### Track example

To track a user's clicks on a particular button:

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Add a tracker</h4><p>Click <span style={{fontWeight: "bold"}}>“Add a tracker”</span> and change the value to match your HTML button ID or button class.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/d35ff75-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Save your changes</h4><p>Click <span style={{fontWeight: "bold"}}>“Save Changes.”</span></p></div>
  </div>
</div>


<Image src="https://files.readme.io/319b3dc-Screenshot_2024-04-25_at_15.52.46.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Add a new segment</h4><p>Go to add a new segment, as shown in the Page example above.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Find your new trait</h4><p>Under the <span style={{fontWeight: "bold"}}>Usage</span> tab, you can see the newly added Engage trait you can target.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/6d939dd-image.png" align="center" width="75%" border={true} />


## Device usage (Roku, Apple TV, Android, iPhone, iPad, or web)

For TVs, tablets, and phones, you can create one type of tracker — **custom**. You'll likely need your app developer's help to integrate a snippet of code that we provide directly from Pulse.

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>If you don't have the device SDK integrated or you're tracking from a third party, you can only track via the cURL option in step 4.</div>
</div>

### Custom example

This example shows you how to add a custom tracker. You can use it to track anything on your client, such as a button click, visits to different screens, or a payment.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Add a tracker</h4><p>Click <span style={{fontWeight: "bold"}}>“Add a tracker”</span> and name your tracker.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/94cdc46-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Save your changes</h4><p>Click <span style={{fontWeight: "bold"}}>“Save Changes”</span> (<span style={{fontWeight: "bold"}}>Settings → Integrations</span>).</p></div>
  </div>
</div>


<Image src="https://files.readme.io/06d104c-Screenshot_2024-04-25_at_17.18.20.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Open the integration options</h4><p>Now click the symbol <code>&lt; &gt;</code> to see the devices you can integrate on, and pick yours.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/cc791c2-Screenshot_2024-04-25_at_17.19.13.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Select your programming language</h4><p>Select the programming language for your device. Here are reference examples. You may want your developer to read this section.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/820a739-image.png" align="center" width="75%" border={true} />


#### cURL

Can be used in any system. Provide the associated `ENDUSER_ID` in your system. Make sure `rf-app` is set to the actual app ID (from Pulse URL).

\[TODO: Dev/PO review — possible issue: the `rf-app` placeholder's last group has 8 characters, while a standard UUID's last group has 12.]

```bash
curl -H 'rf-app: xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxx' \
     -H 'user-id: ENDUSER_ID' \
     'https://conduit.redcurly.com/ping/?type=custom&custom_field_id=fc4ccd34-7876-430b-8b64-65ac7c19a505'
```

**More on the cURL (server-to-server) method**

**Optional headers**, only needed if your account is configured for them:

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Header</td><td>Value</td><td>When to send</td></tr>
  <tr><td><code>user-id-jwt</code></td><td>Signed JSON Web Token (JWT) of the user ID</td><td>Only if your app requires JWT-verified user IDs.</td></tr>
  <tr><td><code>anonymous-user-id</code></td><td>Anonymous visitor ID</td><td>Only for anonymous visitors, on apps that allow anonymous tracking.</td></tr>
</table>

**Query parameters**

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Parameter</td><td>Required</td><td>Value</td><td>Notes</td></tr>
  <tr><td><code>type</code></td><td>Yes</td><td><code>custom</code></td><td>Marks this as a custom event.</td></tr>
  <tr><td><code>custom_field_id</code></td><td>Yes</td><td>The usage tracker's ID</td><td>The tracker being incremented.</td></tr>
  <tr><td><code>device_type</code></td><td>No</td><td>For example, <code>web</code>, <code>ios</code>, or <code>android</code></td><td>Defaults to <code>web</code> if omitted.</td></tr>
</table>

**A few things to know before you integrate:**

- The tracker referenced by `custom_field_id` must already exist as a usage-type tracker (created via **Add New Tracker** in **Settings > Usage Tracking**). Reporting against an ID that isn't configured this way is silently ignored — you won't see an error, but no usage will be recorded.
- An incorrect app ID or tracker ID also won't raise an error — the request still returns `200 OK`, but nothing is recorded. Double-check both values when setting this up.
- Processing happens shortly after the request is accepted, not synchronously in the response — don't expect the usage event to be immediately reflected.
- The app ID can also be supplied as part of the URL path instead of a header, but the header form shown above is recommended for server-to-server integrations.

#### JavaScript

For web or JavaScript clients.

```javascript
RecurlyEngage.customTrack("fc4ccd34-7876-430b-8b64-65ac7c19a505");
```

#### External Web Tracker

For third-party websites. Tutorial: <a href="/docs/user-traits" target="_blank">Usage Tracking → External</a>.

#### HTML

Tracking pixel for emails, web, or JavaScript clients.

```html
<img src="https://conduit.redcurly.com/ping/?type=custom&custom_field_id=fc4ccd34-7876-430b-8b64-65ac7c19a505" />
```

#### Swift

For Apple devices.

```swift
PromotionManager.customTrack("fc4ccd34-7876-430b-8b64-65ac7c19a505")
```

#### Kotlin

For Android devices.

```kotlin
PromotionManager.customTrack("fc4ccd34-7876-430b-8b64-65ac7c19a505")
```

#### Roku

For Roku devices.

```brightscript
m.promoMgr.callFunc("customTrack", { custom_field_id: "fc4ccd34-7876-430b-8b64-65ac7c19a505" })
```

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Add a new segment</h4><p>Go to add a new segment, as shown in the Page example above.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">6</div>
    <div><h4>Find your new trait</h4><p>Under the <span style={{fontWeight: "bold"}}>Usage</span> tab, you can see the newly added Engage trait you can target. Once the custom tracker from step 4 is integrated, users are automatically segmented according to your needs.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/0cdc7c3-image.png" align="center" width="75%" border={true} />


# Tracking web actions from other sites

A common example of tracking external conversions is the need to track links that refer users off-site. In many cases, it's difficult to see whether the user actually converted (for example, signed up or paid) after they land on the partner page. The following method requires you to add your user ID to the URL when you redirect to your partner. The partner site should save the user ID. Then, on completion of the conversion, the partner needs to notify Engage. Here's how to configure it.

## Custom website action

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Create a redirect URL</h4><p>Create a redirect URL using a custom website action that includes an <code>rf_uid</code> parameter:</p></div>
  </div>
</div>

```javascript
// https://example.com?campaign_id=456&rf_uid=123
// rf_uid=123 is the important piece
if (RecurlyEngage.anonymousUserId) {
  return window.location.href = "https://example.com?campaign_id=456&rf_uid=" + RecurlyEngage.anonymousUserId;
} else if (RecurlyEngage.userId) {
  return window.location.href = "https://example.com?campaign_id=456&rf_uid=" + RecurlyEngage.userId;
}
```

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Add a new website action</h4><p>Go to <span style={{fontWeight: "bold"}}>Settings &gt; Actions &gt; Website Actions &gt; Add New Action</span>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/28e316d-Screenshot_2024-04-25_at_15.57.56.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Add the code</h4><p>Add the code from step 1, making sure to change the URL and parameters to your partner URL, but keep <code>rf_uid</code> intact.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/90e6242-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Save your changes</h4><p>Save the changes.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/cda656e-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Open the prompt's website actions</h4><p>Go to the prompt that you want to redirect from and click <span style={{fontWeight: "bold"}}>Website Actions &gt; Add Action</span>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/f86eb59-Screenshot_2024-04-25_at_16.18.56.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">6</div>
    <div><h4>Add the custom website action</h4><p>Add the custom website action to the prompt.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/09e2cab-Screenshot_2024-04-25_at_16.21.49.png" align="center" width="75%" border={true} />


## External custom tracker

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open the tracker form</h4><p>Go to <span style={{fontWeight: "bold"}}>Settings &gt; Usage Tracking &gt; Add New Tracker</span>, as shown in Set up a tracker above.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Add a custom tracker</h4><p>Add a new custom tracker.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/b5a1e44-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Save your changes</h4><p>Click <span style={{fontWeight: "bold"}}>Save Changes</span>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/60b07dd-Screenshot_2024-04-25_at_17.08.08.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Open the code view</h4><p>Click the code icon <code>&lt; &gt;</code>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/b2d3783-Screenshot_2024-04-25_at_17.09.47.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Select External Web Tracker</h4><p>Click <span style={{fontWeight: "bold"}}>External Web Tracker</span>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/435b19a-Screenshot_2024-04-25_at_17.10.47.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">6</div>
    <div><h4>Share the first code block</h4><p>Your partner should add the first code block to their landing page to save the referred user ID (<span style={{fontWeight: "bold"}}>Usage → External</span>).</p></div>
  </div>
</div>


<Image src="https://files.readme.io/f3193d3-Screenshot_2024-04-25_at_17.12.33.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">7</div>
    <div><h4>Share the second code block</h4><p>Your partner should add the second code block to their conversion page to notify Engage of a successful conversion.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/d61c1ac-Screenshot_2024-04-25_at_17.53.16.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">8</div>
    <div><h4>Add the tracker as a custom goal</h4><p>Add the tracker as a Custom Goal to your prompt (no need to wait for steps 6 and 7). This lets you see how your prompt is performing.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/529a107-Screenshot_2024-04-25_at_17.14.04.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">9</div>
    <div><h4>Save the prompt</h4><p>Save the prompt.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/e76c311-image.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">10</div>
    <div><h4>Start the prompt</h4><p>Once your partner has implemented steps 6 and 7, start the prompt to see results.</p></div>
  </div>
</div>

# Using events in Google Tag Manager

In some cases, you can use Google Tag Manager (GTM) events to trigger actions with the Engage SDK. Here's a quick primer.

## GTM setup

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Set up a trigger</h4><p>Set up a new trigger that responds to an event named <code>test</code>.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/830c245-Screenshot_2024-04-29_at_2.51.28_PM.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Associate a tag</h4><p>Associate a tag with the trigger.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/5004849-Screenshot_2024-04-29_at_2.52.26_PM.png" align="center" width="75%" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Publish your changes</h4><p>Publish changes to production.</p></div>
  </div>
</div>

## Testing

To test, send an event via the GTM dataLayer. The contents of the Custom HTML tag will execute:

```javascript
> dataLayer.push({ event: 'test' });

// Test Event for anon user: c7c02a061db6aba3adae5263523005b57a8f90f16cf59d46fe036191213be5dd, user: 123
```
