---
title: Adobe Analytics
excerpt: >-
  Integration guide for sending Recurly Engage prompt events to Adobe Analytics
  using the Experience Platform Web SDK (Alloy.js).
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

The **Adobe Analytics** connector uses the existing Alloy.js instance on your site to report prompt interaction events—impressions, clicks, dismissals—in the same session context as page analytics.

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

export const PrerequisitesLimitations = ({ header }) => {
  return (
    <div className="flex justify-start">
      <div className="rounded-md p-6 m-4 max-w-lg shadow-md border border-gray-300 dark:bg-gray-800 dark:border-gray-600">
        <p className="text-lg font-bold">{header}</p>
        <p>
          <i className="fa-solid fa-check mr-2" />
          <strong>Company</strong> or <strong>App Administrator</strong> permissions in Recurly Engage.
        </p>
        <p>
          <i className="fa-solid fa-check mr-2" />
          An Adobe Experience Platform Web SDK (<a className="text-blue-500! dark:text-blue-300!" href="https://github.com/adobe/alloy?tab=readme-ov-file" target="_blank">Alloy.js</a>) setup on your web property.
        </p>
        <p>
          <i className="fa-solid fa-check mr-2" />
          Access to <strong>Recurly Engage → Settings → Integrations → External → Adobe Analytics</strong>.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

The **Adobe Analytics** integration fires custom events for Recurly Engage prompt interactions directly through Alloy.js, preserving user and session data in your Adobe Analytics reports.

# Key benefits

* **Consistent session data**: Events emit using the same Alloy session context as your other Analytics events.
* **Built-in tracking**: No additional SDKs required—leverages your existing Alloy.js configuration.
* **Full interaction visibility**: Capture all prompt lifecycle events in Adobe Analytics.

# Key details

**Event Details**

| Activity                         | Description                                                                            |
| -------------------------------- | -------------------------------------------------------------------------------------- |
| Recurly Engage Prompt Impression | A user has seen the prompt                                                             |
| Recurly Engage Prompt Dismiss    | A user has dismissed the prompt by clicking the ‘X’ or outside the prompt (if enabled) |
| Recurly Engage Prompt Timeout    | The prompt has closed automatically due to a timer                                     |
| Recurly Engage Prompt Decline    | A user has declined the prompt by clicking the decline button                          |
| Recurly Engage Prompt Click      | A user has accepted the prompt via the primary CTA button                              |
| Recurly Engage Prompt Holdout    | A holdout user has been served the prompt but not exposed                              |
| Recurly Engage Prompt Click 2    | A user has accepted the prompt via the secondary CTA button                            |

Each event includes these attributes when available:

| Event Property    | Description                                                       |
| ----------------- | ----------------------------------------------------------------- |
| `promo_id`        | Unique prompt identifier (from the Prompt ID field under Details) |
| `promo_name`      | The name of the prompt                                            |
| `variation_id`    | Identifier of the experiment variation (if any)                   |
| `variation_name`  | Name of the experiment variation (if any)                         |
| `event_timestamp` | Timestamp of when the interaction occurred                        |

## Setup

1. In Adobe Experience Platform, create or select a **Data Stream**. Ensure you have an associated schema, report suite, and field group configured to accept custom event fields.
2. In **Recurly Engage**, navigate to **Settings → Integrations → External → Adobe Analytics**.
3. Enter your **Data Stream ID** and **Adobe Org ID** (see [Org ID docs](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/orgid)).
4. Save your integration settings. Prompt events will now be sent via Alloy.js to Adobe Analytics under your Data Stream.