---
title: Segment traffic split
excerpt: Optimize prompt performance with traffic splitting
deprecated: false
hidden: true
metadata:
  description: >-
    A guide on Recurly Engage's traffic splitting feature. It explains how to
    A/B test different prompt experiences, like modals and banners, to optimize
    performance and conversion rates.
  robots: index
---
# Overview

Recurly Engage now offers advanced traffic splitting functionality, empowering you to effectively A/B test different prompt experiences. This new feature allows you to distribute a segment's traffic across various prompts, enabling direct comparison of performance between different formats like a modal and an inline banner. Unlike our [experiments feature](https://docs.recurly.com/recurly-engage/docs/create-an-experiment#/)  that runs in the app, this one allows you to test across different types.

# Key benefits

* **Data-Driven Decisions:** Move beyond guesswork by directly comparing how different prompt types engage your audience. This helps you make informed choices that drive the best results.
* **True A/B Testing:** Previously, you could only test variations within a single prompt type. Now, you can run true A/B tests between fundamentally different experiences (e.g., a modal vs. a banner) to see which one performs better.
* **Maximize Conversions:** Easily collect performance data and use it to maximize your conversions. For example, you can configure a campaign to show a modal to the first 30% of your target segment and an inline banner to the remaining 70%, then analyze which experience drives higher engagement.
* **Control:** Use it to set a control group by avoiding a percent of users who are never targeted within a segment.

# Key details

Steps to implement a segment traffic split.

1. **Ensure** you are an active member of Recurly Engage. If not, **[book a demo today](https://recurly.com/product/engage/)** !
2. **Go** to the Segments section in Pulse, the Recurly Engage management console.
3. **Select** the segment type you’d like to split.

<Image align="center" className="border" border={true} src="https://files.readme.io/e409c776c04af53195f1da755493a6b4a5a2b0efc5c7c09e61e9909def8e3e03-unnamed.png" />

4. In the segment detail view, you should see all of the Prompts where the selected segment are active. **Select** the Assign Traffic button on the prompt.

<Image align="center" className="border" border={true} src="https://files.readme.io/244de544d0c37c8688ecf827078bc439d6c6c79baa10623d0a82eae334d87995-segment_split_2.png" />

5. For the selected prompt, set the segmentation split amount. **Once a user is assigned to a group, they will always remain in that group based on a bucketing methodology.** Repeat this step for the second prompt you want to segment.
   <br />
   Set the segmentation split amount for each prompt type.
   <br />
   **Example:**
   For the first group, set the split to 0-50.
   For the second group, set the split to 51-100.

<Image align="center" className="border" border={true} src="https://files.readme.io/ade828ff41c3d1f4fcf50723df1c3cce7d32ff92f6a8d22a3f711a52a9bdaa6b-segment_split_3.png" />

<Image align="center" className="border" border={true} src="https://files.readme.io/18cacc2dd7ae5768b6ef9703fbb32eab55f1b74ea629747a778e4c7eb639b7a1-segment_split_4.png" />

<br />
