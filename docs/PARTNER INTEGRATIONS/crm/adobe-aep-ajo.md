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

The Recurly Engage Adobe integration suite enables seamless data flow and enhanced marketing orchestration between Recurly Engage and your Adobe Experience Cloud products, including Adobe Experience Platform (AEP), Journey Optimizer (AJO), and Analytics. This integration allows you to leverage existing analytics workflows and unify your data to deliver more targeted and effective in-app experiences.

# Key benefits

* **Unified data layer**: Stream real-time prompt interaction events (impressions, clicks, custom goals) into Adobe’s Data Lake via AEP, creating a single, unified view of customer behavior.
* **Cross-product orchestration**: Trigger in-app prompts and update user traits in Recurly Engage directly from Adobe Journey Optimizer, enabling a powerful, automated, and personalized customer journey.
* **Enhanced analytics**: Capture prompt metrics and analyze them alongside your existing site analytics using the Adobe Experience Platform Web SDK.
* **Streamlined onboarding:** Quickly import and utilize existing Adobe Audience segments without additional development work, accelerating your time-to-value.

# Key details

## Connecting Adobe Audience Segments

The Segment Importer allows you to sync segments from Adobe Audience Manager or AEP directly to Recurly Engage. These imported segments are treated as user traits, which can then be used to create or refine Recurly Engage segments. This provides a fast, code-free way for customers using our JavaScript SDK to leverage their existing Adobe audience data for targeted messaging.

### How it works

1. Sync your Adobe Audience segments to Recurly Engage via the Segment Importer.
2. The imported segments appear as user traits on your customers' profiles within Recurly Engage.
3. Use these traits to build new Recurly Engage segments, allowing for further refinement and personalization of your campaigns.

### Adobe Experience Platform (AEP)

The Recurly Engage AEP connector pushes prompt interaction events—including impression, goal, decline, dismiss, timeout, custom_goal, and holdout—to an <a href="https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/overview">Adobe Data Stream</a> in real time.

#### Configuration steps

1. **Identity Map**: Create or reuse an <a href="https://experienceleague.adobe.com/en/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/map-identities">Identity Map</a> in AEP.
2. **Schema:**:Enable the Profile toggle and add a <a href="https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/resources/field-groups">Field Group</a> to your schema with the following traits:
   1. `activity` (String) — Event type (e.g., "impression").
   2. `app_id` (String) — Recurly Engage instance ID.
   3. `app_name` (String) — Recurly Engage instance name.
   4. `event_timestamp` (DateTime) — When the event occurred.
   5. `promo_id`, `promo_name` — Prompt identifiers.
   6. `variation_id`, `variation_name` — Experiment variation identifiers.
3. **Data Stream & Dataset:** Attach the schema to your Data Stream and create a <a href="https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/overview">Dataset</a> from the same schema, ensuring the Profile toggle is enabled.
4. **Recurly Engage Configuration:** In Recurly Engage, navigate to Settings → Integrations → External → Adobe and enter your:
   1. Identity Map Symbol
   2. <a href="https://github.com/adobe/xdm/blob/master/docs/reference/classes/experienceevent.schema.md#xdmeventtype-known-values">Event Type</a> (e.g., xdm:eventType)
   3. Adobe Instance Name
   4. Data Stream ID

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/6fb869da2965a8f79d20ef00ec618c6537524de444351e992c8df3bcd0fbbe46-Screenshot_2025-03-06_at_9.56.33_AM.png" />

### Adobe journey optimizer (AJO)

Use AJO Custom HTTP Actions to call Recurly Engage endpoints directly from within customer journeys, enabling you to update user traits or trigger in-app prompts based on journey logic.

#### Configuration steps

1. In AJO, navigate to Actions and create a new Custom HTTP Action.
2. Enter a name and description for the action.
3. Under Endpoint Configuration, set the HTTP Method to `GET` and enter your Recurly Engage API endpoint.
4. Configure Query Params using the `properties[<keyName>]=<value>` format.
5. Add the `USER-ID` HTTP header.
6. Test the action with your Customer Success Manager and then deploy it within your AJO journey.

<br />

### Adobe analytics

By leveraging the Adobe Experience Platform Web SDK (alloy.js), you can forward Recurly Engage prompt interaction events directly to Adobe Analytics on your web properties. This allows you to analyze prompt metrics alongside your site analytics in a single location.

#### How it works

* Contact your Recurly Engage Customer Success Manager to enable Web SDK configuration for your account.
* Your Customer Success Manager will assist in ensuring that events map correctly to your Adobe Analytics data streams.
