---
title: Adobe
excerpt: >-
  How to integrate Recurly Engage with Adobe Experience Platform, Journey
  Optimizer, and Analytics for event streaming and in-app triggers.
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
# Overview

The **Adobe** connector suite lets you forward Recurly Engage prompt interactions to Adobe Experience Platform (AEP), trigger in-app prompts via Adobe Journey Optimizer (AJO), and send web events to Adobe Analytics using the Experience Platform Web SDK.

### Required plan

This feature is an add on and can be purchased for any Recurly Engage subscription plan.

export const PrerequisitesLimitations = ({ header }) => {
  return (
    <div className="flex justify-start">
      <div className="rounded-md p-6 m-4 max-w-lg shadow-md border border-gray-300 dark:bg-gray-800 dark:border-gray-600">
        <p className="text-lg font-bold">{header}</p>
        <p>
          <i className="fa-solid fa-check mr-2" />
          <strong>Company</strong> or <strong>App Administrator</strong> permissions.
        </p>
        <p>
          <i className="fa-solid fa-check mr-2" />
          Active Adobe Experience Platform, Journey Optimizer, or Analytics licenses.
        </p>
        <p>
          <i className="fa-solid fa-exclamation-triangle mr-4" />
          Schema and data stream configurations in AEP must be completed prior to ingestion.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

**Adobe integrations** enable bidirectional data flows: prompt events (impressions, clicks, custom goals) stream into AEP; AJO can call Recurly Engage APIs to trigger in-app prompts; and web events can be vaulted into Adobe Analytics.

# Key benefits

* **Unified data layer**: Stream prompt interaction events into Adobe’s Data Lake in real time.
* **Cross-product orchestration**: Use AJO journeys to trigger in-app messaging via Recurly Engage.
* **Web analytics**: Capture prompt metrics alongside site analytics using the Experience Platform Web SDK.

# Key details

## Adobe experience platform (AEP)

The **Recurly Engage AEP connector** pushes prompt interaction events—`impression`, `goal`, `decline`, `dismiss`, `timeout`, `custom_goal`, and `holdout`—to an Adobe [Data Stream](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/overview).

**Configure these objects in AEP:**

* **Identity Map**: Create or reuse an [Identity Map](https://experienceleague.adobe.com/en/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/map-identities).
* **Schema**: Enable **Profile** toggle and add traits in a [Field Group](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/resources/field-groups):

  * `activity` (String) — event type, e.g. "impression"
  * `app_id` (String) — Recurly Engage instance ID
  * `app_name` (String) — instance name
  * `event_timestamp` (DateTime) — when the event occurred
  * `promo_id`, `promo_name` — prompt identifiers
  * `variation_id`, `variation_name` — experiment variation identifiers (if applicable)
* **Data Stream**: Attach the schema to your data stream.
* **Dataset**: Create a [Dataset](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/overview) from the same schema and enable the **Profile** toggle.

**In Recurly Engage:** Navigate to **Settings → Integrations → External → Adobe** and enter:

* **Identity Map Symbol**
* **Event Type** (use known [xdm:eventType](https://github.com/adobe/xdm/blob/master/docs/reference/classes/experienceevent.schema.md#xdmeventtype-known-values))
* **Adobe Instance Name** (e.g., `_production`, visible in schema details)
* **Data Stream ID**

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/6fb869da2965a8f79d20ef00ec618c6537524de444351e992c8df3bcd0fbbe46-Screenshot_2025-03-06_at_9.56.33_AM.png" />

## Adobe journey optimizer (AJO)

Use AJO **Custom HTTP Actions** to call Recurly Engage endpoints from within customer journeys, updating user traits or triggering in-app prompts.

1. In AJO, navigate to **Actions → Create Action**, choose **Custom HTTP Action**.
2. Enter **Name** and **Description**.
3. Under **Endpoint Configuration**:

   * Set **HTTP Method** to **GET**.
   * Enter your Recurly Engage API endpoint.
   * Configure **Query Params** using `properties[<keyName>]=<value>`.
   * Add the `USER-ID` HTTP header.
4. **Test** the action with your Customer Success Manager.
5. **Save** and **Deploy** the action in your journey.

Once live, AJO will send requests to Recurly Engage, syncing properties and enabling prompt triggering based on journey logic.

***

## Adobe analytics

Leverage the Experience Platform Web SDK (`alloy.js`) to forward prompt interaction events to Adobe Analytics on your web properties.

Contact your Customer Success Manager to enable Web SDK configuration and ensure events map to your Analytics data streams.