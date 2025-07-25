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
# Overview

### Video

<Embed url="https://www.loom.com/embed/0b567941dcf24629b1c053d4900ff0d3?sid=0d2335cd-d92d-4fcd-8438-3a35c781d0ca" href="https://www.loom.com/embed/0b567941dcf24629b1c053d4900ff0d3?sid=0d2335cd-d92d-4fcd-8438-3a35c781d0ca" typeOfEmbed="iframe" height="480px" width="100%" iframe="true" />

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

Inline prompts occupy predefined [zones](zones) on your site or application. Four styles are supported—horizontal banners, vertical panels, tiles, and text-only bars—each designed to blend with your layout.

# Key benefits

* **Contextual placement**: Deliver messages directly within your page for higher relevance.
* **Versatile formats**: Choose from four inline styles to suit any design.
* **Dynamic sequencing**: Render multiple items per zone in stack, list, or slider modes.

# Key details

These four prompt types occupy defined zones on your site or application alongside your content—hence the name **inline**.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/3306b54-Screenshot_2024-04-18_193019.png" />

Inline prompts live in [zones](zones). Any prompt assigned to a zone appears in that location—for example, a horizontal banner in the **Web Featured** zone.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/e0c5481-Screenshot_2024-04-18_191758.png" />

A single zone can render multiple items of the same type in one of three modes:

* **Stack**: items overlap; each new item appears after the prior one is dismissed.
* **List**: items display side by side, ideal for showing a row of personalized recommendations.
* **Slider**: a carousel showing one item at a time, with optional bullet indicators or auto-rotation.

### Horizontal

A wide banner with a landscape orientation that spans the width of your content area or screen edge-to-edge. Commonly placed at the top or bottom of pages, it can include a call-to-action button and hide itself on click or remain visible.

* **Recommended ratios**: 2×1, 4×1, **6×1**, 8×1, 10×1.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/994d3cd-image.png" />

### Vertical

A tall panel with a portrait orientation, typically along the left or right edge of your layout. Like horizontals, it may include buttons and can be timed or click-to-dismiss.

* **Recommended ratios**: 1×2, **1×3**, 1×4.

<Image align="center" className="border" border={true} src="https://files.readme.io/a1fb469-image.png" />

### Tile

A square or rectangle zone—perfect for grid layouts. Tiles display media and text, and can be closed or persist after interaction.

* **Recommended ratios**: 1×1, 4×3, 16×9.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/5729a7f-image.png" />

### Text-only

A clickable text bar without images, useful for simple announcements or links. It can be configured to hide on click or remain in view.

* **Recommended ratios**: 6×1, 8×1, 10×1.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/392d0bc-image.png" />

***

## Step-by-step guide

1. **Create a zone**

   * Navigate to **Settings > Zones > New Zone**.
   * Name the zone (no spaces) and select its placement (e.g., “Home Page Top Banner”).

   <br />

   <Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/0e07cb5-image.png" />

   <Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/60a9382-inline2.png" />

2. **Build an inline prompt**

   * Go to **Prompts > New Prompt**.
   * Choose **Desktop and Mobile**, then select **Horizontal** (or your desired inline type).

   <br />

   <Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/564d84a-image.png" />

   <Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/664a781-image.png" />

   * Enter a **Name**, **Description**, and assign it to your new zone, then click **Submit**.

   <br />

   <Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/c8c3561-image.png" />

   * Configure **Segments**, **Limits** (optional), **Schedule** (optional), and **Actions**.

   * Click **Edit prompt design** to customize visuals and copy.

   <br />

   <Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/6a6227a-Screenshot_2024-04-22_173653.png" />

   * Tweak settings in the designer and preview live changes. Download sample backgrounds [here](/images/samples.zip).

   <br />

   <Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/0d80810-Screenshot_2024-04-22_174308.png" />

   * Click **Publish** to make the prompt live.

   <br />

   <Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/a55eac9-Screenshot_2024-04-22_174752.png" />

3. **Manage your zone**

   * Under **Settings > Zones**, view all prompts assigned to a zone.
   * Switch between **Stack**, **List**, or **Slider** display modes for multiple items.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/dcbb8c2-Screenshot_2024-04-22_175035.png" />

***

## Integration

### Live tool

1. **Click** the **Live Tool** button and **select** your domain.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/7cb2ded-Screenshot_2024-04-22_175333.png" />

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/03543e0-Screenshot_2024-04-22_175548.png" />

2. **Expand** the panel, switch to the **Add** tab, and choose your zone.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/a1fe85f-image.png" />

3. **Hover** over the target area until the outline appears, then click to insert the zone.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/7878719-image.png" />

### Developer guide

1. **Copy** the zone identifier (e.g., `data-rf-zone="example-tag"`).
2. **Insert** into your HTML:

```html
<div data-rf-zone="example-tag"></div>
```

3. **Optionally** **wrap in** a container with explicit height for absolute positioning:

```html
<div style="height:200px">
  <div data-rf-zone="example-tag"></div>
</div>
```

***

## Tips and tricks

### Absolute positioning - new content

1. Insert the zone tag where needed.
2. Wrap in a container with a set height.
3. Initialize your scroll or animation logic.

### Absolute positioning—replacing content

Use the Live Tool sparingly—ensure your prompt dimensions match the existing element.

### Content delay solutions

* **Header load lag**: add CSS animations or skeleton loaders.
* **Above-the-fold delay**: set explicit height with a brief no-collapse timer.
* **Slow SDK load**: move the Recurly Engage tag earlier in your tag order.

### Responsive resizing

* Use CSS media queries or `transform: scale()` for width issues.
* Apply `background-size: cover` or bake text into images for backgrounds.