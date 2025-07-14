---
title: Segments
excerpt: >-
  How to create and manage user segments in Recurly Engage for targeted prompt
  delivery.
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

### Video

<Embed url="https://www.loom.com/embed/5e730b455754424fa13f1f282bcaafe6?sid=669292ce-0cd1-4d29-960a-ad13a1aebd5c" href="https://www.loom.com/embed/5e730b455754424fa13f1f282bcaafe6?sid=669292ce-0cd1-4d29-960a-ad13a1aebd5c" typeOfEmbed="iframe" height="480px" width="100%" iframe="true" />

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

### Prerequisites & limitations

* Company or App Administrator permissions in Recurly Engage.
* No limit on the number of segments you can create; users may belong to multiple segments.

# Definition

A **segment** uses trait filters—built-in usage, device, location, or imported custom [traits](user-traits)—to include or exclude users based on characteristics or behaviors.

# Key benefits

* **Precision targeting**: Reach the right users with contextually relevant messages.
* **Dynamic audiences**: Automatically update segments based on real-time trait changes.
* **Cross-functional data**: Leverage external data via custom trait imports for advanced targeting.

# Key details

## Trait sources

* **Built-in traits**: Usage metrics (visits, minutes), device type, location, prompt interactions.
* **Custom traits**: Import via AWS S3, CSV upload in Pulse, or real-time event data from your application.

## Common segment examples

* Monthly plan members with declining visits.
* Trial users.
* Users with failed payments.

## Usage-based segments

Combine with [Usage Tracking](usage-tracking-1) to target based on app behavior:

* Users who have never visited a specific page or content.
* Users who clicked a particular button or section.

## Guide

Below is an example for creating a segment of **Engaged, US-based iOS Premium plan users who have not redeemed the iOS prompt**:

1. **Navigate** to **Segments > New Segment**.
2. **Enter** a **Name** (e.g., “Engaged iOS Premium – No Redemption”) and optional **Description**.
3. **Add** trait filters in sequence:

   * **Engaged**: Choose **Usage → Visits** → **Greater than or equal to** → **2** over the last **7 days**.
   * **US-based**: Select **Location → Countries** → **Include** → **United States of America**.
   * **iOS**: Select **Device → OS** → **iOS**.
   * **Premium plan**: Under **Custom** → **Plan** → **Include** → **Premium**.

     > **Note:** “Custom” covers any traits you’ve imported—learn more about importing custom traits [here](user-traits).
   * **Not redeemed iOS prompt**: Select **Interactions → User has not → accepted (primary) → \[iOS popup]**. Choose your created prompt from the dropdown.
4. **Click** **Save** to create the segment.
5. **Toggle** **Enable** to activate the segment and begin real-time monitoring.

Recurly Engage will start processing incoming data and populate your segment within a few hours. Monitor the segment’s metrics by clicking into its detail view and adjusting the date range as needed.