---
title: Accessibility
excerpt: >-
  Accessibility compliance guidelines for Recurly Engage prompts, aligned with
  WCAG standards.
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

Recurly Engage prompts are designed to meet key aspects of the Web Content Accessibility Guidelines (WCAG), ensuring that all users—including those using assistive technologies—can perceive, operate, and understand prompt content.

# Definition

The **Accessibility** section outlines how Recurly Engage implements WCAG principles—Perceivable, Operable, Understandable, and Robust—within prompt designs and interactions.

# Key benefits

* **Screen reader compatibility**: All prompt text is rendered as live text, not images.
* **Keyboard navigation**: Prompts and buttons fully support keyboard focus and actions.
* **Non-flashing content**: Default designs avoid flashing that could trigger seizures.

# Key details

Recurly Engage monitors and implements the following WCAG guidelines for prompt components. Contact your Customer Success Manager for help integrating prompts into an already WCAG-compliant site.

## Perceivable

### Text alternatives

All prompt text is rendered as HTML text (not composited into images), ensuring compatibility with screen readers. Background images used for styling may include an optional text alternative.

### Time-based media

Not applicable to prompt interactions.

### Adaptable

Not applicable for standard prompt configurations.

### Distinguishable

Designers can customize colors, contrast, and spacing in the prompt editor to meet visual clarity requirements.

## Operable

### Keyboard accessible

All buttons and interactive elements support keyboard focus, activation via Enter/Space, and logical tab order. Custom HTML/CSS modifications may be applied for non-standard elements.

### Enough time

Prompts with timers can be configured to allow sufficient time for users to read and interact, and timers may be paused or extended.

### Seizures

Default prompt designs do not include rapid flashing or animations that could induce seizures.

### Navigable

Prompts integrate into existing page layouts without disrupting global navigation. Designers can adjust focus behavior to ensure a logical flow.

## Understandable

### Readable

Prompt text is fully customizable via the console, allowing clear, plain-language messaging.

### Predictable

Prompt interactions do not cause unexpected context changes. Designers should ensure any custom behaviors align with page-level consistency guidelines.

### Input assistance

If a prompt collects user input (e.g., survey responses), error messages appear inline and are cleared when input is corrected.

## Robust

### Compatible

Recurly Engage prompts use standard, well-formed HTML elements. Custom HTML/CSS must also adhere to best practices to maintain accessibility compliance.