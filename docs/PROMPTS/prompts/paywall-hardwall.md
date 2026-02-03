---
title: Paywall & hardwall
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

The Recurly Engage Dynamic Paywall & hardwall prompt types are specifically designed for publishers and content providers seeking to manage and monetize access to their digital assets. This solution effectively controls reader access, encouraging user sign-ups and subscriptions.

The solution allows a user to view a limited number of complimentary articles or paragraphs before requiring paid access. The content is typically visually obscured and interaction-blocked by an intrusive prompt that prevents scrolling past the designated limit.

# Key benefits

* **Maximized Content Value**: Provides a proven method to convert frequent readers into paying subscribers by blocking the remainder of premium article content.
* **Flexible Access Control**: Content providers can define the precise number of complimentary paragraphs or articles a user is permitted to view, offering granular control over the pre-access user experience.
* **Drives User Registration**: Creates a clear incentive for users to sign up or register once they have utilized their introductory content quota.
* **Usage Abuse Prevention:** Includes critical cross-device user tracking capabilities to monitor and prevent unauthorized excess consumption of free content across various devices and browsing modes.

<br />

# Key Steps

## Step 1: Add a new usage tracker:

* Navigate to Settings > Usage Tracking
* Select “+ Add new tracker”
  * Fill out the required fields for Name, Label, Description. Select the Page tracker type, enter the relevant url path. Adding an * after the last backslash will enable tracking for any url path after the entered input.
* Check the “Use as paywall tracker” select button.

<Image align="center" border={false} src="https://files.readme.io/561bbcb28f9202306e6c0e2a1b687e67798a766f508e25df00b1b35c85fd0681-paywall_tracker.png" />

## Step 2: Create a zone

You will need to create a zone to define where the content is getting blocked, and where the prompt will appear.

* Navigate to Settings > Zones
  * Select the New Zone button
  * Enter the associated information for your zone. Your zone is the element where you would like to start hiding your content.

## Step 3: Create a new prompt

* Create a New Prompt Navigate to the main Prompts screen in your dashboard and click the + New Prompt button.
* Choose the Horizontal prompt type.
* In the Edit Prompt Design view, scroll through the configuration options to locate the Paywall accordion menu.
* Add the zone you created
* Enable and Configure Check the box labeled Enable paywall. Enter the required information for your prompt.
  Select Settings for the paywall
  * Paywall tracker: The usage tracker created from Step 1.
  * Free visits: The number of visits for content the user is allowed to access before the paywall is enabled.
  * Zone to block: The area that will be obscured.
* Block method: The way that the content will be removed or obscured from the page
  * Blur: the content will remain on the page, but CSS styling will prevent it from being readable.
  * Hide: The content will be hidden, but not removed from the page.
  * Strip text: The content will be removed from the DOM.
  * Custom CSS: Enter your own custom css to hide the content.
* Apply to elements: The types of elements on your page that will be targeted for hiding or removal.
* Elements to allow: How many paragraphs or pieces of content the user is allowed to read before the paywall blocks the rest.
* Save and Activate Once your limits are set and your copy is finalized, save your prompt to apply the paywall logic to your site.

<Image align="center" border={false} src="https://files.readme.io/302f616bd65719d846476778ae5d4ab3ee543349ef49b89b1755c179c7bf2b8a-paywall_config.png" />
