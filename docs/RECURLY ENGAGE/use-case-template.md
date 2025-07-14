---
title: Use Case Template
excerpt: A sample document to outline a use case
deprecated: false
hidden: true
metadata:
  robots: index
---
This document may be used to create a structured definition of the use case you wish to implement.

### Business Objective

Describe the primary outcome desired from the implementation of this use case.

Example. Reduce cancellations from monthly subscribers

### Outline

In a few sentences describe the end user experience that will achieve the desired outcome.

Example. When a member clicks on the 'Cancel' button on the Account page, show a multi-step guide to understand and mediate their reason for canceling.

The first step is to ask them the reasons for cancellation. Three options should be provided:

1. Too expensive
2. Not enough content
3. Not using it

The second step is conditional on the option selected.

If 'Too expensive' was selected, offer next month at no cost. Experiment between next month free, 50% off for two months.

If 'Not enough content' was selected, display upcoming new releases.

If 'Not using it' was selected, offer to pause the subscription for three months. Experiment between one, two, and three months.

Every path must include the option to 'Cancel anyway'.

### [Segment](/docs/segments#)

Describe the characteristics of the target users who should receive this experience.

Example. Members on the monthly plan with a non-IAP payment method and at least three months of successful rebills.

Required User Traits (attributes) :

* Plan type
* Payment method
* Lifetime (in months) or Member since (date)

### [Trigger](/docs/triggers#/)

Describe the end user action that will initiate the prompt or guide.

Example. When the member clicks on the 'Cancel' link on the /accounts page.

### [Schedule](/docs/schedule-1#/)

Optional. Specify a start and end date for this campaign.

### Design

<Tabs>
  <Tab title="First Step">
    ![Step 1](https://files.readme.io/5f3cdf7ddf0bef60fdadc8bc7ebd9975d57dd5745a134e0c1551753179b3f354-Screenshot_2025-02-02_at_2.25.59_PM.png)
  </Tab>

  <Tab title="Second Step">
    ![Step 2](https://files.readme.io/1c73d7f4c305e7898d4bd404c03cb1647a5b94e88cb25b48980bac630bdcaf64-Screenshot_2025-02-02_at_2.26.41_PM.png)
  </Tab>

  <Tab title="Third Step">
    ![Step 3](https://files.readme.io/2c031af673cbff888d076c3ed8aeaa3f338d2e4c167d696471a4fe91785f13ca-Screenshot_2025-02-02_at_2.26.19_PM.png)
  </Tab>
</Tabs>

Optional:

* Legal disclaimer text
* Timer
* Customize the CSS to match your look and feel

### [Experiment](/docs/create-an-experiment#/)

Optionally you may decide to experiment with the right call to action for a given segment.

Example. 50% of the users get 'Next Month Free' and the other 50% get '50% OFF for Two Months'

### [Call to Action](/docs/actions-1#/)

A call to action is a button click presented to the end user within the prompt. CTAs in Redfast are typically 1-click because the end outcome is directly connected to the button via an integration such as [Stripe](/docs/stripe#/) .

Example:

* Reasons for cancellations prompt: Select Option, Cancel Anyway.
* Too expensive prompt: Accept Offer, Cancel Anyway
* Not enough content prompt: See more, Cancel Anyway
* Not using prompt: Pause my subscription, Cancel Anyway