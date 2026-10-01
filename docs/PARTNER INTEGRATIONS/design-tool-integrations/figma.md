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
<div class="rp-page">
  <div class="rp-overview">Import a Figma frame to create a stylized Recurly Engage web popup prompt that you can refine in the prompt editor.</div>
  <div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly plans</div>
  <div class="rp-toc">
    <a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
    <a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
    <a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
  </div>
</div>

### Prerequisites

<ul class="rp-list">
  <li>You must use a Figma account with a developer license, so you can generate an API key.</li>
  <li>You must create your design from a <a href="https://www.figma.com/community/file/1660045412615829580" target="_blank">Recurly Engage Figma template</a>.</li>
</ul>

### Limitations

<ul class="rp-list">
  <li>AI Figma Sync supports web popup prompts only. Other prompt types are not supported.</li>
  <li>Mapping accuracy depends on how closely the design follows the provided template. Changes to the template structure can reduce mapping reliability for elements such as legal text and call-to-action buttons.</li>
  <li>Recurly Engage supports a maximum of three buttons per prompt. Additional buttons might not map as expected.</li>
  <li><a href="https://www.figma.com/community/file/1660045412615829580" target="_blank">Templates</a> use a fixed medium popup size.</li>
</ul>

# Definition

<div class="rp-definition">AI Figma Sync lets you turn a Figma design into a styled Recurly Engage web popup prompt without manually rebuilding it. Paste a Figma frame link into Engage to map your styling and messaging into a draft that you can edit.</div>

The feature reads mapped fields (metadata that identifies where each element belongs) in Recurly Engage Figma templates. When you import, AI Figma Sync brings in your title, message, survey options, and buttons, and then translates your custom styles into Cascading Style Sheets (CSS) in the prompt editor.

# Key benefits

<div class="rp-benefits rp-benefits-2x2">
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-rocket" aria-hidden="true"></i></div>
    <strong>Faster launches</strong>
    <span>Start from a styled draft instead of a blank canvas.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-code" aria-hidden="true"></i></div>
    <strong>Lower technical barrier</strong>
    <span>Create brand-aligned prompts without hand-written CSS.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-palette" aria-hidden="true"></i></div>
    <strong>Brand consistency</strong>
    <span>Use approved Figma designs while preserving your styling.</span>
  </div>
  <div class="rp-benefit">
    <div class="rp-benefit-icon"><i class="fa-solid fa-pen-to-square" aria-hidden="true"></i></div>
    <strong>Flexible editing</strong>
    <span>Refine the result in Recurly Engage, or update the design in Figma and re-import it.</span>
  </div>
</div>

# Key details

## Connect Figma to Recurly Engage

Connect Figma with a developer API key. You only need to add this token once.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Open your Figma account settings</h4><p>In Figma, open your account settings and select the developer tab.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Generate an API key</h4><p>Generate an API key and copy it.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Find the Figma tile</h4><p>In Recurly Engage, open the integrations dashboard and find the Figma tile under <span style={{fontWeight: "bold"}}>Other</span>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Paste the key and connect</h4><p>Paste the API key into the plan token field, and then connect to Figma.</p></div>
  </div>
</div>

## Create your design from a template

Recurly Engage templates include mapped fields. These fields let Engage place your title, message, survey options, and buttons in the prompt editor when you import the design.

Make a copy of the <a href="https://www.figma.com/community/file/1660045412615829580" target="_blank">template file</a> before you edit it. The original template is shared and can't be edited directly.

You can customize the copy with your own:

* Colors, typography, padding, and spacing
* Element order and placement, including button placement, as long as the underlying button structure remains consistent with the mapping

Keep the design close to the template structure and include no more than three buttons to maintain reliable mapping.

## Copy the Figma frame link

Import a frame link, not a link to the full Figma file.

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Select the frame</h4><p>In Figma, select the frame you want to import, such as the desktop web dialog.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Confirm the URL</h4><p>Confirm that the browser URL updates to reflect the selected frame.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Copy the URL</h4><p>Copy the URL from the browser address bar.</p></div>
  </div>
</div>

## Import the design

<div class="rp-steps">
  <div class="rp-step">
    <div class="rp-step-num">1</div>
    <div><h4>Create a web popup prompt</h4><p>In Recurly Engage, go to <span style={{fontWeight: "bold"}}>Prompts</span> and create a web popup prompt.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">2</div>
    <div><h4>Start the import</h4><p>On the prompt detail page, select <span style={{fontWeight: "bold"}}>Import from Figma</span>.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">3</div>
    <div><h4>Paste the desktop frame link</h4><p>Paste your desktop frame link into the <span style={{fontWeight: "bold"}}>Desktop frame link</span> field. You must provide at least one frame link.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">4</div>
    <div><h4>Paste the mobile frame link</h4><p>If you have a separate mobile design, paste its frame link into the <span style={{fontWeight: "bold"}}>Mobile frame link</span> field. Otherwise, reuse the desktop frame link.</p></div>
  </div>
  <div class="rp-step">
    <div class="rp-step-num">5</div>
    <div><h4>Import</h4><p>Select <span style={{fontWeight: "bold"}}>Import</span>.</p></div>
  </div>
</div>

Processing typically takes about one minute. When processing finishes, the prompt editor opens with the imported text, mapped buttons, and generated custom CSS. View the generated styling in the **CSS** tab at the bottom of the prompt.

## Edit the imported prompt

Choose one of these approaches after importing:

* **Edit in Recurly Engage**: Update copy, replace the background image, adjust styling, or modify individual elements in the prompt editor.
* **Edit in Figma and re-import**: For a larger change or a redesign, update your Figma file and repeat the import process with the frame link.

## Import separate desktop and mobile designs

Recurly Engage imports desktop and mobile web designs separately. When you provide a mobile-specific frame link with the desktop frame link, Engage maps its fields to the prompt's mobile section.

<br />

<br />
