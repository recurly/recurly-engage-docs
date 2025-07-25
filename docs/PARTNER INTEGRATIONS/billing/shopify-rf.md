---
title: Shopify
excerpt: >-
  Configuration guide for the Shopify connector in Recurly Engage—setup,
  supported actions, and usage steps.
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
          <strong>Company</strong> or <strong>App Administrator</strong> permissions in Recurly Engage.
        </p>
        <p>
          <i className="fa-solid fa-check mr-2" />
          Your site must be hosted on Shopify with the storefront API enabled.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

The **Shopify** connector enables web prompts to interact with your Shopify storefront—adding items to carts, redirecting to product or checkout pages, and applying discount codes seamlessly.

# Key benefits

* **Streamlined purchase flows**: Let users add products or apply discounts without leaving your prompt.
* **Increased conversions**: Reduce friction by embedding cart actions directly in your engagement messages.
* **Flexible redirects**: Guide users to specific Shopify pages (collections, products, checkout) with a single click.

# Key details

## Required settings

Under **Settings > Connectors > Shopify**, provide:

* **Shop URL**: Your Shopify store domain (e.g., `your-store.myshopify.com`).

## Supported actions

Use the following actions within web prompts to drive e-commerce interactions:

| Action       | Description                                | User Dependencies | Additional Instructions                        |
| ------------ | ------------------------------------------ | ----------------- | ---------------------------------------------- |
| Add to cart  | Add one or more items to the existing cart | None              | Specify SKU(s) and quantity                    |
| Redirect     | Navigate the user to a Shopify URL         | None              | Enter the target URL (product, checkout, etc.) |
| Add Discount | Apply a discount code to the existing cart | None              | Provide the discount code                      |

## Step by step

Follow these steps to configure a Shopify action within a prompt:

1. In Recurly Engage, **go** to **Settings → Actions → Website Actions**.
2. **Scroll** to the **Shopify** section and **click** **Add Action**.
3. **Select** your desired action type (e.g., **Add to cart**).
4. **Configure** the action details:

   * **Add to cart**: Enter SKU(s) and quantity for each item.
   * **Redirect**: Provide the Shopify URL to navigate users.
   * **Add Discount**: Input the discount code to apply.
5. **Save** the action.
6. **Attach** this action to any **Web** prompt under the **Actions** panel.

Once published, users interacting with the configured prompt will experience seamless Shopify workflows directly within your engagement messages.