---
title: Adobe
excerpt: >-
  A guide to the Recurly Engage and Adobe integration. It details how to connect
  Adobe Experience Cloud products to Recurly Engage to create a unified data
  layer, enable cross-product orchestration, and enhance analytics.
deprecated: false
hidden: false
metadata:
  title: Adobe AEP AJO
  description: ''
  keywords:
    - Adobe
    - AEP
    - AJO
    - Experience Manager
  robots: index
next:
  description: ''
---
<div class="rp-page">
  <div class="rp-overview">The Adobe connector suite lets you forward Recurly Engage prompt interaction events to Adobe Experience Platform (AEP), trigger in-app prompts through Adobe Journey Optimizer (AJO), and send web events to Adobe Analytics using the Experience Platform Web SDK.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available as an add-on for any Recurly Engage subscription plan</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must have <strong>Company</strong> or <strong>App Administrator</strong> permissions.</li>
  <li>You must have active Adobe Experience Platform, Journey Optimizer, or Analytics licenses.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>Schema and data stream configurations in AEP must be completed before ingestion.</li>
</ul>

# Definition

<div class="rp-definition">The Recurly Engage Adobe integration suite connects Recurly Engage with your Adobe Experience Cloud products, including AEP, AJO, and Adobe Analytics. It lets you build on your existing analytics workflows and unify your data to deliver more targeted, effective in-app experiences.</div>

# Key benefits

<div class="rp-benefits rp-benefits-2x2">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-database" aria-hidden="true"></i></div>
    <strong>Unified data layer</strong>
    <span>Stream real-time prompt interaction events (impressions, clicks, and custom goals) into Adobe's Data Lake through AEP, creating a single, unified view of customer behavior.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-diagram-project" aria-hidden="true"></i></div>
    <strong>Cross-product orchestration</strong>
    <span>Trigger in-app prompts and update user traits in Recurly Engage directly from Adobe Journey Optimizer, enabling automated, personalized customer journeys.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-chart-line" aria-hidden="true"></i></div>
    <strong>Enhanced analytics</strong>
    <span>Capture prompt metrics and analyze them alongside your existing site analytics using the Adobe Experience Platform Web SDK.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-file-import" aria-hidden="true"></i></div>
    <strong>Streamlined onboarding</strong>
    <span>Quickly import and use existing Adobe Audience segments without additional development work, accelerating your time to value.</span>
  </div>
</div>

# Key details

## Connect Adobe Audience segments

The Segment Importer syncs segments from Adobe Audience Manager or AEP directly to Recurly Engage. Recurly Engage treats these imported segments as user traits, which you can use to create or refine Recurly Engage segments. It's a fast, code-free way for customers who use our JavaScript SDK to use their existing Adobe audience data for targeted messaging.

### How it works

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Sync your segments</h4><p>Sync your Adobe Audience segments to Recurly Engage using the Segment Importer.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Review the imported traits</h4><p>The imported segments appear as user traits on your customers' profiles in Recurly Engage.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Build new segments</h4><p>Use these traits to build new Recurly Engage segments, so you can refine and personalize your campaigns further.</p></div>
  </div>
</div>

## Adobe Experience Platform (AEP)

The Recurly Engage AEP connector pushes prompt interaction events (impression, goal, decline, dismiss, timeout, `custom_goal`, and holdout) to an <a href="https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/overview" target="_blank">Adobe Data Stream</a> in real time.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Create an Identity Map</h4><p>Create or reuse an <a href="https://experienceleague.adobe.com/en/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/map-identities" target="_blank">Identity Map</a> in AEP.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Add the schema fields</h4><p>Enable the <span style={{fontWeight: "bold"}}>Profile</span> toggle and add a <a href="https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/resources/field-groups" target="_blank">Field Group</a> to your schema with the traits listed below.</p></div>
  </div>
</div>

1. `activity` (String) — Event type (for example, "impression").
2. `app_id` (String) — Recurly Engage instance ID.
3. `app_name` (String) — Recurly Engage instance name.
4. `event_timestamp` (DateTime) — When the event occurred.
5. `promo_id`, `promo_name` — Prompt identifiers.
6. `variation_id`, `variation_name` — Experiment variation identifiers.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Attach the schema to a Data Stream and Dataset</h4><p>Attach the schema to your Data Stream and create a <a href="https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/overview" target="_blank">Dataset</a> from the same schema, making sure the <span style={{fontWeight: "bold"}}>Profile</span> toggle is enabled.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Configure Recurly Engage</h4><p>In Recurly Engage, navigate to <span style={{fontWeight: "bold"}}>Settings → Integrations → External → Adobe</span> and enter the values listed below.</p></div>
  </div>
</div>

1. Identity Map Symbol
2. <a href="https://github.com/adobe/xdm/blob/master/docs/reference/classes/experienceevent.schema.md#xdmeventtype-known-values" target="_blank">Event Type</a> (for example, `xdm:eventType`)
3. Adobe Instance Name
4. Data Stream ID


<Image src="https://files.readme.io/6fb869da2965a8f79d20ef00ec618c6537524de444351e992c8df3bcd0fbbe46-Screenshot_2025-03-06_at_9.56.33_AM.png" align="center" width="75%" border={true} />


## Adobe Journey Optimizer (AJO)

Use AJO Custom HTTP Actions to call Recurly Engage endpoints directly from customer journeys, so you can update user traits or trigger in-app prompts based on journey logic.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Create a Custom HTTP Action</h4><p>In AJO, navigate to <span style={{fontWeight: "bold"}}>Actions</span> and create a new Custom HTTP Action.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Name the action</h4><p>Enter a name and description for the action.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Configure the endpoint</h4><p>Under <span style={{fontWeight: "bold"}}>Endpoint Configuration</span>, set the HTTP Method to <code>GET</code> and enter your Recurly Engage API endpoint.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Configure query parameters</h4><p>Configure <span style={{fontWeight: "bold"}}>Query Params</span> using the <code>properties[&lt;keyName&gt;]=&lt;value&gt;</code> format.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Add the header</h4><p>Add the <code>USER-ID</code> HTTP header.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">6</div>
    <div><h4>Test and deploy</h4><p>Test the action with your Customer Success Manager, and then deploy it within your AJO journey.</p></div>
  </div>
</div>

## Adobe Analytics

Using the Adobe Experience Platform Web SDK (`alloy.js`), you can forward Recurly Engage prompt interaction events directly to Adobe Analytics on your web properties. This lets you analyze prompt metrics alongside your site analytics in a single location.

To get started:

* Contact your Recurly Engage Customer Success Manager or <a href="mailto:support@recurly.com">[support@recurly.com](mailto:support@recurly.com)</a> to enable Web SDK configuration for your account.
* Your Customer Success Manager helps make sure events map correctly to your Adobe Analytics data streams.
