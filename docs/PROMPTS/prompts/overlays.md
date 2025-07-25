---
title: Overlay prompts
excerpt: >-
  Details on creating and managing overlay prompts—interstitials, pop-ups, video
  overlays, notifications, and bottom banners—in Recurly Engage.
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

Overlay prompts float above your site or app content. Some (interstitial, pop-up, video) block interaction until dismissed, while others (notification, bottom banner) allow continued use.

### Video

<Embed url="https://www.loom.com/embed/37d0ba60b71e4444be6ddcfe14e56add?sid=77dddded-5f13-4cd0-899b-9105cde9f286" href="https://www.loom.com/embed/37d0ba60b71e4444be6ddcfe14e56add?sid=77dddded-5f13-4cd0-899b-9105cde9f286" typeOfEmbed="iframe" height="480px" width="100%" iframe="true" />

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

An **overlay prompt** is an in-app message rendered atop your interface to capture user attention with varying levels of interruption.

# Key benefits

* **Maximum visibility**: Command user focus at critical moments.
* **Format flexibility**: Choose from full-screen interstitials to subtle notifications.
* **Custom behavior**: Control size, timing, and dismissal for optimal UX.

# Key details

Overlay prompts appear above your content and may fully block interaction (interstitial, pop-up, video) or sit unobtrusively (notification, bottom banner).

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/eb0dc55-image.png" />

### Interstitial

Full-screen or near–full-screen prompts shown before or after page load. They respect device aspect ratios and safe-area margins to keep key content visible.

![](https://files.readme.io/0ab0f6f-image.png)

### Pop-up

Overlay windows featuring an image, text, and one or more calls to action. Users can dismiss them if configured.

* **Sizes**: 1200×800, 960×640, or 750×500 (configurable).

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/d2cb3d2-image.png" />

### Video

Media-rich overlays combining video playback with text and actionable buttons.

* **Size**: 1100×619 (configurable).

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/5b26f7a-image.png" />

### Notification

Subtle corner prompts with a brief headline, background image, and a single call to action—ideal for low-impact messaging.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/45dbbcc-image.png" />

### Bottom banner

Banner prompts spanning the bottom of the viewport, displaying text and imagery without fully blocking content.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/1500b39-image.png" />

## Step-by-step

1. **Go** to **Prompts > +New Prompt**.
2. Select **Desktop and Mobile**, then choose your overlay type (e.g., **Pop-up**).
3. **Add** a name and optional description.
4. **Add** one or more segments: Adding the **Test Users** segment allows you to view the prompt as if you were a targeted user.
5. **Add** a trigger: Learn more about triggers [here](triggers).
6. **Set** a limit (optional): There are multiple types of limits; see [limits](limits-1).
7. **Set** a schedule (optional): **Click** [Schedule](schedule-1) to configure timing.
8. **Set** an action (optional): **Define** post-click behavior via [Actions](actions-1).
9. **Select** **Edit prompt design** to design the prompt.
10. Tinker with settings in the preview—when done, **click** **Continue**.
11. **Preview** your prompt on your live site.
12. When satisfied, **click** **Save** and **set** status to **Start**.
13. **Test** the prompt: Validate your setup with the **Test Users** segment; see the [test user guide](test-users).

### Activate the prompt

Activation has two phases:

1. **Review phase**: launch to **Test Users** for final QA.
2. **Active phase**: attach all target segments for full-scale deployment.

You can **pause**, **restart**, or **end** a prompt at any time—just end any active experiment first.