---
title: Sync user traits
excerpt: >-
  How to sync and import user attributes into Recurly Engage for targeted
  campaigns and personalized experiences.
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

Learn how to select, format, and upload user traits to Recurly Engage so you can segment your audience and activate tailored workflows.

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

export const PrerequisitesLimitations = ({ header }) => {
  return (
    <div className="flex justify-start">
      <div className="rounded-md p-6 m-4 max-w-lg shadow-md border border-gray-300 dark:bg-gray-800 dark:border-gray-600">
        <p className="text-lg font-bold">{header}</p>
        <p>
          <i className="fa-solid fa-check mr-2" />
          You must have <strong>Administrator</strong> access in your Recurly Engage console.
        </p>
        <p>
          <i className="fa-solid fa-exclamation-triangle mr-4" />
          Trait imports occur on a daily schedule unless using real-time Segment events.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

**User traits** are attributes—like plan type or billing status—that describe each customer. Syncing these traits enables Recurly Engage to dynamically target users based on their behavior or profile data.

# Key benefits

* **Targeted engagement**: Deliver personalized messages and experiences based on real user data.
* **Data-driven segmentation**: Easily group customers by attributes like plan tier, billing date, or payment status.
* **Automated workflows**: Keep segments up to date with scheduled imports or real-time events.

# Key details

Depending on your use case, identify which user attributes you’ll need and gather them in a CSV or via Segment events. For example:

| Item                | Example                  | Interval  | Source        |
| :------------------ | :----------------------- | :-------- | :------------ |
| Current plan        | Trial / Monthly / Annual | Daily     | CSV           |
| Customer since      | 6 months                 | Daily     | CSV           |
| Next bill date      | 2025-07-15               | Daily     | CSV           |
| Payment method      | Credit card / iOS        | Daily     | CSV           |
| Last payment status | Failed                   | Real time | Segment event |

1. **Create your CSV**

   * Include a header row matching the attribute names.
   * Populate each file with the user identifiers (e.g., email or user ID) plus the trait columns.
   * See the example file in the shared folder for formatting guidelines.

2. **Upload traits**

   * In Recurly Engage, go to **Settings > Data imports**.
   * Select **User traits** and upload your CSV.
   * Schedule the import frequency (daily or one-off).

3. **Real-time events (optional)**

   * If you use Segment or another event source, configure it to send trait updates as they happen.
   * Real-time imports ensure your segments reflect the latest customer activity without waiting for the daily CSV.

A CSV isn’t required if your campaign doesn’t rely on attribute-based targeting. You can learn more about importing user traits [here](user-traits).