---
title: Ping
excerpt: >-
  An API for loading user-specific prompts. It describes the request parameters,
  response object, and an example of how to use it to retrieve updated prompts.
api:
  file: custom-rendering-api.yaml
  operationId: ping-api
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
This API should be invoked periodically to load the prompts appropriate for the current user. The response object indicates when (in seconds) the next invocation should take place in order to retrieve updated prompts.