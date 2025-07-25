---
title: Create a pop-up
excerpt: >-
  Steps to create and configure a pop-up prompt in Recurly Engage, from initial
  setup to live deployment.
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
          You must have <strong>Company</strong>, <strong>App Administrator</strong>, or <strong>App Member</strong> permissions in Recurly Engage.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

A **pop-up** is a modal prompt that appears over your site’s content to deliver messages, offers, or calls to action. Pop-ups are one of four prompt types available in the Prompts console.

# Key benefits

* **High visibility**: Ensures critical messages capture user attention.
* **Targeted delivery**: Combine with segments and triggers to reach the right audience.
* **Easy customization**: Design, schedule, and limit frequency—all within the console.

# Key details

In this guide, you’ll create a browser pop-up. To start:

1. **Go** to Prompts > New Prompt (**+** sign).

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/c46f2ae-Screenshot_2024-05-23_at_16.31.29.png" />

2. **Select** “Desktop and Mobile” then **choose** “Pop-up”.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/66c5557-Screenshot_2024-05-23_at_16.32.40.png" />

3. **Add** a name and description.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/6d1cd5a-Screenshot_2024-05-23_at_16.34.02.png" />

4. **Add** one or more segments

Use segments to control who sees the prompt. For testing, add the **Test Users** segment so you can preview as a specific user group.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/c389c63-Screenshot_2024-05-23_at_16.35.19.png" />

<br />

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/9acb5c6-Screenshot_2024-05-23_at_16.36.08.png" />

<br />

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/8b788cc-Screenshot_2024-05-23_at_16.37.00.png" />

<br />

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/74f4509-Screenshot_2024-05-23_at_16.37.51.png" />

5. **Add** a trigger: **Define** when and where the pop-up appears. Selecting **All Pages** shows it to every visitor.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/035de64-Screenshot_2024-05-23_at_16.38.49.png" />

<br />

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/7bfe1b7-Screenshot_2024-05-23_at_16.39.44.png" />

<br />

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/371bb5f-Screenshot_2024-05-23_at_16.40.39.png" />

<br />

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/21823b1-Screenshot_2024-05-23_at_16.41.38.png" />

6. **Set** a limit (optional).

Control how many times or how many users can see the pop-up by choosing from available limit types.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/f44ce1a-Screenshot_2024-05-23_at_16.43.11.png" />

<br />

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/ecd3c1c-Screenshot_2024-05-23_at_16.44.28.png" />

7. **Set** a schedule (optional): **Schedule** start and end dates or times for your pop-up campaign.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/3ea543f-Screenshot_2024-05-24_at_16.13.26.png" />

<br />

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/8779e53-Screenshot_2024-05-24_at_16.14.16.png" />

8. **Set** an action (optional): **Redirect** users after they interact with the pop-up by configuring **Website Actions**.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/2d57a20-Screenshot_2024-05-24_at_16.16.39.png" />

<br />

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/e353f8a-Screenshot_2024-05-24_at_17.13.47.png" />

9. **Click** **Edit** to open the designer and tweak styles, copy, and layout.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/e5df649-Screenshot_2024-05-24_at_17.15.01.png" />

10. **Design** the prompt: **Customize** colors, text, buttons, and images. **Preview** updates live. For sample background images, **download** [this ZIP file](https://docs.redfast.com/images/samples.zip).

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/67fe571-Screenshot_2024-05-24_at_17.20.04.png" />

11. **Preview** your prompt: Once saved, **preview** your pop-up on your live site to ensure it looks and behaves as expected.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/23d54d9-Screenshot_2024-05-24_at_17.23.01.png" />

<br />

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/d5b09d4-Screenshot_2024-05-24_at_17.23.34.png" />

11. When you’re happy with your design, **click** **Save**, then **set** the status to **Start**. Your pop-up is now live.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/72e4d57-Screenshot_2024-05-24_at_17.24.40.png" />

12. **Test** the prompt: Before full rollout, **validate** your pop-up using test users. **See** the [test users guide](test-users) for step-by-step instructions.