---
title: Sequence Diagram
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
The following diagram illustrates how you would fetch data from the Ping API to receive eligible prompts and render it onto a screen. Once an eligible prompt is shown to a user additional endpoints should be called to facilitate the user’s interaction. Finally, the Ping API should be called again to refresh the prompts for which a user is eligible.

<Image align="center" src="https://files.readme.io/8559e77-api-sequence.png" />

The following image shows the relevant actions that the user can take once a popup or full screen interstitial is rendered and an impression is fired.

<Image align="center" src="https://files.readme.io/6b58ccf-api-sequence-2.png" />