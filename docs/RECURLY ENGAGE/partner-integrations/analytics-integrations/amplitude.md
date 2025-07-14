---
title: Amplitude
excerpt: >-
  Integration guide for sending Recurly Engage prompt events to Amplitude and
  syncing user data via CSV, Webhooks, or Export API.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

The **Amplitude** integration streams Recurly Engage prompt interactions—impressions, clicks, dismissals, timeouts—into your Amplitude analytics instance using the existing Amplitude JS SDK, and supports inbound user and event data syncs.

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

### Prerequisites & limitations

* Company or App Administrator permissions in Recurly Engage.
* An Amplitude account with project API Key and access to SDK or Export API.
* For outbound events, ensure the Amplitude JS SDK is initialized on your site.

# Definition

The **Amplitude** connector provides:

* **Outbound Events**: Leverage the running Amplitude JS SDK to fire prompt events in-session.
* **Inbound Data Sync**: Import historical events and user traits via CSV uploads, Webhooks, or scheduled Export API jobs.

# Key benefits

* **Seamless event tracking**: Capture prompt interactions in the same session context as your other Amplitude events.
* **Flexible data import**: Choose CSV, Webhooks, or Export API based on your data flow needs.
* **Unified analytics**: Analyze prompt performance alongside full user behavior in Amplitude.

# Key details

## Outbound Events

For web-based devices, Recurly Engage uses the existing Amplitude JS SDK instance to emit events. Contact your Customer Success Manager to confirm your SDK configuration and enable the integration.

1. In **Recurly Engage**, navigate to **Settings → Integrations → External → Amplitude**.
2. Enter your Amplitude **Project API Key** (see [Amplitude authentication](https://amplitude.com/docs/apis/authentication)).

**Event Details**

| Activity                         | Description                                                               |
| -------------------------------- | ------------------------------------------------------------------------- |
| Recurly Engage Prompt Impression | A user has seen the prompt                                                |
| Recurly Engage Prompt Dismiss    | A user has dismissed the prompt by clicking close or outside (if enabled) |
| Recurly Engage Prompt Timeout    | The prompt closed automatically due to a timer                            |
| Recurly Engage Prompt Decline    | A user declined the prompt by clicking the decline button                 |
| Recurly Engage Prompt Click      | A user accepted the prompt via the primary CTA                            |
| Recurly Engage Prompt Holdout    | A holdout user reached the prompt without exposure                        |
| Recurly Engage Prompt Click 2    | A user accepted via the secondary CTA                                     |

Attributes sent with each event:

| Property          | Description                              |
| ----------------- | ---------------------------------------- |
| `promo_id`        | Unique prompt identifier (from Details)  |
| `promo_name`      | Prompt name                              |
| `variation_id`    | Experiment variation identifier (if any) |
| `variation_name`  | Variation name                           |
| `event_timestamp` | When the event occurred                  |

***

## Inbound data sync

Depending on your use cases, import user or event data into Recurly Engage via these methods:

### CSV export

Download one-off reports from Amplitude (ensure **User ID** is first column) and upload to **Settings → User Traits → CSV Import** in Pulse.

### Webhook

1. In Amplitude’s Data Catalog, add a **Webhook** destination.
2. Configure the endpoint details provided by your Customer Success Manager.
3. Filter for only the events needed for your use cases.
4. Test the connection to validate payload delivery.

### Export API

For automated exports, work with your Customer Success team to schedule jobs using the Amplitude [Export API](https://developers.amplitude.com/docs/export-api). Provide an API key with appropriate permissions and configure the schedule to automatically sync data into Recurly Engage.