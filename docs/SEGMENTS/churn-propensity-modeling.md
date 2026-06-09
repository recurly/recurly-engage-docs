---
title: Churn Propensity Modeling
deprecated: false
hidden: true
metadata:
  robots: index
---
#### Metadata description: Predict subscriber churn risk before cancellation occurs using Recurly Engage's machine learning propensity model — combining behavioral engagement signals with subscription billing intelligence to enable proactive retention.

# Churn propensity modeling

### Prerequisites
- Recurly Engage must be enabled on your account
- The Churn Propensity Score feature must be activated by your Recurly customer success team before it appears in the Engage console
- Approximately two weeks of subscriber data is required for meaningful predictions; full model accuracy is reached after approximately 12 weeks

### Limitations
- Score distributions may take time to stabilize for new accounts or accounts that have recently onboarded a large number of subscribers
- It's normal for some accounts to have few or no subscribers in the 8–10 risk range — this reflects the model's confidence threshold, not a misconfiguration
- Merchants using Recurly Engage without Recurly Subscription Management (RSM) have access to a behavioral engagement-only model; the enhanced model incorporating billing and payment history requires RSM

# Definition

Churn Propensity Modeling is a machine learning feature within Recurly Engage that assigns each subscriber a real-time risk score reflecting their likelihood of canceling. Rather than reacting after a cancellation has already occurred, the feature surfaces at-risk subscribers early — giving you the opportunity to intervene with targeted retention campaigns, personalized offers, or guided experiences before a subscriber has made the decision to leave.

The model trains on historical subscriber data and learns the behavioral patterns associated with churn. Because engagement habits vary across industries and business models, the model establishes merchant-level baselines to calibrate expected behavior, ensuring scores are contextually meaningful for your platform.

Risk scores are expressed on a scale of 1–10, where 1 indicates low churn risk and 10 indicates very high churn risk. Scores update automatically whenever new engagement activity is detected, or every five days in the absence of activity.

Data inputs vary by merchant configuration:

| Integration type | Data used in model |
|---|---|
| Recurly Engage + RSM | Behavioral engagement signals + subscription billing and payment history |
| Recurly Engage only | Behavioral engagement signals only |

The model improves as more data accumulates. Scores are useful after approximately two weeks of subscriber data and reach full accuracy after approximately 12 weeks. If you maintain your own propensity scores, you can import them as user traits and use them for segmentation alongside — or instead of — the native model.

# Key benefits

- **Proactive retention**: Identify at-risk subscribers before they make a cancellation decision, enabling timely and relevant outreach.
- **Unified data model**: For RSM merchants, behavioral engagement signals are combined with subscription billing data — including payment history, renewal trends, and pause and cancellation events — providing a more complete picture of subscriber health than engagement signals alone.
- **Granular risk scoring**: The 1–10 scale gives you more flexibility than a binary flag, supporting tiered intervention strategies based on confidence level.
- **Flexible segmentation**: Combine churn scores with other subscriber attributes — such as geographic location, coupon usage history, or prior prompt interactions — to build highly targeted audiences.
- **Dynamic score updates**: Scores recalculate on every new engagement event and every five days of inactivity, keeping risk signals current without manual intervention.
- **Works across merchant types**: All Recurly Engage merchants can use this feature, regardless of RSM status. RSM merchants benefit from a richer dataset that improves model accuracy over time.

# Key details

## How to use churn propensity modeling

### Step 1 — Request feature enablement

The Churn Propensity Score feature must be enabled on your account before it's accessible in the Recurly Engage console. Contact your Recurly customer success team to request activation.

### Step 2 — Allow the model to accumulate data

Once enabled, the model begins learning from incoming subscriber activity. Avoid drawing conclusions from early scores — meaningful predictions emerge after approximately two weeks of data, with full model accuracy reached around 12 weeks.

If your account is brand new or has recently onboarded a large number of new subscribers, expect score distributions to stabilize over time. It's also normal for some accounts to have few or no subscribers in the 8–10 range; this reflects the model's confidence threshold and is not a misconfiguration.

### Step 3 — Create a segment using the churn score

1. In the Recurly Engage console, navigate to **Segments**.
2. Select **Add new segment**.
3. Under the **Users** section, locate the **Churn Score** attribute.
4. Use the slider to define the score range you want to target (for example, 7–10 for high-risk subscribers).
5. Optionally, add additional conditions to refine the audience — such as geographic filters, coupon usage history, or prior prompt interactions.
6. Save the segment.

### Step 4 — Associate the segment with a prompt or campaign

Once your segment is saved, attach it to a prompt, guide, or retention campaign within Engage. Common use cases include surfacing a discount offer, initiating a cancel-save flow, or triggering a personalized re-engagement message for subscribers in a defined risk band.