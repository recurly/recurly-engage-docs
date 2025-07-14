---
title: Cleeng
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
#### Metadata description

Configuration and usage guide for the Cleeng connector in Recurly Engage, including API setup, supported actions, and subscription data syncing.

# Overview

The **Cleeng** integration enables you to manage subscriber offers, coupons, and reactivations directly from prompts within Recurly Engage by connecting to your Cleeng account.

### Required plan

This feature or setting is available to all customers on any Recurly Engage subscription plan.

### Prerequisites & limitations

* Company or App Administrator permissions in Recurly Engage.
* A Cleeng Publisher account with a valid API Broadcaster Token.

# Definition

The **Cleeng** connector synchronizes offers and subscription data from Cleeng, allowing you to trigger subscription management actions from within your prompts.

# Key benefits

* **Seamless plan management**: Upgrade or downgrade user subscriptions via prompts.
* **Coupon application**: Apply promo codes instantly when users interact.
* **Reactivation support**: Easily reactivate churned subscribers through targeted prompts.

# Key details

## Required settings

Configure your Cleeng connector under **Settings > Connectors**:

* **API Key**: Your Broadcaster Token. Instructions [here](https://publisher.support.cleeng.com/hc/en-us/articles/218389137-Obtaining-your-API-Broadcaster-Token).

## Supported actions

Available billing actions you can attach to prompt interactions:

| Action                  | Description                                                | Dependencies                                         |
| :---------------------- | :--------------------------------------------------------- | :--------------------------------------------------- |
| Switch Subscription     | Subscribe user to a different offer (upgrade or downgrade) | Offer upgrade/downgrade configured in Cleeng console |
| Apply Coupon            | Apply coupon code to the user’s subscription               | None                                                 |
| Reactivate Subscription | Reactivate a subscription marked for cancellation          | None                                                 |

## Sync subscription data

Schedule periodic export of subscription data from Cleeng into Recurly Engage using CSV via S3.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/217df5b-Screenshot_2024-06-02_at_10.08.45_PM.png" />

## Setup

1. In the Cleeng console, **navigate** to **Segments**.
2. **Click** **Build a Segment**, then **click** the gear icon (upper right).
3. **Select** **Schedule** from the dropdown.
4. **Click** **New**, **name** the schedule (e.g., “Recurly Engage Sync”).
5. **Choose** **Amazon S3** as the delivery method.
6. **Fill in** **Bucket**, **Optional Path**, **Access Key**, and **Secret Key** from **Pulse > Settings > User Traits > AWS S3 Credentials**. **Select** **US West (Oregon) – us-west-2** for the region.
7. **Set** format to **CSV**.
8. For **Trigger**, **choose** **Repeating interval**.
9. Under **Deliver this Schedule**, **select** **Daily** → **Every day** at a post-midnight time (e.g., 1:00 AM).
10. **Expand** **Advanced Options**:

    1. **Send this schedule if**: “there are results”.
    2. **Check** “and results changed since last run”.
    3. **Set** **Timezone** to “United States – Los Angeles”.
11. **Use** **Send Test** and coordinate with your Customer Success Manager to verify the data transfer.
12. **Click** **Save All** to finalize the schedule.