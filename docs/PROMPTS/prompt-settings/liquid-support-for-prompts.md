---
title: Liquid support for prompts
excerpt: >-
  A guide on how to use Liquid, a template language, to personalize prompts in
  Recurly Engage. It explains how to dynamically insert subscriber and account
  data into your prompts to create a more relevant and engaging user experience.
deprecated: false
hidden: false
metadata:
  description: >
    A guide on how to use Liquid, a template language, to personalize prompts in
    Recurly Engage. It explains how to dynamically insert subscriber and account
    data into your prompts to create a more relevant and engaging user
    experience.
  robots: index
---
<div class="rp-page">
  <div class="rp-overview">Recurly Engage supports Liquid, an open-source template language. Use it to pull data from your Recurly accounts directly into prompt text and create personalized messages, such as addressing a customer by name, referencing their current subscription plan, or reminding them of their renewal date.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

# Definition

<div class="rp-definition">A Liquid variable is a placeholder in your prompt text that Recurly Engage replaces with data for each user, so every user sees a personalized message.</div>

# Key benefits

<div class="rp-benefits rp-benefits-2x2">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-user-pen" aria-hidden="true"></i></div>
    <strong>Personalized messaging</strong>
    <span>Move beyond generic prompts by dynamically inserting user-specific data, such as first names, subscription details, or renewal dates, for a more relevant and engaging experience.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-bullseye" aria-hidden="true"></i></div>
    <strong>Increased relevance</strong>
    <span>Prompts that speak directly to a user's situation are more likely to be acted on. A prompt that mentions a customer's billing amount or plan name is more effective than a generic one.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-layer-group" aria-hidden="true"></i></div>
    <strong>Fewer prompts to manage</strong>
    <span>Instead of creating multiple prompts for different user segments, use a single prompt with Liquid variables to show unique content to each user. This saves time and reduces management overhead.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-arrow-trend-up" aria-hidden="true"></i></div>
    <strong>Better engagement</strong>
    <span>Timely, personalized information improves user interaction and drives better outcomes, whether you're encouraging a plan upgrade or preventing involuntary churn.</span>
  </div>
</div>

# Key details

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open Prompts</h4><p>Go to the <span style={{fontWeight: "bold"}}>Prompts</span> section in Pulse, the Recurly Engage management console.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Create or select a prompt</h4><p>Create a new prompt, or select an existing one you want to edit.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Edit the prompt design</h4><p>Click into the text field you want to personalize.</p></div>
  </div>
</div>

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Insert Liquid variables</h4><p>Add Liquid variables to the text field using the delimiters described below.</p></div>
  </div>
</div>

Insert Liquid variables using the `{{ }}` delimiters. The system automatically suggests available variables from your Recurly account data as you type. All Liquid functionality is supported, including control flow, iterators (loops), and assignments.

## Variable types

There are two primary types of Liquid variables you can use:

* **User trait variables**: These variables come from user data you have imported. Use the `user.` prefix, such as `{{user.first_name}}`.
* **Data source variables**: These variables are available if you have connected your Recurly account as a data source.

For more information on connecting data sources, see the <a href="https://docs.recurly.com/recurly-engage/docs/data-sources" target="_blank">Data Sources documentation</a>.

## Example: personalize a renewal message

You can create a prompt that displays a customer's name and current plan with the following code:

Hello `{{ user.first_name }}`, your `{{ subscription.plan.name }}` plan is set to renew on `{{ subscription.renews_at }}`.

This renders a personalized message for each user, such as:

`Hello Jane, your Pro plan is set to renew on 09/30/2025.`

<div class="rp-callout rp-callout-note">
  <div><strong><i class="fa-solid fa-circle-info" aria-hidden="true"></i> Note</strong>The system shows only the variables available for the targeted user. If a variable, such as <code>user.first_name</code>, isn't available for a specific user, the field appears blank.</div>
</div>

## Set default values

When you use Liquid variables, the data field you're referencing (for example, a customer's plan type) might not be available for a specific user. By default, the field appears blank.

To keep your messages clean and professional, use the default filter to specify a fallback value. Apply the filter with a vertical pipe (`|`) followed by `default: 'Your Fallback Value'`.

**Example:**

`Hello {{ user.first_name | default: 'there' }}, your {{ subscription.plan.name }} plan is set to renew on {{ subscription.renews_at }}.`

<br />

<br />
