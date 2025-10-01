---
title: Recommended prompt sizes
excerpt: >-
  Creative asset specifications for platform prompts. Includes recommended image
  sizes, aspect ratios, and supported file types for Inline and Overlay prompt
  styles across web, mobile, and TV SDKs.
deprecated: false
hidden: false
metadata:
  robots: index
---
# Definition

Recommended prompt sizes is a technical specification guide that outlines the supported parameters for creative assets. It details which prompt styles (e.g., Horizontal, Tile, Popup) and prompt types (Inline, Overlay) are available on specific platforms (Web, native iOS, Android TV, ROKU, etc.), and provides the recommended width and height (in pixels) and supported image file types (png, jpg, gif) required for production.

# Key benefits

This guide is essential for creative and design departments to ensure technical compliance and efficiency when creating assets:

* **Accuracy in Production:** Provides the exact pixel dimensions for every supported prompt, eliminating guesswork and preventing the creation of assets that are improperly sized or scaled.
* **Streamlined Creative Workflow:** Confirms the required aspect ratios and accepted file formats (png, jpg, gif) upfront, allowing teams to set up design templates correctly from the start.

# Key details

## Supported prompt styles

The following tables show which prompt styles are supported across various platforms for Inline, Overlay, and other prompt types.

### Inline prompt styles

<br />

| Platform                                                                                 | Horizontal | Vertical | Tile | Text Only | Slider |
| ---------------------------------------------------------------------------------------- | ---------- | -------- | ---- | --------- | ------ |
| Web (desktop browser)                                                                    | TRUE       | TRUE     | TRUE | TRUE      | TRUE   |
| Web (mobile browser)                                                                     | TRUE       | TRUE     | TRUE | TRUE      | TRUE   |
| HTML5 TV devices (Comcast, Cox, Vizio, Vidaa, Xbox, PS4, PS5, Xbox, Samsung, LG devices) | TRUE       | TRUE     | TRUE | TRUE      |        |
| native iOS (iPhone)                                                                      | TRUE       | TRUE     | TRUE |           |        |
| native iOS (iPad)                                                                        | TRUE       | TRUE     | TRUE |           |        |
| native Apple TV                                                                          | TRUE       | TRUE     | TRUE |           |        |
| native Android (phone)                                                                   | TRUE       | TRUE     | TRUE |           |        |
| native Android (tablet)                                                                  | TRUE       | TRUE     | TRUE |           |        |
| native Android TV                                                                        | TRUE       | TRUE     | TRUE |           |        |
| native Amazon Fire TV                                                                    | TRUE       | TRUE     | TRUE |           |        |
| ROKU                                                                                     | TRUE       | TRUE     | TRUE |           |        |
| hybrid iOS (iPhone)                                                                      | TRUE       | TRUE     | TRUE |           |        |
| hybrid iOS (iPad)                                                                        | TRUE       | TRUE     | TRUE |           |        |
| hybrid Apple TV                                                                          | TRUE       | TRUE     | TRUE |           |        |
| hybrid Android (phone)                                                                   | TRUE       | TRUE     | TRUE |           |        |
| hybrid Android (tablet)                                                                  | TRUE       | TRUE     | TRUE |           |        |
| hybrid Android TV                                                                        | TRUE       | TRUE     | TRUE |           |        |

<br />

### Overlay prompt sizes

| Platform                                                                                 | Interstitial | Popup | Video | Bottom banner | Notification |
| ---------------------------------------------------------------------------------------- | ------------ | ----- | ----- | ------------- | ------------ |
| Web (desktop browser)                                                                    | TRUE         | TRUE  | TRUE  | TRUE          | TRUE         |
| Web (mobile browser)                                                                     | TRUE         | TRUE  | TRUE  | TRUE          | TRUE         |
| HTML5 TV devices (Comcast, Cox, Vizio, Vidaa, Xbox, PS4, PS5, Xbox, Samsung, LG devices) |              | TRUE  |       | TRUE          |              |
| native iOS (iPhone)                                                                      | TRUE         | TRUE  | TRUE  | TRUE          | TRUE         |
| native iOS (iPad)                                                                        |              | TRUE  | TRUE  | TRUE          | TRUE         |
| native Apple TV                                                                          | TRUE         | TRUE  | TRUE  | TRUE          | TRUE         |
| native Android (phone)                                                                   | TRUE         | TRUE  | TRUE  | TRUE          | TRUE         |
| native Android (tablet)                                                                  |              | TRUE  | TRUE  | TRUE          | TRUE         |
| native Android TV                                                                        | TRUE         | TRUE  | TRUE  | TRUE          | TRUE         |
| native Amazon Fire TV                                                                    | TRUE         | TRUE  | TRUE  | TRUE          | TRUE         |
| ROKU                                                                                     | TRUE         | TRUE  | TRUE  | TRUE          |              |
| hybrid iOS (iPhone)                                                                      | TRUE         | TRUE  | TRUE  | TRUE          |              |
| hybrid iOS (iPad)                                                                        |              | TRUE  | TRUE  | TRUE          |              |
| hybrid Apple TV                                                                          | TRUE         | TRUE  | TRUE  | TRUE          |              |
| hybrid Android (phone)                                                                   | TRUE         | TRUE  | TRUE  | TRUE          |              |
| hybrid Android (tablet)                                                                  |              | TRUE  | TRUE  | TRUE          |              |
| hybrid Android TV                                                                        | TRUE         | TRUE  | TRUE  | TRUE          |              |

<br />

### Other prompt types

| Platform                                                                                 | Invisible | Email |
| ---------------------------------------------------------------------------------------- | --------- | ----- |
| Web (desktop browser)                                                                    | TRUE      | TRUE  |
| Web (mobile browser)                                                                     | TRUE      | TRUE  |
| HTML5 TV devices (Comcast, Cox, Vizio, Vidaa, Xbox, PS4, PS5, Xbox, Samsung, LG devices) |           |       |
| native iOS (iPhone)                                                                      |           |       |
| native iOS (iPad)                                                                        |           |       |
| native Apple TV                                                                          |           |       |
| native Android (phone)                                                                   |           |       |
| native Android (tablet)                                                                  |           |       |
| native Android TV                                                                        |           |       |
| native Amazon Fire TV                                                                    |           |       |
| ROKU                                                                                     |           |       |
| hybrid iOS (iPhone)                                                                      |           |       |
| hybrid iOS (iPad)                                                                        |           |       |
| hybrid Apple TV                                                                          |           |       |
| hybrid Android (phone)                                                                   |           |       |
| hybrid Android (tablet)                                                                  |           |       |
| hybrid Android TV                                                                        |           |       |

<br />

## Recommended prompt sizes

The following tables show the recommended prompt sizes for all of the available Recurly Engage SDKs.

| SDK                  | Prompt Type | Prompt Style  | Supported Aspect Ratios  | Recommended Width × Height                 | Supported Image Types |
| -------------------- | ----------- | ------------- | ------------------------ | ------------------------------------------ | --------------------- |
| Web (desktop)        | Inline      | Horizontal    | 2:1, 4:1, 6:1, 8x1, 10x1 | 960 x 300 px                               | png, jpg, gif         |
| Web (desktop)        | Inline      | Vertical      | 1:2, 1:3, 1:4            | 250 x 500 px                               | png, jpg, gif         |
| Web (desktop)        | Inline      | Tile          | 1:1, 1:2                 | 250 x 500 px                               | png, jpg, gif         |
| Web (desktop)        | Inline      | Text Only     | 6:1, 8:1, 10:1           | 100% x auto                                | png, jpg, gif         |
| Web (desktop)        | Overlay     | Interstitial  |                          | 1200 x 800 px                              | png, jpg, gif         |
| Web (desktop)        | Overlay     | Popup         |                          | 1200 x 800 px, 960 x 640 px, 750 x 500 px  | png, jpg, gif         |
| Web (desktop)        | Overlay     | Video         |                          | 1200 x 619 px ; 960 x 619 px, 750 x 619 px | png, jpg, gif         |
| Web (desktop)        | Overlay     | Bottom banner |                          | 1000 x 100 px                              | png, jpg, gif         |
| Web (desktop)        | Overlay     | Notification  |                          | 450 x 180 px                               | png, jpg, gif         |
| Web (mobile browser) | Inline      | Horizontal    | 2:1, 4:1, 6:1, 8x1, 10x1 | 300 x 200 px                               | png, jpg, gif         |
| Web (mobile browser) | Inline      | Vertical      | 1:2, 1:3, 1:4            | 200 x 300 px                               | png, jpg, gif         |
| Web (mobile browser) | Inline      | Tile          | 1:1, 1:2                 | 375 x 205 px                               | png, jpg, gif         |
| Web (mobile browser) | Inline      | Text Only     | 6:1, 8:1, 10:1           | 100% x auto                                | png, jpg, gif         |
| Web (mobile browser) | Overlay     | Interstitial  |                          | 337.5 x 479.5 px                           | png, jpg, gif         |
| Web (mobile browser) | Overlay     | Popup         |                          | 500 x 800                                  | png, jpg, gif         |
| Web (mobile browser) | Overlay     | Video         |                          | 337.5 x 470.13 px                          | png, jpg, gif         |
| Web (mobile browser) | Overlay     | Bottom banner |                          | 100% x 120 px                              | png, jpg, gif         |
| Web (mobile browser) | Overlay     | Notification  |                          | 100% x 120 px                              | png, jpg, gif         |
| HTML5 TV devices     | Inline      | Horizontal    | 2:1, 4:1, 6:1, 8x1, 10x1 | 960 x 300 px                               | png, jpg, gif         |
| HTML5 TV devices     | Inline      | Vertical      | 1:2, 1:3, 1:4            | 250 x 500 px                               | png, jpg, gif         |
| HTML5 TV devices     | Inline      | Tile          | 1:1, 1:2                 | 250 x 500 px                               | png, jpg, gif         |
| HTML5 TV devices     | Inline      | Text Only     | 6:1, 8:1, 10:1           | 100% x auto                                | png, jpg, gif         |
| HTML5 TV devices     | Overlay     | Popup         |                          | 1200 x 800 px, 960 x 640 px, 750 x 500 px  | png, jpg, gif         |
| HTML5 TV devices     | Overlay     | Bottom banner |                          | 1000 x 100 px                              | png, jpg, gif         |
| iOS (iPhone)         | Inline      | Horizontal    | 2:1, 4:1, 6:1, 8x1, 10x1 | 1000x200px                                 | png, jpg              |
| iOS (iPhone)         | Inline      | Vertical      | 1:2, 1:3, 1:4            | 300x1400px                                 | png, jpg              |
| iOS (iPhone)         | Inline      | Tile          | 1:1, 1:2                 | 320x180px                                  | png, jpg              |
| iOS (iPhone)         | Inline      | Text Only     | 6:1, 8:1, 10:1           | 1000x200px                                 | png, jpg              |
| iOS (iPhone)         | Overlay     | Interstitial  |                          | 1200 x 2400 px                             | png, jpg              |
| iOS (iPhone)         | Overlay     | Bottom banner |                          | 900x200px                                  | png, jpg              |
| iOS (iPad)           | Inline      | Horizontal    | 2:1, 4:1, 6:1, 8x1, 10x1 | 1500x300px                                 | png, jpg              |
| iOS (iPad)           | Inline      | Vertical      | 1:2, 1:3, 1:4            | 300x1500px                                 | png, jpg              |
| iOS (iPad)           | Inline      | Tile          | 1:1, 1:2                 | 360x200px                                  | png, jpg              |
| iOS (iPad)           | Inline      | Text Only     | 6:1, 8:1, 10:1           | 1400x200px                                 | png, jpg              |
| iOS (iPad)           | Overlay     | Popup         |                          | 1024 x 1024 px                             | png, jpg              |
| iOS (iPad)           | Overlay     | Bottom banner |                          | 1300x300px                                 | png, jpg              |
| Apple TV             | Inline      | Horizontal    | 2:1, 4:1, 6:1, 8x1, 10x1 | 1400x200px                                 | png, jpg              |
| Apple TV             | Inline      | Vertical      | 1:2, 1:3, 1:4            | 300x1000px                                 | png, jpg              |
| Apple TV             | Inline      | Tile          | 1:1, 1:2                 | 320x180px                                  | png, jpg              |
| Apple TV             | Inline      | Text Only     | 6:1, 8:1, 10:1           | 1720x150px                                 | png, jpg              |
| Apple TV             | Overlay     | Popup         |                          | 1600x1200 px                               | png, jpg              |
| Apple TV             | Overlay     | Interstitial  |                          | 1920x1080 or 3840x2160 px                  | png, jpg              |
| Apple TV             | Overlay     | Bottom banner |                          | 1200x200px                                 | png, jpg              |
| Android (phone)      | Inline      | Horizontal    | 2:1, 4:1, 6:1, 8x1, 10x1 | 1000x200px                                 | png, jpg              |
| Android (phone)      | Inline      | Vertical      | 1:2, 1:3, 1:4            | 300x1400px                                 | png, jpg              |
| Android (phone)      | Inline      | Tile          | 1:1, 1:2                 | 320x180px                                  | png, jpg              |
| Android (phone)      | Inline      | Text Only     | 6:1, 8:1, 10:1           | 1000x200px                                 | png, jpg              |
| Android (phone)      | Overlay     | Interstitial  |                          | 1200 x 2400 px                             | png, jpg              |
| Android (phone)      | Overlay     | Bottom banner |                          | 900x200px                                  | png, jpg              |
| Android (tablet)     | Inline      | Horizontal    | 2:1, 4:1, 6:1, 8x1, 10x1 | 1500x300px                                 | png, jpg              |
| Android (tablet)     | Inline      | Vertical      | 1:2, 1:3, 1:4            | 300x1500px                                 | png, jpg              |
| Android (tablet)     | Inline      | Tile          | 1:1, 1:2                 | 360x200px                                  | png, jpg              |
| Android (tablet)     | Inline      | Text Only     | 6:1, 8:1, 10:1           | 1400x200px                                 | png, jpg              |
| Android (tablet)     | Overlay     | Popup         |                          | 1024 x 1024 px                             | png, jpg              |
| Android (tablet)     | Overlay     | Bottom banner |                          | 1300x300px                                 | png, jpg              |
| Android TV           | Inline      | Horizontal    | 2:1, 4:1, 6:1, 8x1, 10x1 | 1400x200px                                 | png, jpg              |
| Android TV           | Inline      | Vertical      | 1:2, 1:3, 1:4            | 300x1000px                                 | png, jpg              |
| Android TV           | Inline      | Tile          | 1:1, 1:2                 | 320x180px                                  | png, jpg              |
| Android TV           | Inline      | Text Only     | 6:1, 8:1, 10:1           | 1720x150px                                 | png, jpg              |
| Android TV           | Overlay     | Popup         |                          | 1600x1200 px                               | png, jpg              |
| AndroidTV            | Overlay     | Interstitial  |                          | 1920x1080 or 3840x2160 px                  | png, jpg              |
| Android TV           | Overlay     | Bottom banner |                          | 1200x200px                                 | png, jpg              |
| ROKU                 | Inline      | Horizontal    | 2:1, 4:1, 6:1, 8x1, 10x1 | 1400x200px                                 | png, jpg              |
| ROKU                 | Inline      | Vertical      | 1:2, 1:3, 1:4            | 300x1000px                                 | png, jpg              |
| ROKU                 | Inline      | Tile          | 1:1, 1:2                 | 320x180px                                  | png, jpg              |
| ROKU                 | Inline      | Text Only     | 6:1, 8:1, 10:1           | 1720x150px                                 | png, jpg              |
| ROKU                 | Overlay     | Interstitial  |                          | 1920x1080 or 3840x2160 px                  | png, jpg              |
| ROKU                 | Overlay     | Popup         |                          | 1400 x 790 px or 1920x1080 px              | png, jpg              |
| ROKU                 | Overlay     | Bottom banner |                          | 1200x200px                                 | png, jpg              |

<br />

<br />

<br />
