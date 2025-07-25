---
title: Download data
excerpt: >-
  Configuration guide for the Download Data feature, which allows you to export
  Segment, Prompt, Guide, and activity data from Recurly Engage.
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

The **Download Data** feature enables you to export various datasets—such as segment definitions, prompt configurations, and user activity—for offline analysis or integration with external systems.

# Key benefits

* **Flexible exports**: Get CSV files of segments, prompts, and guides for quick offline review.
* **Seamless integration**: Sync activity data with external reporting tools like Google Analytics or AWS S3.
* **Comprehensive auditing**: Access detailed prompt interaction logs to understand user behavior and system performance.

# Key details

Recurly Engage can export data to various external systems. The simplest option is a CSV export of Segment, Prompt, and Guide data.

More advanced options to receive event data and syncing with an external reporting system like Google Analytics are also possible.

## Download from Pulse

See this [article](/docs/can-i-download-prompt-interactions-data#detailed-activity-data) for instructions on how to download activity data directly from Pulse.

## Download from AWS S3

Data from all user activity relating to running prompts are continuously saved to an AWS S3 bucket. This data may be imported into your BI system for offline analysis.

1. **Go** to **Settings > User Traits**
2. **Select** “Show credentials”.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/60d5733d567e8ebe61eeef8a39345ccf6c7c78e00d792a40bf4f185f6db46108-aws-creds.png" />

3. You will need to copy the AWS Bucket, Access Key and Secret Key to log in. Replace `ingest` with `exports` within the Upload Location path. All filenames will start with the activities prefix.

## Prompt activity data specifications

| Field                        | Description                                                | Notes                                                         |
| ---------------------------- | ---------------------------------------------------------- | ------------------------------------------------------------- |
| app\_id                      | Recurly Engage app id                                      | Assigned by Recurly Engage                                    |
| app\_name                    | Recurly Engage app name                                    | Name as saved within Settings > Application                   |
| activity                     | Type of activity                                           | Values: impression, timeout, dismiss, decline, click, exclude |
| user\_id                     | Unique ID of user                                          |                                                               |
| anonymous\_user\_id          | Identifier for a user in the event userId is not available |                                                               |
| promo\_id                    | Unique ID of prompt                                        | Assigned by Recurly Engage                                    |
| promo\_name                  | Name of prompt                                             | As configured in Recurly Engage Console                       |
| experiment\_id               | Unique ID of experiment                                    | Only populated if there is a running experiment               |
| variation\_id                | Unique ID of variation                                     | Only populated if there is a running experiment               |
| variation\_name              | Name of variation                                          | Only populated if there is a running experiment               |
| survey\_option               | Survey option label                                        | Only populated for survey prompts                             |
| ts                           | Timestamp that activity occurred                           | Epoch                                                         |
| pipeline\_stage\_start\_id   | Unique ID of pipeline stage                                | Populated as part of Pipeline\_Transition activity (optional) |
| pipeline\_stage\_start\_name | Name of pipeline stage                                     | Populated as part of Pipeline\_Transition activity (optional) |
| pipeline\_stage\_end\_id     | Unique ID of pipeline stage                                | Populated as part of Pipeline\_Transition activity (optional) |
| pipeline\_stage\_end\_name   | Name of pipeline stage                                     | Populated as part of Pipeline\_Transition activity (optional) |