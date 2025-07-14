---
title: mParticle
excerpt: >-
  Integration guide for capturing Recurly Engage prompt interactions as custom
  events in mParticle via Custom Feed.
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

The **mParticle** connector lets you export prompt events and attributes from Recurly Engage to your mParticle workspace, enabling unified user activity tracking across platforms.

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

### Prerequisites & limitations

* Company or App Administrator permissions in Recurly Engage.
* An mParticle account with permissions to create Custom Feeds.
* Access to your mParticle workspace’s Server Key and Secret.

# Definition

Using mParticle’s Custom Feed integration, Recurly Engage will send prompt interaction events and related attributes to mParticle for real-time analytics and segmentation.

# Key benefits

* **Streamlined event export**: Automatically push Recurly Engage events into mParticle without custom coding.
* **Unified user data**: Leverage mParticle’s identity resolution and data pipeline for prompt events.
* **Real-time insights**: View prompt impressions, clicks, and custom goals alongside all other mParticle-tracked events.

# Key details

## Activation

1. In **mParticle**, **navigate** to **Setup → Inputs**.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/d0f22ee-mParticle_add_new_custom_feed.png" />

2. **Click** on the **Feeds** tab and **add** a **Custom Feed** by clicking the **+** icon.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/9b94f9b-mParticle_add_new_custom_feed_1.png" />

3. Provide a **Configuration Name**, then share the **Server Key**, **Server Secret**, and **API Endpoint** with your Recurly Engage Customer Success Manager.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/27a2abc-mParticle_add_new_custom_feed_2.png" />

### Required settings

Under **Settings → Integrations → External → mParticle** in Recurly Engage, configure:

* **Base API Endpoint** (including mParticle Pod)
* **Server Key**
* **Server Secret**
* **Mode**: Production or Development

### Supported actions

| Action            | Description                                                                 |
| ----------------- | --------------------------------------------------------------------------- |
| **Export Events** | Reports custom events with user-specific prompt interactions and attributes |

## Custom events and attributes

After activation, mParticle will receive the following custom events tagged to the user’s identity, visible in the User Activity screen:

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/b504573-mparticle-user-activity-4.png" />

<br />

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/e006d0a-mparticle-custom-event-5.png" />

| Custom Event                          | Description                                                               |
| ------------------------------------- | ------------------------------------------------------------------------- |
| **Recurly Engage Prompt Impression**  | A user has seen the prompt                                                |
| **Recurly Engage Prompt Dismiss**     | A user has dismissed the prompt by clicking close or outside (if enabled) |
| **Recurly Engage Prompt Timeout**     | The prompt closed automatically due to a timer                            |
| **Recurly Engage Prompt Decline**     | A user declined the prompt by clicking the decline button                 |
| **Recurly Engage Prompt Click**       | A user accepted the prompt via the primary CTA                            |
| **Recurly Engage Prompt Custom Goal** | A user completed the custom goal action defined for the prompt            |

**Attributes** sent with each event (when available):

| Custom Attribute  | Description                                                          |
| ----------------- | -------------------------------------------------------------------- |
| `app_name`        | The name of your Recurly Engage instance in Pulse                    |
| `prompt_id`       | Unique prompt identifier (from Details)                              |
| `prompt_name`     | The name of the prompt                                               |
| `experiment_id`   | Unique experiment identifier (if the prompt is part of an A/B test)  |
| `experiment_name` | Name of the running experiment                                       |
| `variation_id`    | Identifier for the specific prompt variation                         |
| `variation_name`  | Name of that prompt variation                                        |
| `survey_value`    | Value of selected survey option (if survey is enabled on the prompt) |

***

## Additional resources

* [mParticle Custom Feed Reference](https://docs.mparticle.com/integrations/custom-feed/feed/)