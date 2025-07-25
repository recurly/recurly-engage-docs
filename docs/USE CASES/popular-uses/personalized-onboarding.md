---
title: Personalized onboarding
excerpt: >-
  Configuration guide for the Personalized Onboarding use case, leveraging
  Journey guides to educate new users contextually.
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: See more popular uses
  pages:
    - type: basic
      slug: popular-uses
      title: Popular Uses
---
# Overview

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

Traditional onboarding tours interrupt the user flow with step-by-step callouts. The **Personalized Onboarding** Journey guide delivers prompts only for actions or sections the user hasn’t yet seen—and can span multiple visits—for a frictionless, contextual experience.

# Key benefits

* **Contextual guidance**: Show prompts only for features the user hasn’t accessed.
* **Multi-visit flexibility**: Space your onboarding steps across sessions to avoid overload.
* **Higher engagement**: Streamlined education that respects the user’s flow.

# Key details

Traditional approaches to onboarding new users include a step-by-step homepage tour with highlighted callouts to various features. This method may work for B2B, but B2C users often find it disruptive.

Recurly Engage’s Journey guide lets you predefine a sequence of prompts linked to key site elements. Each prompt fires only if the user hasn’t completed the associated action, and you can schedule them over multiple visits—resulting in a more user-friendly onboarding flow.

<Image align="center" className="border" border={true} src="https://files.readme.io/8e77a00-Screenshot_2024-04-19_at_1.33.00_PM.png" />

> 📘 Important
>
> Create usage trackers for your key features and content, then reference those trackers in your onboarding guide to target only first-time interactions.

## Guide

1. **Create** a new Guide (Settings > Guides) and **set** the type to **Journey**.
2. **Configure** the first prompt as a **Popup** targeting first-time visitors.
3. **Set** the CTA on that prompt to either trigger the feature directly (1-Click) or **redirect** to the relevant page.
4. **Add** a second prompt in the guide and schedule it for the user’s next visit.
5. **Add** a third prompt scheduled for a subsequent visit as needed.
6. **Target** the guide to the **Test Users** segment.
7. **Specify** the trigger conditions (e.g., specific page URLs or tracker events).
8. **Start** the Guide.
9. **Add** your User ID to **Test Users** (Settings > Users > Test Users).
10. **Verify** that each prompt appears in the correct order across visits.

> 📘 Important
>
> To experiment with different onboarding sequences, run an A/B test on your guide prompts.