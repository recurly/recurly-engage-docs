---
title: Introduction
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
## SDK vs API based implementation

Device SDKs utilize the same APIs described below, with the following built-in functionality:

* Automatic refreshing of prompts ([Ping API](ping-api))
* Popup rendering and interaction handling ([Impression](impression-api), [Goal](goal-api), [Dismiss](dismiss-api) APIs)
* Functions for retrieving inline prompt assets and attributes
* Functions for reporting Impression, Goal, Dismiss for inline prompts
* Support for utilizing existing media asset deep linking
* Support kicking off InApp Purchase from prompt CTA

An API based implementation allows for greater control over the rendering of Redfast prompts while removing the requirement to add an SDK. Attributes for all supported prompt types (described [here](prompt-attributes)) are configured within the Pulse web console and may be utilized to create a custom experience for users.
