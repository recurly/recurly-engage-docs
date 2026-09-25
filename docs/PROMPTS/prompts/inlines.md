---
title: Inline prompts
excerpt: >-
  Comprehensive guide to creating and managing inline prompts—horizontal,
  vertical, tile, and text-only—using defined zones in Recurly Engage.
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
<div class="rp-overview">Inline prompts let you surface targeted messages directly within your site or app's layout instead of as a pop-up or overlay. Assign a prompt to a zone, pick from four inline styles, and choose how multiple prompts in the same zone render—stacked, listed, or in a slider. Once you've built a prompt in the dashboard, you can drop its zone into your page with the Live Tool or a single line of code.</div>

<Embed title="" typeOfEmbed="iframe" url="https://www.loom.com/embed/0b567941dcf24629b1c053d4900ff0d3?sid=0d2335cd-d92d-4fcd-8438-3a35c781d0ca" height="480px" width="100%" href="https://www.loom.com/embed/0b567941dcf24629b1c053d4900ff0d3?sid=0d2335cd-d92d-4fcd-8438-3a35c781d0ca" />
<div class="rp-plan"><i class="fa-solid fa-key" aria-hidden="true"></i> Available on all Recurly Engage plans</div>
<div class="rp-toc">
<a class="rp-toc-pill" href="#definition"><span class="rp-toc-num">1</span>Definition</a>
<a class="rp-toc-pill" href="#key-benefits"><span class="rp-toc-num">2</span>Key benefits</a>
<a class="rp-toc-pill" href="#key-details"><span class="rp-toc-num">3</span>Key details</a>
<a class="rp-toc-pill" href="#step-by-step-guide"><span class="rp-toc-num">4</span>Step-by-step guide</a>
<a class="rp-toc-pill" href="#integration"><span class="rp-toc-num">5</span>Integration</a>
<a class="rp-toc-pill" href="#tips-and-tricks"><span class="rp-toc-num">6</span>Tips and tricks</a>
</div>
</div>

### Prerequisites

<ul class="rp-list">
<li>Company, App Administrator, or App Member permissions in Recurly Engage.</li>
</ul>

# Definition

<div class="rp-definition">An inline prompt is a message that renders inside a defined zone on your page, rather than as a pop-up or overlay. Four styles are available—horizontal banners, vertical panels, tiles, and text-only bars—so you can match the format to where it sits in your layout.</div>

# Key benefits

<div class="rp-benefits">
<div class="rp-benefit"><div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div><strong>Contextual placement</strong><span>Deliver messages directly within your page for higher relevance.</span></div>
<div class="rp-benefit"><div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div><strong>Versatile formats</strong><span>Choose from four inline styles to suit any design.</span></div>
<div class="rp-benefit"><div class="rp-benefit-icon"><i class="fa-solid fa-circle-check" aria-hidden="true"></i></div><strong>Dynamic sequencing</strong><span>Render multiple items per zone in stack, list, or slider mode.</span></div>
</div>

# Key details

These four prompt types occupy defined zones on your site or application alongside your content—that's where the name "inline" comes from.


<Image src="https://files.readme.io/3306b54-Screenshot_2024-04-18_193019.png" align="center" width="75%" border={true} />


Inline prompts live in <a href="zones" target="_blank">zones</a>. Any prompt assigned to a zone appears in that location—for example, a horizontal banner in the Web Featured zone.


<Image src="https://files.readme.io/e0c5481-Screenshot_2024-04-18_191758.png" align="center" width="75%" border={true} />


A single zone can render multiple items of the same type in one of three modes:

<ul class="rp-list">
<li><strong>Stack</strong>: items overlap; each new item appears after the prior one is dismissed.</li>
<li><strong>List</strong>: items display side by side, ideal for showing a row of personalized recommendations.</li>
<li><strong>Slider</strong>: a carousel showing one item at a time, with optional bullet indicators or auto-rotation.</li>
</ul>

## Horizontal

A wide banner with a landscape orientation that spans the width of your content area or screen edge-to-edge. Commonly placed at the top or bottom of pages, it can include a call-to-action button and hide itself on click or remain visible.

**Recommended ratios**: 2×1, 4×1, **6×1**, 8×1, 10×1.


<Image src="https://files.readme.io/994d3cd-image.png" align="center" width="75%" border={true} />


## Vertical

A tall panel with a portrait orientation, typically along the left or right edge of your layout. Like horizontals, it may include buttons and can be timed or dismissed with a click.

**Recommended ratios**: 1×2, **1×3**, 1×4.


<Image src="https://files.readme.io/a1fb469-image.png" align="center" width="75%" border={true} />


## Tile

A square or rectangular zone—perfect for grid layouts. Tiles display media and text, and can be closed or persist after interaction.

**Recommended ratios**: 1×1, 4×3, 16×9.


<Image src="https://files.readme.io/5729a7f-image.png" align="center" width="75%" border={true} />


## Text-only

A clickable text bar without images, useful for simple announcements or links. It can be configured to hide on click or remain in view.

**Recommended ratios**: 6×1, 8×1, 10×1.


<Image src="https://files.readme.io/392d0bc-image.png" align="center" width="75%" border={true} />


# Step-by-step guide

Follow these steps to build and publish your first inline prompt.

<div class="rp-steps">
<div class="rp-step"><div class="rp-step-num">1</div><div><h4>Create a zone</h4><p>Go to <strong>Settings > Zones > New Zone</strong>, then name the zone (no spaces) and choose its placement—for example, "Home Page Top Banner."</p></div></div>
</div>


<Image src="https://files.readme.io/0e07cb5-image.png" align="center" width="75%" border={true} />



<Image src="https://files.readme.io/60a9382-inline2.png" align="center" width="75%" border={true} />


<div class="rp-steps">
<div class="rp-step"><div class="rp-step-num">2</div><div><h4>Build an inline prompt</h4><p>Go to <strong>Prompts > New Prompt</strong>, choose <strong>Desktop and Mobile</strong>, then select <strong>Horizontal</strong> (or the inline type you want).</p></div></div>
</div>


<Image src="https://files.readme.io/564d84a-image.png" align="center" width="75%" border={true} />


Enter a name and description, assign the prompt to your new zone, then select <strong>Submit</strong>.


<Image src="https://files.readme.io/664a781-image.png" align="center" width="75%" border={true} />



<Image src="https://files.readme.io/c8c3561-image.png" align="center" width="75%" border={true} />


Configure segments, limits (optional), schedule (optional), and actions, then select <strong>Edit prompt design</strong> to customize visuals and copy.


<Image src="https://files.readme.io/6a6227a-Screenshot_2024-04-22_173653.png" align="center" width="75%" border={true} />


Tweak the settings in the designer and preview your changes live. You can download sample backgrounds <a href="/images/samples.zip" target="_blank">here</a>.


<Image src="https://files.readme.io/0d80810-Screenshot_2024-04-22_174308.png" align="center" width="75%" border={true} />


Select <strong>Publish</strong> to make the prompt live.


<Image src="https://files.readme.io/a55eac9-Screenshot_2024-04-22_174752.png" align="center" width="75%" border={true} />


<div class="rp-steps">
<div class="rp-step"><div class="rp-step-num">3</div><div><h4>Manage your zone</h4><p>Under <strong>Settings > Zones</strong>, view every prompt assigned to a zone and switch between <strong>Stack</strong>, <strong>List</strong>, or <strong>Slider</strong> display modes for zones with multiple items.</p></div></div>
</div>


<Image src="https://files.readme.io/dcbb8c2-Screenshot_2024-04-22_175035.png" align="center" width="75%" border={true} />


# Integration

<Tabs>
  <Tab title="Live tool">
    <div class="rp-steps">
    <div class="rp-step"><div class="rp-step-num">1</div><div><h4>Open the Live Tool</h4><p>Select the <strong>Live Tool</strong> button and choose your domain.</p></div></div>
    </div>


    <Image src="https://files.readme.io/7cb2ded-Screenshot_2024-04-22_175333.png" align="center" width="75%" border={true} />



    <Image src="https://files.readme.io/03543e0-Screenshot_2024-04-22_175548.png" align="center" width="75%" border={true} />


    <div class="rp-steps">
    <div class="rp-step"><div class="rp-step-num">2</div><div><h4>Add your zone</h4><p>Expand the panel, switch to the <strong>Add</strong> tab, and choose your zone.</p></div></div>
    </div>


    <Image src="https://files.readme.io/a1fe85f-image.png" align="center" width="75%" border={true} />


    <div class="rp-steps">
    <div class="rp-step"><div class="rp-step-num">3</div><div><h4>Place the zone</h4><p>Hover over the target area until the outline appears, then click to insert the zone.</p></div></div>
    </div>


    <Image src="https://files.readme.io/7878719-image.png" align="center" width="75%" border={true} />

  </Tab>

  <Tab title="Developer guide">
    <div class="rp-steps">
    <div class="rp-step"><div class="rp-step-num">1</div><div><h4>Copy the zone identifier</h4><p>Copy the zone identifier—for example, <code>data-rf-zone="example-tag"</code>.</p></div></div>
    </div>

    <div class="rp-steps">
    <div class="rp-step"><div class="rp-step-num">2</div><div><h4>Insert it into your HTML</h4><p>Add the zone tag to your page markup.</p></div></div>
    </div>

    ```html
    <div data-rf-zone="example-tag"></div>
    ```

    <div class="rp-steps">
    <div class="rp-step"><div class="rp-step-num">3</div><div><h4>Optionally set an explicit height</h4><p>Wrap the zone tag in a container with a set height for absolute positioning.</p></div></div>
    </div>

    ```html
    <div style="height:200px">
      <div data-rf-zone="example-tag"></div>
    </div>
    ```
  </Tab>
</Tabs>

# Tips and tricks

### Absolute positioning—new content

<ol>
<li>Insert the zone tag where needed.</li>
<li>Wrap it in a container with a set height.</li>
<li>Initialize your scroll or animation logic.</li>
</ol>

### Absolute positioning—replacing content

Use the Live Tool sparingly, and make sure your prompt's dimensions match the element it's replacing.

### Content delay solutions

<ul class="rp-list">
<li><strong>Header load lag</strong>: add CSS animations or skeleton loaders.</li>
<li><strong>Above-the-fold delay</strong>: set an explicit height with a brief no-collapse timer.</li>
<li><strong>Slow SDK load</strong>: move the Recurly Engage tag earlier in your tag order.</li>
</ul>

### Responsive resizing

<ul class="rp-list">
<li>Use CSS media queries or <code>transform: scale()</code> for width issues.</li>
<li>Apply <code>background-size: cover</code>, or bake text directly into your background images.</li>
</ul>

***

📋 TODO before publishing:

- [ ] Confirm page title (drafted as "Inline Prompts")
