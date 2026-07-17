---
title: Figma
excerpt: >-
  How to import a Figma design into Recurly Engage and generate a styled web
  popup prompt using AI Figma Sync.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Overview

Import a Figma frame to create a styled Recurly Engage web popup prompt that you can refine in the prompt editor.

## Required plan

AI Figma Sync is available to all Recurly Engage merchants. The feature is rolled out behind a feature flag and enabled across all accounts at release.

## Additional cost

AI Figma Sync is included with Recurly Engage at no additional cost.

# Prerequisites

Complete these steps before you import a design:

1. Use a Figma account with a developer license so you can generate an API key.
2. Create your design from a Recurly Engage Figma template.

# Limitations

- AI Figma Sync supports web popup prompts only. Other prompt types are not supported.
- Mapping accuracy depends on how closely the design follows the provided template. Changes to the template structure can reduce mapping reliability for elements such as legal text and call-to-action buttons.
- Recurly Engage supports a maximum of three buttons per prompt. Additional buttons might not map as expected.
- Templates use a fixed medium popup size.

# Definition

AI Figma Sync lets you turn a Figma design into a styled Recurly Engage web popup prompt without manually rebuilding it. Paste a Figma frame link into Engage to map your styling and messaging into a draft that you can edit.

The feature reads mapped fields (metadata that identifies where each element belongs) in Recurly Engage Figma templates. When you import, AI Figma Sync brings in your title, message, survey options, and buttons, then translates your custom styles into CSS in the prompt editor.

# Key benefits

- **Faster launches:** Start from a styled draft instead of a blank canvas.
- **Lower technical barrier:** Create brand-aligned prompts without hand-written CSS.
- **Brand consistency:** Use approved Figma designs while preserving your styling.
- **Flexible editing:** Refine the result in Recurly Engage or update the design in Figma and re-import it.

# Key details

## Connect Figma to Recurly Engage

Connect Figma with a developer API key. You only need to add this token once.

1. In Figma, open your account settings and select the developer tab.
2. Generate an API key and copy it.
3. In Recurly Engage, open the integrations dashboard and find the Figma tile under **Other**.
4. Paste the API key into the plan token field, then connect to Figma.

## Create your design from a template

Recurly Engage templates include mapped fields. These fields let Engage place your title, message, survey options, and buttons in the prompt editor when you import the design.

Make a copy of the template file before you edit it. The original template is shared and cannot be edited directly.

You can customize the copy with your own:

- Colors, typography, padding, and spacing
- Element order and placement, including button placement, as long as the underlying button structure remains consistent with the mapping

Keep the design close to the template structure and include no more than three buttons to maintain reliable mapping.

## Copy the Figma frame link

Import a frame link, not a link to the full Figma file.

1. In Figma, select the frame you want to import, such as the desktop web dialog.
2. Confirm that the browser URL updates to reflect the selected frame.
3. Copy the URL from the browser address bar.

## Import the design

1. In Recurly Engage, go to **Prompts** and create a web popup prompt.
2. On the prompt detail page, select **Import from Figma**.
3. Paste your desktop frame link into the **Desktop frame link** field. You must provide at least one frame link.
4. If you have a separate mobile design, paste its frame link into the **Mobile frame link** field. Otherwise, reuse the desktop frame link.
5. Select **Import**.

Processing typically takes about one minute. When processing finishes, the prompt editor opens with the imported text, mapped buttons, and generated custom CSS. View the generated styling in the **CSS** tab at the bottom of the prompt.

## Edit the imported prompt

Choose one of these approaches after importing:

- **Edit in Recurly Engage:** Update copy, replace the background image, adjust styling, or modify individual elements in the prompt editor.
- **Edit in Figma and re-import:** For a larger change or a redesign, update your Figma file and repeat the import process with the frame link.

## Import separate desktop and mobile designs

Recurly Engage imports desktop and mobile web designs separately. When you provide a mobile-specific frame link with the desktop frame link, Engage maps its fields to the prompt's mobile section.

# FAQs

The source content does not provide FAQs for AI Figma Sync.
