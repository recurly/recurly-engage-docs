---
title: Interstitial prompts
deprecated: false
hidden: true
metadata:
  description: >
    Information on Recurly Engage's enhanced SDK. It details the new granular
    button controls for interstitial prompts on HTML devices, Roku, and Apple
    TV, which allow for customized button layouts and positioning.
  robots: index
---
# Definition

Recurly Engage's enhanced SDK now provides granular button controls for interstitial prompts. This update allows developers to fully customize the appearance and layout of buttons within prompts displayed on HTML devices (including React Native), Roku, and Apple TV.

These enhancements offer precise control over various button attributes, including:

* Button dimensions (width and height)
* Border properties (radius, thickness, and color)
* Font size
* Absolute positioning

# Key benefits

This enhanced functionality provides developers with the flexibility to design highly customized and effective interstitial prompts for a wide range of use cases. The ability to precisely control button layouts, including stacked or inline configurations, is particularly valuable for optimizing user experience and driving specific outcomes.

* **Enhanced Customization**: Create unique button styles that align with your brand's design language.
* **Improved User Experience**: Optimize button placement and layout to improve readability and user interaction.
* **Flexible Design**: Tailor prompts for high-value use cases such as subscriber activation, engagement campaigns, involuntary churn reduction, and special offers.

# Key details

The new granular controls are configured programmatically within the SDK, simplifying the process of creating custom prompts.

1. **Create a new interstitial [prompt](https://docs.recurly.com/recurly-engage/update/docs/prompts#/) :** In **Pulse**, the Recurly Engage management console, navigate to **Prompts > + New Prompt.** Select the **Interstitial** Prompt Type for the Device Type you’re looking to target.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/ef983cda52f1278237e68949b1d3fc6868ae3adf5dc1711a5ab08bb89fc49c25-Interstitial_1.png" />

<br />

2. **Configure your prompt details:** In the details section of the prompt, configure your targeted [Segment](https://docs.recurly.com/recurly-engage/docs/segments#/) , Trigger, Limits and schedule.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/771975700b27e6b44667ce690f4ec31325773b112c3f9166d70fa3a6d0172e57-Interstitial_2.png" />

3. **Edit prompt design:** In the Prompt Details screen, open the Edit prompt design window. Configure your prompt to match the messaging, styles and interactions desired.
4. **Update the user interactions:** Under the User Interaction section, update the buttons to have personalized height, width, font size, border radius, thickness and color, and positioning.

<Image align="center" className="border" border={true} width="80% " src="https://files.readme.io/82205e058c6dc7281a5d9ab6d534119ab7d8d75000ae391d631dc8b68a2a6eff-Interstitial_3.png" />
