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
  <div class="rp-overview">Recurly Engage user traits let you import and define custom attributes — such as lifetime value, satisfaction score, or subscription dates — so you can target users on more than built-in behavior metrics. You can bring these traits in as a scheduled CSV batch, through a partner integration, or in real time by calling the Ingest API directly. Once a trait lands in Engage, it's available for segmentation and personalized prompts.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> This feature or setting is available to all customers on any Recurly Engage subscription plan</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
    <a class="rp-toc-pill" href="#choosing-an-ingest-method"><span class="rp-toc-num">4</span>Choosing an ingest method</a>
    <a class="rp-toc-pill" href="#customizing-user-traits"><span class="rp-toc-num">5</span>Customizing user traits</a>
    <a class="rp-toc-pill" href="#common-issues--how-to-resolve-them"><span class="rp-toc-num">6</span>Common issues &amp; how to resolve them</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have <strong>Company</strong> or <strong>App Administrator</strong> permissions in Recurly Engage.</li>
  <li>For CSV ingest: access to your Engage S3 bucket or a CSV export source.</li>
  <li>For real‑time ingest via the Ingest API: your App ID and API Key (<strong>Settings &gt; Application &gt; API Key</strong>).</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>For third‑party connector activation, ensure required ID columns are present.</li>
  <li>CSV uploads to S3 are ingested within a few hours — for real‑time updates, use the Ingest API.</li>
</ul>

# Definition

<div class="rp-definition"><strong>User traits</strong> are custom attributes imported into Recurly Engage that extend targeting beyond built-in usage metrics. You can ingest them three ways: a scheduled CSV upload to a secure S3 bucket, a partner integration, or a direct call to the Ingest API for real-time updates.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-bullseye" aria-hidden="true"></i></div>
    <strong>Richer personalization</strong>
    <span>Leverage lifetime value, plan type, NPS, or any business metric in your prompts.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-bolt" aria-hidden="true"></i></div>
    <strong>Ingest at the speed you need</strong>
    <span>Batch data through CSV, or push it in real time through the Ingest API when freshness matters.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-plug" aria-hidden="true"></i></div>
    <strong>Flexible integrations</strong>
    <span>Activate push notifications and connector‑based traits for services like Stripe, Salesforce, SendGrid, and Zendesk.</span>
  </div>
</div>

# Key details

<ul class="rp-list">
  <li><strong>CSV format</strong>: First column must be <code>user_id</code>, additional columns become traits.</li>
  <li><strong>Trait types</strong>: Number, string, boolean, date with corresponding display options (slider, multi‑select, date range).</li>
  <li><strong>Push endpoints</strong>: Import device tokens via CSV or Device Registration API.</li>
  <li><strong>3rd‑party requirements</strong>: Specific ID or email columns needed for connectors (e.g., <code>stripe_id</code>, <code>email_address</code>).</li>
</ul>

You can import additional user traits into Recurly Engage to give you greater ability to target users based on characteristics beyond site/app usage. Typical examples are lifetime value, customer satisfaction score, subscription start date, renewal date etc. User traits can be added via a CSV file. This file will be stored, encrypted, on a secured S3 bucket and will be ingested within a few hours of uploading. Each column will be mapped into a Recurly Engage user trait.

You can also export your CSV data from [Looker](looker).

# Choosing an ingest method

Recurly Engage supports three ways to get custom trait data in. Pick the one that matches how fresh your data needs to be and where it lives.

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Method</td><td>Latency</td><td>Best for</td></tr>
  <tr><td>CSV upload to S3</td><td>Within a few hours</td><td>Bulk or historical loads, scheduled exports</td></tr>
  <tr><td>Partner integration</td><td>Varies by partner</td><td>Data already flowing through a supported connector</td></tr>
  <tr><td>Ingest API</td><td>Real time</td><td>Custom data from your own backend or database</td></tr>
  <tr><td>Custom JS Snippet<br /><br /><code>fetchUserTraits()</code></td><td>Real time</td><td>Trait data already available client-side (cookies, localStorage, a data layer) that you want to sync without calling the Ingest API from your backend</td></tr>
</table>

## Method 1 — CSV upload to S3 (batch)

You can import user traits into Recurly Engage to target users on characteristics beyond site or app usage. Typical examples are lifetime value, customer satisfaction score, subscription start date, and renewal date. User traits can be added via a CSV file. This file is stored, encrypted, on a secured S3 bucket and is ingested within a few hours of uploading. Each column is mapped into a Recurly Engage user trait.

You can also export your CSV data from Looker.

### One-off uploads

If you need to load a small, one-time batch of trait data — for example, an exclusion list or a short-term partner list — you can upload a CSV directly in Pulse instead of dropping a file to your S3 bucket:

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><p>In Pulse, use the CSV upload option in <strong>Settings &gt; User Traits</strong>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><p>Check <strong>App Messages</strong> in Pulse to track the file's status.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><p>Once the status shows successful, your new trait keys will appear in the User Traits list, ready to configure.</p></div>
  </div>
</div>

This method mimics the same processing your S3 uploads go through, just triggered manually rather than automatically. It's best suited for small, one-time uploads — for ongoing or recurring trait syncs, use the S3 method above.

### Formatting the CSV file

Here is an example of what your CSV file should look like. **The first column must be**`user_id`, all other columns can be utilized to specify user traits. There are no limits on columns but please keep in mind this can significantly impact load and sync times.

```csv
user_id,ltv,channel,signup_date,nps,plan_type,payment_failed
789129,150,adwords,2011-08-12,8,monthly,false
322321,0,blog,2014-09-18,7,trial,false
900194,100,homepage,2018-04-01,9,annual,true
```

<ul class="rp-list">
  <li><strong>Trait key casing is case-sensitive.</strong> If you change the casing of a column header between uploads (for example, <code>LTV</code> vs. <code>ltv</code>), Engage treats it as a brand-new trait rather than an update to the existing one — this creates duplicate traits and inconsistent data. Keep column header casing identical across every file you upload.</li>
  <li><strong>Trait keys must use underscores, not spaces.</strong> A column header containing a space (e.g. <code>signup date</code>) will not be processed. Use <code>signup_date</code> instead.</li>
  <li><strong>Only include traits you actually plan to use for segmentation.</strong> Every additional column increases file size and processing time. If you upload traits you don't intend to use, you'll still need to configure each one (see "Customizing user traits" above) before they're usable.</li>
  <li><strong>Do not include personally identifiable information (PII)</strong> in trait columns.</li>
</ul>

### Required columns for third party connectors

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>To activate third‑party connectors like Stripe, Salesforce, and others the following columns are required:</div>
</div>

<ul class="rp-list">
  <li><strong>Salesforce</strong>: <code>salesforce_id</code> (the id of the Salesforce contact) OR <code>email_address</code></li>
  <li><strong>SendGrid</strong>: <code>email_address</code></li>
  <li><strong>Stripe</strong>: <code>stripe_id</code> (the id of the Stripe customer) OR <code>email_address</code></li>
  <li><strong>Zendesk</strong>: <code>zendesk_id</code> (the id of the Zendesk user) OR <code>email_address</code></li>
</ul>

### Push notifications

To activate push notifications, the following columns are required:

1. `Id`: the id of the device (aka endpoint)
2. `ChannelType`: the push channel of this endpoint. Allowed values: `FCM`, `ADM`, `APNS`
3. `Address`: The device token
4. `User.UserId`: the id of the user. This should be the same id that Recurly Engage uses

This CSV can be used as a one‑time initial load of endpoint information. To keep this information updated, you may:

1. Upload an updated CSV periodically into your S3 bucket from Recurly Engage OR
2. Call the [Device Registration](ref:device-registration) API with the device token from your client application

### Upload the file to AWS

After creating your CSV file you will need to upload it to your secure area on Amazon S3. In this step we will retrieve the credentials to allow you to upload the file.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><p>Go to <strong>Settings &gt; User Traits</strong></p></div>
  </div>
</div>


<Image src="https://files.readme.io/da8ce5e-image.png" align="center" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><p>Select "Click here for AWS S3 credentials"</p></div>
  </div>
</div>


<Image src="https://files.readme.io/679abbc-image.png" align="center" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><p>Check the <strong>Show Credentials</strong> box to view your credentials. You will need to use the AWS Bucket, Access Key and Secret Key to login and securely upload via AWS. Keep this information handy, you will need it to upload the CSV.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><p>If you are automating a file transmission to the S3 bucket, use the above credentials with the AWS SDK or CLI (<a href="https://aws.amazon.com/cli/">link</a>). Otherwise, the following steps describe how to manually upload a CSV file.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><p>Download <a href="https://cyberduck.io/download/">Cyberduck</a>. Cyberduck is a client that you can connect to AWS with. Otherwise the next steps describe how to use a free S3 client to upload the CSV file.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">6</div>
    <div><p>Click the plus sign to add a new connection</p></div>
  </div>
</div>


<Image src="https://files.readme.io/fc1bd26-image.png" align="center" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">7</div>
    <div><p>Select <strong>Amazon S3</strong> from the dropdown list</p></div>
  </div>
</div>


<Image src="https://files.readme.io/193d845-image.png" align="center" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">8</div>
    <div><p>Type in your credentials. Then click <strong>More Options</strong> and type in your AWS Bucket in the <strong>Path</strong> field with the "/" in front of it (see the screenshot for reference)</p></div>
  </div>
</div>


<Image src="https://files.readme.io/5a75d55-image.png" align="center" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">9</div>
    <div><p>Locate <strong>Upload Location</strong> which gives you the location where you should put your CSV.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/db565a6-image.png" align="center" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">10</div>
    <div><p>Drag and drop your CSV file to the <strong>ingest</strong> folder, using the information from above. Within 3 hours your data will be fully ingested. You should receive an email once you're done.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/5319ecd-image.png" align="center" border={true} />

## Method 2 — Partner integrations

If your data already lives in a supported tool — such as Segment, Stripe, Braze, or Salesforce — you can sync traits by connecting that tool directly, without preparing and uploading a CSV yourself. Set the integration up in Pulse (Engage Backend) and trait updates propagate into Engage on their own. Latency depends on the partner; for example, Segment traits typically appear within minutes. See CRM integrations for the full list and setup steps.

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>This is different from the connector column requirements under Method 1. Use Method 1 when you're uploading a CSV that feeds a connector; use this method when the connector syncs to Engage on its own.</div>
</div>

## Method 3 — Ingest API (real time)

When your data lives in your own backend or internal database — or you simply need updates faster than the batch cycle allows — call the Ingest API directly. There's no S3 upload and no batch wait; traits are available as soon as the call succeeds.

<ul class="rp-list">
  <li><strong>Endpoint:</strong> POST <a href="https://conduit.redfast.com/ingest/property">https://conduit.redfast.com/ingest/property</a></li>
  <li><strong>Authentication:</strong> Basic Auth with your Application ID and API Key. Depending on your client, the API Key may be passed as a query-string parameter. Find your API Key at Settings &gt; Application &gt; API Key.</li>
</ul>

<strong>Payload:</strong>

```json
{
  "id": "123-456-789-012",
  "user_id": "test-user-001",
  "properties": {
    "first_name": "Jane",
    "plan": "premium"
  }
}
```

<strong>Example response</strong>

```json
{
  "success": true
}
```

Each key in properties maps to a Recurly Engage user trait. As with CSV ingest, you'll configure the type and display for each new trait before using it in a segment (see Customizing user traits).

### Error responses

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Status</td><td>Message</td><td>Cause</td></tr>
  <tr><td>422</td><td><code>app_not_found</code></td><td>Your app ID didn't resolve to a valid app.</td></tr>
  <tr><td>422</td><td><code>user_id_not_found</code></td><td>No user ID was provided in the request.</td></tr>
  <tr><td>401</td><td><code>invalid_credentials</code></td><td>Authentication is required for your account but was missing or invalid.</td></tr>
  <tr><td>401</td><td><code>not_authorized</code></td><td>Real-time ingest isn't enabled for your app yet — contact Recurly support.</td></tr>
</table>

<strong>A few behaviors worth knowing:</strong>

<ul class="rp-list">
  <li>You don't need to include <code>user_id</code> inside the <code>properties</code> object — it's automatically attached to the trait set from the user ID you provide in the request.</li>
  <li>Sending the exact same trait values for the same user repeatedly is treated as a no-op — it won't cause an error, but it also won't re-trigger any downstream processing. Only send a trait update when a value has actually changed.</li>
  <li>Depending on your account's configuration, certain trait keys may be filtered out automatically. If a trait you're sending isn't showing up, contact Recurly support to check your configuration.</li>
  <li>As with other ingest methods, this is processed asynchronously — a successful response confirms the request was accepted, not that it's finished processing.</li>
</ul>

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>This section covers custom attribute (property) data. To send event or behavioral signals — for example, "payment failed" or "user hit a milestone" — see Usage tracking.</div>
</div>

## Method 4 — Live ingest via Custom JS Snippet

If your trait data already lives on the client — in cookies, localStorage, a data layer, or reachable through a call to your own backend — you can push it into Recurly Engage on every page load by implementing a `fetchUserTraits()` function in your Custom JS Snippet. This works alongside the `fetchUserId()` and `fetchAnonUserId()` functions described in <a href="/recurly-engage/docs/custom-js-snippet" target="_blank">Custom JS snippet</a>.

`fetchUserTraits()` returns an object whose keys map to Recurly Engage user traits — the same shape as the properties object in the Ingest API payload.

```text
static fetchUserTraits() {
  const user = JSON.parse(localStorage.getItem("user_object"));
  return {
    is_registered: !!user.token,
    member_since: user.registrationDate,
    accepted_tos: localStorage.getItem("tos_acceptance_date")
  };
}
```

<div class="rp-callout rp-callout-note"> <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>Traits ingested this way still need to be configured (type, display, and an optional description) under Customizing user traits before you can use them in a segment.</div> </div>

# Customizing user traits

After a trait is ingested — whether by CSV, a partner integration, or the Ingest API — you'll need to configure it before you can use it in your segments.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><p>Go to <strong>Settings &gt; User Traits</strong>, you should now see all imported columns</p></div>
  </div>
</div>


<Image src="https://files.readme.io/1fe2677-image.png" align="center" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><p>Now go through each trait to update the type, display and description (optional) by clicking on the <strong>Edit</strong> (pencil) icon</p></div>
  </div>
</div>


<Image src="https://files.readme.io/669873a-image.png" align="center" border={true} />



<Image src="https://files.readme.io/56498d9-image.png" align="center" border={true} />


This may seem intimidating at first but let's take a look at the original CSV to see what the values should be:

```csv
user_id,ltv,channel,signup_date,nps,plan_type,payment_failed
789129,150,adwords,2011-08-12,8,monthly,false
322321,0,blog,2014-09-18,7,trial,false
900194,100,homepage,2018-04-01,9,annual,true
```

- **ltv** – number
- **channel** – string
- **signup_date** – date
- **nps** – number
- **plan_type** – string
- **payment_failed** – boolean

Now that we know the types, selecting the display is easy. Here are some guidelines for display options:

- **numbers** – slider (unless it refers to an ID such as `zendesk_id`, then multi‑select)
- **string** – multi‑select
- **boolean** – multi‑select
- **date** – date_range


<Image src="https://files.readme.io/e418514-image.png" align="center" border={true} />


<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>For the slider display type there is a <strong>Normalize to 0–10</strong> checkbox. You can check this box and it will allow you to target percentiles rather than the exact number (e.g. top 20% LTV users).</div>
</div>


<Image src="https://files.readme.io/b56371d-image.png" align="center" border={true} />


<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><p>Now when you create or edit a segment you can filter based on these user traits.</p></div>
  </div>
</div>


<Image src="https://files.readme.io/0cc29c7-image.png" align="center" border={true} />

## Common issues & how to resolve them

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Issue</td><td>What's happening</td><td>How to resolve</td></tr>
  <tr><td>A trait key has a space in it</td><td>The column isn't processed at all.</td><td>Rename the column header to use underscores instead of spaces, and re-upload.</td></tr>
  <tr><td>Trait key casing changed between uploads</td><td>Engage creates a new, separate trait rather than updating the existing one, leading to inconsistent data.</td><td>Keep column header casing identical across every file. If duplicates already exist, contact support to help consolidate them.</td></tr>
  <tr><td>A newly created coupon isn't showing up in the segment builder</td><td>No user with that coupon has synced to Engage yet — coupons only appear once at least one user carries that value.</td><td>Wait for the first user with that coupon to sync, or manually add the value to the trait in <strong>Settings &gt; User Traits</strong> to pre-build your segment (see note below).</td></tr>
  <tr><td>A segment built on a manually-added trait value has no matching users</td><td>The manually-entered value doesn't exactly match the value that eventually syncs from your data (for example, a typo or different capitalization).</td><td>Double check the manually-entered value against the actual synced value once data arrives, and correct if needed.</td></tr>
  <tr><td>A file isn't processing</td><td>This can happen for a few reasons — an incorrectly formatted file, or ingestion validation paused on your account.</td><td>Check <strong>App Messages</strong> in Pulse for an error status. If the file looks correctly formatted and there's no clear error, contact Recurly support.</td></tr>
  <tr><td>Processing is slower than expected</td><td>Large files, or a high volume of merchants syncing at once, can add processing time.</td><td>Where possible, sync only changed records ("delta" files) after your initial historical load, rather than re-sending your full dataset every time.</td></tr>
  <tr><td>A very large initial file is taking a long time to process</td><td>A large one-time historical load can take substantially longer than routine daily syncs.</td><td>Expect longer processing on your first sync. Switch to delta files (changed records only) for all syncs after the initial load.</td></tr>
</table>

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note on pre-seeding trait values</strong>You can manually add a trait value in <strong>Settings &gt; User Traits</strong> before any user has actually synced with that value — useful for building a segment ahead of time. Just make sure the value you enter exactly matches what will eventually sync; a mismatch means no users will be assigned to that segment until it's corrected.</div>
</div>
