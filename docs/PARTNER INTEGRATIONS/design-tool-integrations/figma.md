---
title: Figma
excerpt: >-
  A guide to the Recurly Engage and Figma integration. It details how to upload
  a Figma design and have it automatically translated into an editable Engage
  prompt, letting you go from design to live campaign without a developer.
deprecated: false
hidden: true
metadata:
  robots: index
---
# Overview

The Figma integration lets you turn a finished Figma design into a Recurly Engage prompt automatically. Upload a Figma file or paste a Figma URL from within the Engage console, and Engage generates an editable prompt — copy, calls to action, colors, and layout intent included — that you can review, adjust, and publish yourself.

### Required plan

This feature is included in all Recurly Engage subscription plans, but requires that merchants have a Figma developer plan .

### <br />Prerequisites & limitations

Company or App Administrator permissions.<br />A completed Figma design exported as a single frame or single page. Multi-frame and multi-page files are not supported in this release.<br />Figma is the only supported design tool at this time.<br />Definition<br />The Recurly Engage Figma integration removes the manual handoff between design and campaign setup. Instead of a developer or implementation specialist rebuilding a Figma mockup in Engage by hand, the integration interprets your design and generates a matching prompt for you. You keep full control at the review step — nothing publishes without your explicit confirmation — so you can launch on-brand campaigns in minutes rather than days or weeks.<br />Key benefits

Faster time to launch: Go from a finished design to a live prompt in minutes, eliminating the design-to-development queue that traditionally delays campaigns.
No developer required: Marketers and designers can complete the entire workflow themselves inside the Engage console, with no technical intermediary.
Higher design fidelity: Your original copy, CTA, color, and layout intent carry through to the generated prompt, reducing the interpretation errors that come with manual rebuilding.
Full editability: Every generated field is editable in the standard Engage editor before you publish — nothing is locked or read-only.

Key details
Translating a Figma design to a prompt
The Figma integration analyzes your uploaded design and produces a structured Engage prompt with populated copy, CTA text, color values, and layout intent. The generated output maps to the same fields you would configure manually in the Engage prompt editor, so you can refine it exactly as you would any other prompt.
How it works

In the Engage console, select New Campaign or Import from Figma.
Upload a Figma file or paste a Figma URL. Engage validates the file format before continuing.
Engage processes the design and displays a loading state while the prompt is generated.
The generated prompt opens in the Engage editor. Review all fields — copy, CTA, colors, and layout.
Make any edits you need, then select Publish to take the prompt live, or Save as Draft to return to it later from the standard Engage drafts view.

Supported input

File upload: Upload a Figma design file directly in the Engage console.
URL input: Paste a link to a Figma file as an alternative to uploading.
Single frame or page only: Phase 1 supports single-frame or single-page exports. Multi-frame and multi-page files are not yet supported.

Reviewing and publishing
Merchant approval is required before anything goes live — the integration never auto-publishes. After review, you can:

Publish the prompt directly to Engage in a single action.
Save as Draft to store the generated or edited prompt for later, accessible from the standard Engage drafts view.

Error states and recovery
If translation can't complete, Engage shows a clear, non-technical message with a path forward so you're never left at a dead end:

Unsupported or malformed file: Engage flags the format error before translation begins.
Translation timeout or failure: You can retry the translation, switch to manual prompt entry, or contact support.
Partial translation: Any fields the design didn't populate are clearly flagged in the editor for manual completion.
No design content detected: If an uploaded frame is blank or has no interpretable elements, Engage notifies you with guidance on supported design inputs.
