---
title: Recurly.js / HAM / Checkout
deprecated: false
hidden: true
metadata:
  description: >
    Information on Recurly Engage's automatic integration with Recurly.js,
    Hosted Account Management, and Checkout. It explains how this integration
    enables churn prevention and abandoned cart use cases with minimal
    engineering effort.
  robots: index
---
# Definition

Recurly Engage is a powerful, low-code platform designed to help businesses manage and optimize subscriber engagement. For Recurly Subscription Management (RSM) customers, this integration is particularly seamless. Once your Recurly Engage account is enabled, it automatically becomes available across **Recurly.js, Hosted Account Management, and Recurly Checkout.** This allows you to immediately begin implementing core use cases like **Cancel Save** and **Involuntary Churn** with no additional engineering effort.

<Image align="center" src="https://files.readme.io/a4db3dcdd83acc1b07904125149de9ec922be851bc2b6695ddc4550af1d58fe3-Screenshot_2025-09-12_at_1.25.37_PM.png" />

# Key benefits

The out-of-the-box integration of Recurly Engage offers significant value across key customer touchpoints:

* **Hosted Account Management:** Recurly Engage is automatically enabled on the Hosted Account Management pages. This allows you to target existing subscribers to reduce involuntary churn, offer cancel-save incentives, or promote plan upgrades.
* **Recurly Checkout:** Recurly Engage is pre-integrated into the Recurly Checkout pages to optimize your conversion funnel. This functionality supports workflows for abandoned cart recovery, cross-sells, and upsells, helping you drive new visitors and improve overall checkout completion rates.
* **Recurly.js:** For merchants who use Recurly.js to build custom account and checkout experiences, the Engage integration is automatically included wherever Recurly.js is installed. This provides a no-code solution for implementing in-app messaging on payment and checkout pages to address abandoned carts, prevent payment failures, and execute upsell campaigns.

This deep integration allows you to fully customize Engage prompts to suit your business needs across these critical pages.

<Image align="center" src="https://files.readme.io/c383fd83e685b78808654a4a6d27be7dd52e793b9678c71888f3e7f4f98fea16-Screenshot_2025-09-12_at_1.27.52_PM.png" />

# Key details

Once your Recurly Engage account has been enabled by your Recurly Account Manager, follow these steps to begin leveraging the integration:

1. **Follow the Recurly Engage Integration Guide: **[Refer to the official guide](https://docs.recurly.com/recurly-subscriptions/docs/recurly-engage-integration)  to complete the initial setup of your Recurly Engage account.
2. **Access Out-of-the-Box Functionality:** Upon completion of the integration guide, Recurly Engage will be automatically enabled on your Hosted Account Management pages, Recurly Checkout, and any pages where Recurly.js is installed. No additional engineering effort is required for these core use cases.
3. **Manual Installation (Optional):** To extend Recurly Engage to additional site pages, such as your product catalog or marketing content, you must manually install the Recurly Engage Javascript tag (redfast.js) on those pages.
4. **Manage Multiple Tags:** If you are using Recurly.js and choose to manually install the redfast.js tag, it is recommended that you disable the automatic redfast.js installation to prevent duplication. The system is designed to handle deduplication, but managing a single tag is the best practice. The system will always use the first tag it encounters.

<br />

```
<head>
  <!-- auto installed when Recurly.js is installed, ideally disable, but we dedupe –>
  <script src="https://00c2a588-6f6c-454a-950a-bbfaae614b3b.redfastlabs.com/assets/redfast.js" async>		</script> 

  <!-- manually installed by you or added via google/tealium tag manager →
  <script src="https://00c2a588-6f6c-454a-950a-bbfaae614b3b.redfastlabs.com/assets/redfast.js" async>		</script>
</head>

```

<br />
