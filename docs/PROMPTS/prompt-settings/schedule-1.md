---
title: Schedule
excerpt: >-
  How to schedule prompts or guides to run only during specific dates, days, and
  times in Recurly Engage.
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

export const PrerequisitesLimitations = ({ header }) => {
  return (
    <div className="flex justify-start">
      <div className="rounded-md p-6 m-4 max-w-lg shadow-md border border-gray-300 dark:bg-gray-800 dark:border-gray-600">
        <p className="text-lg font-bold">{header}</p>
        <p>
          <i className="fa-solid fa-check mr-2" />
          You must have <strong>Company</strong>, <strong>App Administrator</strong>, or <strong>App Member</strong> permissions in Recurly Engage.
        </p>
        <p>
          <i className="fa-solid fa-exclamation-triangle mr-4" />
          Times are interpreted in the selected time zone (user’s or app’s).
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

A **schedule** is a configuration that limits when a prompt or guide is active, using three nested settings: Date Window, Day Part, and Time Part.

# Key benefits

* **Precision timing**: Target promotions or messages during high-traffic windows.
* **Automated control**: Automatically enable and disable prompts without manual intervention.
* **Flexible recurrence**: Combine date ranges, weekdays, and hourly windows for complex schedules.

# Key details

## Date Window

Defines the overall start and end dates for your prompt or guide. The item is active from 12:01 AM on the start date to 11:59 PM on the end date. Leave blank to run indefinitely.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/bc5ca6e-image.png" />

## Day Part

Choose specific weekdays when the prompt or guide is active. If unset, all days are included.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/bfd314d-image.png" />

### Time Part

Set specific hours within each selected day when the prompt or guide will appear. Time parts are a sub-setting of Day Parts—days must be selected first. You must also choose whether to enforce the schedule in the **user’s timezone** or the **app’s timezone**.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/a77ae00-image.png" />

Ensure your time windows do not overlap midnight unless you intend the schedule to wrap across days.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/fcbe451-image.png" />

Use these settings together to create complex schedules—for example, showing a weekend-only special offer every Friday and Saturday evening between 6 PM and 11 PM, from May 1, 2024, through December 31, 2024.