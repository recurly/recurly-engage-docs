---
title: Figma
excerpt: >-
  How to import a Figma design into Recurly Engage and generate a styled web
  popup prompt using AI Figma Sync.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

## Prerequisites

- A Recurly Engage account with the AI Figma Sync feature enabled
- A Figma account with a developer license (required to generate an API key)
- A design built from one of Recurly Engage's provided Figma templates

## Limitations

- AI Figma Sync is available for web popup prompts only. It isn't supported for other prompt types yet.
- Mapping accuracy depends on staying close to the provided templates. The further a design deviates from the template structure, the less reliably the AI maps elements like legal text and call-to-action buttons.
- Recurly Engage supports a maximum of three buttons per prompt. Designs with additional buttons may not map as expected.
- Templates use a fixed medium popup size.

# Definition

AI Figma Sync lets you turn a Figma design into a styled Recurly Engage web popup prompt without manually rebuilding it. Instead of copying colors, fonts, and copy by hand — or writing CSS — you paste a Figma frame link into Engage, and the AI maps your brand styling and messaging into a ready-to-edit draft.

The feature works by reading the metadata mapped to fields in Recurly Engage's Figma templates. When you import, the AI pulls in your title, messaging, survey options, and buttons, translates your custom styles into CSS, and drops everything into the right place in the prompt editor.<br />

# Key benefits

- **Faster launches:** Start from a styled draft instead of a blank canvas, so campaigns go live in less time
- **Lower technical barrier:** Marketing teams can produce brand-aligned prompts without a front-end developer or hand-written CSS
- **Brand consistency:&#x20;**&#x41;pproved Figma designs translate into the final experience while preserving your styling
- **Flexible editing:** Refine the result directly in Engage, or make changes in Figma and re-import

# Key details

## Step 1 — Connect Figma to Recurly Engage

Before you can import, connect your Figma account to Engage using a developer API key. You only need to enter this token once to complete the integration.

1. In Figma, open your account settings and go to the developer tab
2. Generate an API key and copy it
3. In Recurly Engage, go to the integrations dashboard and find the Figma tile under Other
4. Paste your API key into the plan token field and connect to Figma

## Step 2 — Build your design from a template

Start from one of the Figma templates Recurly Engage provides. The templates include mapped fields — behind-the-scenes metadata that tells Engage where each element belongs, so your title, messaging, survey options, and buttons land in the right place on import.

Because the templates are shared, you can't edit them directly. Make a copy of the template file first, then build your design in the copy. This keeps the original templates intact for everyone.

When customizing, you can:

- Apply your own colors, typography, padding, and spacing
- Reorder or reposition elements — including moving buttons to different locations — as long as the underlying button structure stays consistent with the mapping

To keep mapping reliable, stay as close to the template structure as possible and don't add more than three buttons.

## Step 3 — Copy your Figma frame link

Recurly Engage imports from a frame link rather than a whole file.

1. In Figma, click the frame you want to import (for example, the desktop web dialog)
2. Notice that your browser's URL changes to reflect the selected frame
3. Copy that URL from your browser's address bar

## Step 4 — Import the design into Recurly Engage

1. In Recurly Engage, go to Prompts and create a new web popup prompt<br />On the prompt detail page, select Import from Figma
2. Paste your desktop frame link into the Desktop frame link field. At least one link is required.
3. If you have a separate mobile design, paste its frame link into the Mobile frame link field. If you don't, you can reuse your desktop frame link.
4. Select Import

Processing typically takes about a minute. When it's done, your prompt editor opens with the imported design — mapped buttons, text, and generated custom CSS all in place. You can view the generated styling in the CSS tab at the bottom of the prompt.

## <br />Editing after import

Once your design is imported, you have two ways to make changes:

- **Edit in Recurly Engage:** Update copy, swap the background image, adjust styling, and tweak individual elements directly in the prompt editor
- **Edit in Figma and re-import:&#x20;**&#x46;or larger changes or a full redesign, update your Figma file, then repeat the import steps. Copy the frame link again, open the import modal, and run another import.

## Desktop and mobile designs

Desktop and mobile web are imported separately. If you have a mobile-specific design, import it at the same time as your desktop design, and its fields map to the mobile section of the prompt.
