---
title: Google Analytics
excerpt: >-
  Integration guide for sending Recurly Engage prompt interaction events to
  Google Analytics via client-side SDK and server-side Measurement Protocol.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
# Overview

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

### Prerequisites & limitations

* Company or App Administrator permissions in Recurly Engage.
* A Google Analytics property and tracking ID (GA Tag ID).
* Access to **Recurly Engage → Settings → Integrations → External → Google Analytics**.
* For server-side calls, familiarity with the Measurement Protocol (v1).

# Definition

The **Google Analytics** integration provides two methods:

1. **Client Integration**: Uses your existing GA JavaScript SDK instance to fire custom events for prompt interactions.
2. **Server Integration**: Sends events via an API action using Google Analytics Measurement Protocol.

# Key benefits

* **Unified reporting**: View prompt metrics within your GA dashboards alongside pageviews and user behavior.
* **Session continuity**: Events fire in the same session context as your GA page events.
* **Custom payloads**: Leverage GA’s Measurement Protocol to include any relevant parameters.

# Key details

## Client integration

For web-based devices, Recurly Engage leverages the running instance of the Google Analytics JS SDK. This ensures session and user context is preserved when reporting real-time prompt events.

1. In **Recurly Engage**, go to **Settings → Integrations → External → Google Analytics**.
2. Enter your [GA Tag ID](https://support.google.com/analytics/answer/9539598?hl=en).

**Event Details**

| Activity                         | Description                                                                             |
| -------------------------------- | --------------------------------------------------------------------------------------- |
| Recurly Engage Prompt Impression | A user has seen the prompt                                                              |
| Recurly Engage Prompt Dismiss    | A user has dismissed the prompt by clicking the close button or outside the prompt view |
| Recurly Engage Prompt Timeout    | The prompt closed automatically due to a timer                                          |
| Recurly Engage Prompt Decline    | A user has declined the prompt by clicking the decline button                           |
| Recurly Engage Prompt Click      | A user has accepted the prompt by clicking the primary CTA button                       |
| Recurly Engage Prompt Holdout    | A holdout user has reached the prompt but not seen it                                   |
| Recurly Engage Prompt Click 2    | A user has accepted the prompt by clicking the secondary CTA button                     |

Each event includes these attributes when applicable:

| Event Property    | Description                                     |
| ----------------- | ----------------------------------------------- |
| `promo_id`        | Unique prompt identifier (see Prompt Details)   |
| `promo_name`      | Name of the prompt                              |
| `variation_id`    | Identifier of the experiment variation (if any) |
| `variation_name`  | Name of the experiment variation (if any)       |
| `event_timestamp` | Timestamp when the interaction occurred         |

***

## Server integration

### Create an API action

Configure a POST action in **Settings → Actions → API Actions** to send events via Google Analytics Measurement Protocol (v1). Use the following endpoint:

```
https://www.google-analytics.com/collect
```

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/ebf7cc4-Google_Analytics_Custom_Action.png" />

### Specify the payload

Include required and optional Measurement Protocol parameters.

* **Required**: `v` (protocol version), `tid` (Tracking ID), `t` (hit type, e.g., `event`).
* **Optional**: `cid` (Client ID), `ec` (event category), `ea` (event action), `el` (event label), `ev` (event value).

See full parameter reference: [https://developers.google.com/analytics/devguides/collection/protocol/v1/parameters](https://developers.google.com/analytics/devguides/collection/protocol/v1/parameters)

### Add action to prompt

Attach the newly created API action to a prompt interaction (Accept, Decline, etc.) or within a Guide/Experience.\
Follow the [Add Action guide](actions-1) for detailed steps.