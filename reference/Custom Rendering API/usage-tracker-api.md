---
title: Usage Tracker API
excerpt: >-
  An API for logging custom usage events. It details how to use the Ping API to
  track specific user actions, such as a completed purchase, registration, or
  content consumption.
api:
  file: custom-rendering-api.yaml
  operationId: usage-tracker-api
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
This API should be invoked when a specified usage/event tracker condition has been met. Examples of this would be a user completing a purchase, completing registration or consuming some content. This API reuses the Ping API with some specific URL param attributes.