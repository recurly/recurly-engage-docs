---
title: 'Overview: Segments'
excerpt: >-
  How to create and manage user segments in Recurly Engage for targeted prompt
  delivery.
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
  <div class="rp-overview">Segments group your users by characteristics and behavior so you can target the right audience with prompts and guides. Build a segment from built-in or custom traits, then use it to include or exclude users.</div>
  <div style={{position: "relative", paddingTop: "56.25%", marginBottom: "28px", borderRadius: "10px", overflow: "hidden"}}>
    <iframe src="https://www.loom.com/embed/5e730b455754424fa13f1f282bcaafe6?sid=669292ce-0cd1-4d29-960a-ad13a1aebd5c"
      title="Segments overview"
      allow="autoplay; fullscreen"
      allowtransparency="true"
      frameBorder="0"
      scrolling="no"
      allowFullScreen
      style={{position: "absolute", top: 0, left: 0, width: "100%", height: "100%", border: "none"}}></iframe>
  </div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly Engage subscription plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have <strong>Company</strong> or <strong>App Administrator</strong> permissions in Recurly Engage.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>There's no limit on the number of segments you can create, and users can belong to multiple segments.</li>
</ul>

# Definition

<div class="rp-definition">A segment uses trait filters to include or exclude users based on their characteristics or behaviors. Filters can use built-in usage, device, and location traits, or imported custom <a href="/recurly-engage/docs/user-traits" target="_blank">traits</a>.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-bullseye" aria-hidden="true"></i></div>
    <strong>Precision targeting</strong>
    <span>Reach the right users with contextually relevant messages.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-arrows-rotate" aria-hidden="true"></i></div>
    <strong>Dynamic audiences</strong>
    <span>Automatically update segments based on real-time trait changes.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-database" aria-hidden="true"></i></div>
    <strong>Cross-functional data</strong>
    <span>Use external data through custom trait imports for advanced targeting.</span>
  </div>
</div>

# Key details

## Trait sources

<ul class="rp-list">
  <li><strong>Built-in traits</strong>: Usage metrics (visits, minutes), device type, location, and prompt interactions, tracked automatically. See <a href="/recurly-engage/docs/usage-tracking-1" target="_blank">Usage tracking</a> for the full list of automatically tracked attributes and how to add custom trackers.</li>
  <li><strong>Custom traits</strong>: Import through <a href="https://docs.recurly.com/recurly-engage/docs/user-traits#method-1--csv-upload-to-s3-batch" target="_blank">AWS S3</a> (CSV, ingested within a few hours), direct CSV upload in Pulse, or <a href="https://docs.recurly.com/recurly-engage/docs/user-traits#method-3--ingest-api-real-time" target="_blank">real-time events through the API or SDK</a>.</li>
  <li><strong>Complex collections</strong>: Collections such as a user having multiple active or expired subscriptions. <a href="https://docs.recurly.com/recurly-engage/docs/complex-collections" target="_blank">Learn more about complex collections</a>.</li>
</ul>

## Common segment examples

<ul class="rp-list">
  <li>Monthly plan members with declining visits</li>
  <li>Trial users</li>
  <li>Users with failed payments</li>
</ul>

## Advanced filtering logic

* **Multi-value support**: You can add multiple rows for the same custom trait within a single segment. For example, you can set a filter to include "Renewal Start Date" greater than 30 days AND exclude "Renewal Start Date" greater than 60 days.
* **Within a single "Subscription" collection**: Currently, filters within the subscription object function independently. A user qualifies if they have any subscription matching criterion A and any subscription matching criterion B. They don't necessarily have to be the same subscription.


<Image src="https://files.readme.io/3d0176cb8376d1f61829a3d2bf950e182dac28a7f2651906a5ec6995d624027c-segments.png" align="center" width="75%" border={true} />


## Usage-based segments

Combine segments with <a href="/recurly-engage/docs/usage-tracking-1" target="_blank">Usage tracking</a> to target users based on app behavior:

* Users who have never visited a specific page or content
* Users who clicked a particular button or section

## Create a segment: example

The following example creates a segment of **Engaged, US-based iOS Premium plan users who have not redeemed the iOS prompt**.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Start a new segment</h4><p>Navigate to <span style={{fontWeight: "bold"}}>Segments &gt; New Segment</span>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Name the segment</h4><p>Enter a <span style={{fontWeight: "bold"}}>Name</span> (for example, "Engaged iOS Premium – No Redemption") and an optional <span style={{fontWeight: "bold"}}>Description</span>.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Add trait filters</h4><p>Add the following trait filters in sequence.</p></div>
  </div>
</div>

* **Engaged**: Choose **Usage → Visits** → **Greater than or equal to** → **2** over the last **7 days**.
* **US-based**: Select **Location → Countries** → **Include** → **United States of America**.
* **iOS**: Select **Device → OS** → **iOS**.
* **Premium plan**: Under **Custom** → **Plan** → **Include** → **Premium**.
* **Not redeemed iOS prompt**: Select **Interactions → User has not → accepted (primary) → \[iOS popup]**. Choose your created prompt from the dropdown.
* **Add complex subscription traits**:
  * Select Subscriptions from the trait dropdown.
  * Sub-attribute: Choose a dimension.
  * Match Type: Set your criteria.
  * Note: You can add multiple sub-attributes to further refine the collection.

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>Custom covers any traits you've imported. Learn more about <a href="/recurly-engage/docs/user-traits" target="_blank">importing custom traits</a>.</div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Save the segment</h4><p>Select <span style={{fontWeight: "bold"}}>Save</span> to create the segment.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Enable the segment</h4><p>Toggle <span style={{fontWeight: "bold"}}>Enable</span> to activate the segment and begin real-time monitoring.</p></div>
  </div>
</div>

Recurly Engage starts processing incoming data and populates your segment within a few hours. To monitor the segment's metrics, open its detail view and adjust the date range as needed.

<br />

<br />
