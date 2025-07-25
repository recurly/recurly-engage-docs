---
title: Styling (CSS selectors)
excerpt: >-
  CSS selector reference for customizing the look and feel of Recurly Engage
  prompts.
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
        <p>
          <i className="fa-solid fa-check mr-2" />
          Familiarity with CSS and your site’s stylesheet.
        </p>
        <p>
          <i className="fa-solid fa-exclamation-triangle mr-4" />
          Custom styles are loaded after default Recurly Engage CSS. Please ensure your styles are specific enough to override the default style.
        </p>
      </div>
    </div>
  );
};

<PrerequisitesLimitations header="Prerequisites & limitations" />

# Definition

**Prompt Styling** refers to the customization of prompt elements—layout containers, text areas, buttons, and form controls—via CSS selectors.

# Key benefits

* **Full branding control**: Match prompts to your application’s design system.
* **Responsive tweaks**: Adjust styles for desktop, mobile, and TV viewports.
* **Targeted overrides**: Fine-tune individual prompt types without affecting others.

# Key details

## Quick reference

Use these core selectors to modify the default styling of any Redfast prompt.

| Selector                     | Description                  |
| ---------------------------- | ---------------------------- |
| `.rfmodal-content-wrapper`   | prompt area                  |
| `.rfmodal-inner-wrapper`     | prompt text content area     |
| `.rfmodal-backgroundimage`   | prompt background image      |
| `.rfmodal-header`            | prompt title                 |
| `.rfmodal-header-mobileweb`  | prompt title (mobile)        |
| `.rfmodal-message`           | prompt message body          |
| `.rfmodal-message-mobileweb` | prompt message body (mobile) |
| `.rfmodal-button-yes`        | primary accept button        |
| `.rfmodal-button-no`         | secondary button             |
| `.rfmodal-footer`            | button area                  |
| `.rfmodal-close`             | dismiss button               |
| `.rfmodal-close-icon`        | dismiss button icon          |
| `.rf-radio-group`            | survey form options          |
| `.rf-radio-item`             | survey form line item        |

## Full reference

### Desktop | (Video(web), retention\_modal(web), ios, android\_os, tv\_os, roku\_os)

| Selector                       | Description                             |
| ------------------------------ | --------------------------------------- |
| `.rfmodal-content.outer-modal` | **modal**                               |
| `.rfmodal-backgroundimage`     | **background image or video for modal** |
| `.rfmodal-wrapper.inner-modal` | **layout container**                    |

> [See Desktop Retention Message](#desktop-retention-message)

### Mobile | (Video(web), retention\_modal(web), interstitial(web), ios, android\_os, tv\_os, roku\_os)

| Selector                                              | Description                         |
| ----------------------------------------------------- | ----------------------------------- |
| `.mobileFrameDisplay`                                 | **modal**                           |
| `.mobileFrameInner`                                   | **inner frame**                     |
| [See close button](#close-button)                     | **interstitial only**               |
| `.rfmodal-backgroundimage`                            | **background image for modal**      |
| `.mobileWebModalWrapper`                              | **modal wrapper**                   |
| `.mobilewebModalContentWrapper`                       | **content wrapper**                 |
| [See close button](#close-button)                     | **everything, except interstitial** |
| `.rfmodal-backgroundimage`                            | **background video for modal**      |
| `.videoPosterImgDefault`                              | **video poster**                    |
| [See TOS](#tos)                                       | **terms of service link**           |
| [See Mobile header and body](#mobile-header-and-body) | **header and body containers**      |
| [See Input](#input)                                   | **input fields container**          |
| [See Survey input](#survey-input)                     | **survey options container**        |
| [See Mobile footer](#mobile-footer)                   | **buttons and countdown wrapper**   |

### Mobile | (widget(web), bottom\_banner(web))

| Selector                            | Description                       |
| ----------------------------------- | --------------------------------- |
| `.mweb-widget-container`            | **modal**                         |
| `.mweb-phone-kit-bg`                | **inner frame**                   |
| `.mweb-canvas-bound`                | **inner frame**                   |
| `.mweb-widget-wrapper`              | **layout wrapper**                |
| `.rfmodal-backgroundimage`          | **background image for modal**    |
| `.mobilewebModalContentWrapper`     | **content wrapper**               |
| [See close button](#close-button)   | **close button**                  |
| `.mweb-widget-msg-container`        | **message wrapper**               |
| `.mweb-widget-spacer`               | **message spacer**                |
| `.mweb-widget-content-colm`         | **message content**               |
| `.rfmodal-footer-mobileweb`         | **buttons and countdown wrapper** |
| [See Mobile footer](#mobile-footer) | **buttons and countdown wrapper** |

### Desktop | (widget(web))

| Selector                                                    | Description                    |
| ----------------------------------------------------------- | ------------------------------ |
| `.modal-overlay-style.widget-rf-promo`                      | **modal**                      |
| `.rf-widgetpromo-wrapper`                                   | **inner frame**                |
| `.rfmodal-backgroundimage`                                  | **background image for modal** |
| `.rfmodal-wrapper`                                          | **content wrapper**            |
| [See Desktop Retention Message](#desktop-retention-message) |                                |

### Desktop | (interstitial(web))

| Selector                                                    | Description     |
| ----------------------------------------------------------- | --------------- |
| `.modal-overlay-style.interstitialModal`                    | **modal**       |
| [See close button](#close-button)                           |                 |
| `.rfmodal-content.outer-modal`                              | **outer modal** |
| `.rfmodal-wrapper.inner-modal`                              | **inner modal** |
| [See Desktop Retention Message](#desktop-retention-message) |                 |

### Desktop | (text)

| Selector                          | Description        |
| --------------------------------- | ------------------ |
| `.promo-text-wrapper`             | **prompt text**    |
| [See close button](#close-button) |                    |
| `.promo-text-wrapper-container`   | **text container** |
| `.promo-text-title`               | **text title**     |
| `.promo-text-message`             | **text message**   |

### Mobile | (text)

| Selector                          | Description        |
| --------------------------------- | ------------------ |
| `.promo-text-wrapper-mobile`      | **prompt text**    |
| [See close button](#close-button) |                    |
| `.promo-text-wrapper-container`   | **text container** |
| `.promo-text-title`               | **text title**     |
| `.promo-text-message`             | **text message**   |

### Desktop | (horizontal, tile, vertical)

| Selector                          | Description          |
| --------------------------------- | -------------------- |
| `.promo-tile-wrapper`             | **prompt tile**      |
| [See close button](#close-button) |                      |
| `.promo-tile-backgroundimage`     | **background image** |
| `.promo-tile-wrapper-container`   | **alignment class**  |
| `.tile-header-msg-wrp`            | **message wrapper**  |
| [Promo Content](#promo-content)   |                      |

### Mobile | (horizontal, tile, vertical)

| Selector                        | Description          |
| ------------------------------- | -------------------- |
| `.rtile-mweb-content-wrapper`   | **prompt tile**      |
| `.rtile-mweb-content`           | **content wrapper**  |
| `.rfmodal-backgroundimage`      | **background image** |
| `.rtile-mweb-content-msg`       | **message wrapper**  |
| [Promo Content](#promo-content) |                      |

### Desktop, Mobile | (email)

| Selector                            | Description                 |
| ----------------------------------- | --------------------------- |
| `.pr-email-logo`                    | **Logo**                    |
| `.pr-email-wrapper`                 | **email content wrapper**   |
| `.pr-email-container`               | **email content container** |
| `.pr-email-image`                   | **email image**             |
| `.pr-email-msg`                     | **email message container** |
| `.pr-email-msg-title`               | **email message title**     |
| `.pr-email-msg-body`                | **email message body**      |
| `.pr-email-btn`                     | **email buttons wrapper**   |
| [See Input](#input)                 |                             |
| [See Buttons promo](#buttons-promo) |                             |
| `.pr-email-footer`                  | **email footer (links)**    |

### Desktop | (bottom\_banner)

| Selector                                                    | Description          |
| ----------------------------------------------------------- | -------------------- |
| `.modal-overlay-style.banner-rf-promo`                      | **banner**           |
| `.rfmodal-content.rf-bannerpromo-wrapper`                   | **layout wrapper**   |
| `.rfmodal-backgroundimage`                                  | **background image** |
| `.rfmodal-wrapper`                                          | **content wrapper**  |
| [See Desktop Retention Message](#desktop-retention-message) |                      |

## Basic components

### Buttons

| Selector                              | Description                  |
| ------------------------------------- | ---------------------------- |
| `.rfmodal-button-yes.primary-btn-p`   | **primary confirm button**   |
| `.rfmodal-button-yes.secondary-btn-p` | **secondary confirm button** |
| `.rfmodal-button-no`                  | **no button**                |

### Tile buttons

| Selector                                  | Description               |
| ----------------------------------------- | ------------------------- |
| `.promo-tile-wrapper-btn-accept`          | **primary tile button**   |
| `.promo-tile-wrapper-btn-accept.btn-ac-2` | **secondary tile button** |
| `.promo-tile-wrapper-btn-no`              | **no button**             |

### Survey input

| Selector                              | Description                    |
| ------------------------------------- | ------------------------------ |
| `.survey-wrapper(.center-align-mode)` | **survey wrapper** (alignment) |
| `.survey-wrapper(.right-align-mode)`  | **survey wrapper** (alignment) |
| `.rf-radio-group`                     | **radio buttons wrapper**      |
| `.rf-radio-item`                      | **radio item wrapper**         |

### Input

| Selector                    | Description         |
| --------------------------- | ------------------- |
| `.rfmodal-input-wrapper`    | **input container** |
| `.rfmodal-input-label`      | **label for input** |
| `.rfmodal-input-inputfield` | **input field**     |

### Close button

| Selector              | Description            |
| --------------------- | ---------------------- |
| `.rfmodal-close`      | **modal close button** |
| `#rfmodal-close-icon` | **modal close icon**   |

### TOS

| Selector             | Description |
| -------------------- | ----------- |
| `.modal-privacy-tos` | **TOS**     |

### Mobile header and body

| Selector                     | Description        |
| ---------------------------- | ------------------ |
| `.rfmodal-header-mobileweb`  | **content header** |
| `.rfmodal-body-mobileweb`    | **content body**   |
| `.rfmodal-message-mobileweb` | **content**        |

### Mobile footer

| Selector                    | Description                       |
| --------------------------- | --------------------------------- |
| `.rfmodal-footer-mobileweb` | **buttons and countdown wrapper** |
| `.rfmodal-countdown`        | **countdown label**               |

### Desktop retention message

| Selector                                   | Description                          |
| ------------------------------------------ | ------------------------------------ |
| [See close button](#close-button)          |                                      |
| `.video-volume-control`                    | **volume button (video only)**       |
| `.rfmodal-inner-wrapper`                   | **content container**                |
| `.rfmodal-content-wrapper(.b-left-align)`  | **alignment class (left)**           |
| `.rfmodal-content-wrapper(.b-right-align)` | **alignment class (right)**          |
| `.rfmodal-text-container`                  | **content container**                |
| [See TOS](#tos)                            |                                      |
| `.rfmodal-header`                          | **content header**                   |
| `.rfmodal-body`                            | **content body**                     |
| `.rfmodal-message`                         | **content**                          |
| [See Input](#input)                        |                                      |
| [See Survey input](#survey-input)          |                                      |
| `.rfmodal-footer`                          | **footer container**                 |
| `.rf-button-wrapper`                       | **buttons and countdown wrapper**    |
| `.rf-buttons-inner`                        | **button wrapper**                   |
| `.rfmodal-countdown`                       | **countdown label (desktop/mobile)** |

### Prompt content

| Selector                            | Description         |
| ----------------------------------- | ------------------- |
| `.promo-tile-wrapper-header`        | **message header**  |
| `.promo-tile-wrapper-body`          | **message body**    |
| `.promo-tile-wrapper-footer`        | **message footer**  |
| `.promo-tile-wrapper-btn`           | **buttons wrapper** |
| [See Input](#input)                 |                     |
| [See Buttons promo](#buttons-promo) |                     |

## Fine tuning

While Redfast works out of the box, your customer experience can be further improved. See the [Fine Tuning](#) guide for advanced positioning and performance optimizations.

## Tools and resources

Recurly Engage provides:

1. Live Tool and Live Preview for style testing.
2. Custom CSS overrides and HTML enhancements.
3. Direct support from the Recurly technical team.