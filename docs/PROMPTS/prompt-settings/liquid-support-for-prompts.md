---
title: Liquid support for prompts
deprecated: false
hidden: true
metadata:
  description: >
    A guide on how to use Liquid, a template language, to personalize prompts in
    Recurly Engage. It explains how to dynamically insert subscriber and account
    data into your prompts to create a more relevant and engaging user
    experience.
  robots: index
---
# Definition

Recurly Engage now supports Liquid, a powerful and flexible open-source template language. With this new feature, you can easily pull and insert data from your Recurly accounts directly into the text of your prompts. This allows you to create highly personalized messages, such as addressing a customer by name, referencing their current subscription plan, or reminding them of their renewal date.

# Key benefits

* **Personalized Messaging**: Move beyond generic prompts by dynamically injecting user-specific data, such as first names, subscription details, or renewal dates. This creates a more relevant and engaging experience for your audience.
* **Increased Relevance**: Prompts that speak directly to the user's situation are more likely to be acted upon. For example, a prompt that mentions a customer's specific billing amount or plan name will be more effective than a generic one.
* **Streamlined Workflows**: Instead of creating multiple prompts for different user segments, you can now use a single prompt with Liquid variables to display unique content to each user. This saves time and reduces management overhead.
* **Enhanced Engagement:** By providing timely and personalized information, you can improve user interaction and drive better outcomes, whether it's encouraging a plan upgrade or preventing involuntary churn.

# Key details

1. **Go to the Prompts** section in Pulse, the Recurly Engage management console.
2. **Create a new prompt** or select an existing one you wish to edit.
3. **Edit the prompt design** by clicking into the text field you want to personalize.
4. **Insert Liquid variables** using the `{{ }}` delimiters. The system will automatically suggest available variables from your Recurly account data as you type.

**Example:**

There are two primary types of Liquid variables you can use:

* **User trait variables:** These variables come from user data you have imported. Use the `user.`prefix, such as `{{user.first_name}}`.
* **Data source variables:** These variables are available if you have connected your Recurly account as a data source.

For more information on connecting data sources, refer to our [Data Sources documentation](https://docs.recurly.com/recurly-engage/docs/data-sources).

**Example:** 

You can create a prompt that displays a customer's name and current plan with the following code:

Hello `{{ user.first_name }}`, your `{{ subscription.plan.name }}` plan is set to renew on `{{ subscription.renews_at }}`.

This will render a personalized message for each user, such as:

`Hello Jane, your Pro plan is set to renew on 09/30/2025.`

**Note: **The system will only show variables available for the targeted user. If a variable, such as `user.first_name`, is not available for a specific user, the field will simply appear blank.
