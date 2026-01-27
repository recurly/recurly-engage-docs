---
title: Engagement categories
excerpt: >-
  Learn how to assign specific use-case categories to prompts during
  configuration to ensure accurate success rate tracking and reporting.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

The Prompt Classification system allows you to explicitly define the intended use case for every prompt you configure. With this update, you can now select a specific category—such as Acquisition or Retention (among others)—directly within the configuration dropdown when creating or editing a prompt. This ensures that every prompt is tagged with a clear intent from the moment of launch, regardless of whether it results in a transaction.

# Key benefits

* **Accurate success rate tracking:** By classifying prompts at the configuration stage, we can calculate the "Prompt Success Rate" for specific types of campaigns (e.g., Acquisition vs. Upgrade). This eliminates the data gap where only successful revenue-generating prompts were categorized.
* **Enhanced revenue analysis**: Defining the prompt’s intent allows for more precise Recovered Revenue analysis. Business Intelligence teams can better attribute revenue to specific strategies, providing a clearer picture of ROI for sales and strategy conversations.

# Key steps

## Step 1: Assigning a category

When configuring a new prompt, you will see a required dropdown menu labeled **Prompt** Category. You must select one of the following intent types:

* **Acquisition:** Encouraging new user conversion.
* **Retention:** Keeping existing users active.
* **Win Back:** Re-engaging lapsed users.
* **Upgrade:** Moving users to a higher tier or product.
* **Engagement:** General interaction and usage promotion.

_Note: Default generated guides and prompts have these categories automatically attributed._

## Step 2: Updating existing prompts & guides

For prompts and guides created prior to this update, assigning an engagement category is optional. You are not required to go back and tag your entire library immediately.

However, to ensure your reporting data is as accurate as possible, you can manually assign categories to existing content at any time:

* Navigate to the Detail Screen of the specific prompt or guide.
* Select the appropriate engagement  category from the dropdown menu.
* Save your changes to begin tracking that item’s intent in your success rate metrics.

## Step 3: Behavior with guides

If a prompt is associated with a Guide, the categorization logic follows strict inheritance rules to ensure consistency:

* **Adding to a guide:** If you add a prompt to a Guide, the prompt will automatically inherit the Guide's category, overriding any previous selection.
* **Inherited status:** While a prompt is part of a Guide, its category is inherited and cannot be manually changed. It must match the Guide.
* **Removing from a guide:** If a prompt is removed from a Guide, it retains the category it inherited from that Guide. You can then manually update it if necessary.

<br />
