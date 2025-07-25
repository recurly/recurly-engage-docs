---
title: Event API Firehose
excerpt: >-
  Configuration guide for the Event API Firehose feature, which allows you to
  export and stream usage tracking data via AWS S3 or custom webhooks.
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

export const PrerequisitesLimitations = ({ header }) => {
  return (
    <div className="flex justify-start">
      <div className="rounded-md p-6 m-4 max-w-lg shadow-md border border-gray-300 dark:bg-gray-800 dark:border-gray-600">
        <p className="text-lg font-bold">{header}</p>
        <p>
          <i className="fa-solid fa-check mr-2" />
          You must have <strong>Company</strong> or <strong>App Administrator</strong> permissions in Recurly Engage.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

The **Event API Firehose** feature pushes usage tracking events in JSON format to external systems—either by writing to an S3 bucket or by POSTing to a custom web API endpoint—enabling real-time or batch consumption of event data.

# Key benefits

* **Real-time insights**: Stream usage events as they occur for immediate data-driven decisions.
* **Scalable storage**: Offload event logs to S3 for long-term retention and BI integration.
* **Flexible integration**: Send data to any HTTP endpoint or cloud storage service to fit your architecture.

# Key details

## S3 Event Data Logs

Usage tracking data that has been enabled in Recurly Engage can be pushed to external systems. Anything added in the Usage Tracker section is sent as an event once the integration is set up.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/d7f9c3c-Event_Export_1.png" />

There are two ways to receive usage data. You must provide the following values to your account manager:

**AWS S3 Requirements** – Pull data using Recurly Engage:

* **Go** to **Settings > User Traits**.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/bfbf239-Event_Exports_settings.png" />

* **Select** “Click here for AWS S3 credentials”.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/a970314-Event_Exports_settings_1.png" />

* **Copy** the **AWS Bucket**, **Access Key**, and **Secret Key**, then **navigate** to the `exports` folder. All filenames start with the `usages` prefix. Pull this data on demand.

### AWS S3 data specifications

All data is JSON formatted with the following fields. To enable optional fields, ask your account manager:

| Field               | Description                                                                  | Notes                                        |
| ------------------- | ---------------------------------------------------------------------------- | -------------------------------------------- |
| user\_id            | Primary user identifier                                                      |                                              |
| anonymous\_user\_id | Identifier when userId is unavailable                                        |                                              |
| event               | Name of event                                                                |                                              |
| platform            | Type of integration                                                          | Always `redfast` for usage                   |
| type                | Type of tracker                                                              | Values: `page`, `track`, `custom`            |
| properties.id       | Usage Tracker id                                                             |                                              |
| properties.values   | Configured values in Recurly Engage Console                                  |                                              |
| properties.options  | Additional options                                                           | Specifies if regex is used for page trackers |
| ts                  | Timestamp when activity occurred (epoch)                                     |                                              |
| app\_id             | Recurly Engage app id                                                        | Optional                                     |
| traits              | Key/value pairs of user attributes ingested from external and in-app sources | Optional                                     |
| segments            | List of segment objects (id + name) at event time                            | Optional                                     |
| paths               | List of personalization path objects (id, name, device\_type, zone)          | Optional                                     |

### Event types

| Type                            | Description                                            |
| ------------------------------- | ------------------------------------------------------ |
| Impression                      | User was shown the prompt                              |
| Timeout                         | User did not respond before timer expired              |
| Dismiss                         | User dismissed by clicking `X` or outside the window   |
| Decline                         | User clicked on the decline link                       |
| Click                           | User accepted the prompt (phased out in favor of Goal) |
| Goal                            | User accepted the prompt                               |
| Custom\_Goals\_\[Activity Type] | User completed a defined custom goal on a prompt       |
| Exclude                         | User excluded due to holdout or user limits            |
| Holdout                         | User in holdout group                                  |
| Pipeline\_Impression            | User shown the prompt and is in a pipeline stage       |
| Pipeline\_Transition            | User moved from one pipeline stage to another          |

## Custom Web API Firehose

This option provides near-real-time delivery. Recurly Engage can send single or batched events within sub-minute windows to an endpoint you specify. Provide your account manager with:

* **URL**
* **API Key** / **Access Token**
* **Request type** (`GET`, `POST`, `PUT`)

### Payload format

The payload is a JSON array of event objects. In S3 each event is one object per row.

```json
[  
  { /* event object as shown below */ },  
  { /* ... */ }  
]
```

### Example event payload

```json
{
  "app_id": "74f72649-0327-4911-bd21-a4cd533cec1c",
  "user_id": "123",
  "anonymous_user_id": "2528a84d8fa8…",
  "event": "Home Page",
  "platform": "redfast",
  "type": "page",
  "ts": 1630476856,
  "properties": {
    "id": "8e282c72-07da-4c2f-bf91-85df633828af",
    "values": [{ "url_hash": "", "url_path": "/", "query_params": "" }],
    "options": { "use_regex": false }
  },
  "traits": { /* user trait key/value pairs */ },
  "segments": [{ "id": "...", "name": "Engaged" }, /* ... */],
  "paths": [{ "id": "...", "name": "Prompt A", "device_type": "web", "zone": "banner" }, /* ... */]
}
```

### API data specifications

| Field               | Description                                              | Notes    |
| ------------------- | -------------------------------------------------------- | -------- |
| app\_id             | Recurly Engage app id                                    |          |
| user\_id            | Primary user identifier                                  |          |
| anonymous\_user\_id | Identifier when userId is unavailable                    |          |
| event               | Name of event                                            |          |
| platform            | Always `redfast`                                         |          |
| type                | `page`, `track`, or `custom`                             |          |
| properties.id       | Usage Tracker id                                         |          |
| properties.values   | Configured tracker values                                |          |
| properties.options  | Regex or other options                                   |          |
| ts                  | Epoch timestamp                                          |          |
| traits              | User attributes (key/value pairs)                        | Optional |
| segments            | Segment list (id + name)                                 | Optional |
| paths               | Personalization path list (id, name, device\_type, zone) | Optional |

### Usage types

| Type   | Description                               |
| ------ | ----------------------------------------- |
| page   | Page view tracker                         |
| track  | Button or CSS class click                 |
| custom | Custom event (e.g., transaction complete) |

#### API Push example

```bash
curl 'example.backendurl.com/v1/api/ingest/' \
  -X POST \
  -H 'Content-Type: application/json' \
  -H 'your-api-key: abcdef' \
  --data-raw '[ { /* event objects */ } ]'
```