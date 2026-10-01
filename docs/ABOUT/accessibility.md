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
<div class="rp-page">
  <div class="rp-overview">Recurly Engage prompts are designed to meet key aspects of the Web Content Accessibility Guidelines (WCAG). The goal is that all users, including those who use assistive technologies, can perceive, operate, and understand prompt content.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

# Definition

<div class="rp-definition">This page outlines how Recurly Engage applies the four WCAG principles (Perceivable, Operable, Understandable, and Robust) within prompt designs and interactions.</div>

# Key benefits

<div class="rp-benefits">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-ear-listen" aria-hidden="true"></i></div>
    <strong>Screen reader compatibility</strong>
    <span>All prompt text is rendered as live text, not images.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-keyboard" aria-hidden="true"></i></div>
    <strong>Keyboard navigation</strong>
    <span>Prompts and buttons fully support keyboard focus and actions.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-shield-heart" aria-hidden="true"></i></div>
    <strong>Non-flashing content</strong>
    <span>Default designs avoid flashing that could trigger seizures.</span>
  </div>
</div>

# Key details

Recurly Engage monitors and implements the following WCAG guidelines for prompt components. To get help integrating prompts into a site that is already WCAG-compliant, contact your Customer Success Manager or <a href="mailto:support@recurly.com">[support@recurly.com](mailto:support@recurly.com)</a>.

## Perceivable

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Guideline</td><td>How Recurly Engage meets it</td></tr>
  <tr><td>Text alternatives</td><td>All prompt text is rendered as HyperText Markup Language (HTML) text, not composited into images, which ensures compatibility with screen readers. Background images used for styling may include an optional text alternative.</td></tr>
  <tr><td>Time-based media</td><td>Not applicable to prompt interactions.</td></tr>
  <tr><td>Adaptable</td><td>Not applicable for standard prompt configurations.</td></tr>
  <tr><td>Distinguishable</td><td>Designers can customize colors, contrast, and spacing in the prompt editor to meet visual clarity requirements.</td></tr>
</table>

## Operable

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Guideline</td><td>How Recurly Engage meets it</td></tr>
  <tr><td>Keyboard accessible</td><td>All buttons and interactive elements support keyboard focus, activation with Enter or Space, and a logical tab order. You can apply custom HTML and Cascading Style Sheets (CSS) modifications for non-standard elements.</td></tr>
  <tr><td>Enough time</td><td>You can configure prompts with timers to give users enough time to read and interact. Timers may be paused or extended.</td></tr>
  <tr><td>Seizures</td><td>Default prompt designs don't include rapid flashing or animations that could induce seizures.</td></tr>
  <tr><td>Navigable</td><td>Prompts integrate into existing page layouts without disrupting global navigation. Designers can adjust focus behavior to ensure a logical flow.</td></tr>
</table>

## Understandable

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Guideline</td><td>How Recurly Engage meets it</td></tr>
  <tr><td>Readable</td><td>Prompt text is fully customizable in the console, so you can write clear, plain-language messages.</td></tr>
  <tr><td>Predictable</td><td>Prompt interactions don't cause unexpected context changes. Designers should make sure any custom behaviors align with page-level consistency guidelines.</td></tr>
  <tr><td>Input assistance</td><td>If a prompt collects user input (for example, survey responses), error messages appear inline and clear when the input is corrected.</td></tr>
</table>

## Robust

<table class="rp-gw-table">
  <tr class="rp-thead-row"><td>Guideline</td><td>How Recurly Engage meets it</td></tr>
  <tr><td>Compatible</td><td>Recurly Engage prompts use standard, well-formed HTML elements. Custom HTML and CSS must also follow best practices to maintain accessibility compliance.</td></tr>
</table>
