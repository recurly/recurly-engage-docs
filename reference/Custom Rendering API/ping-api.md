---
title: Ping
excerpt: The ping call is the starting point to interacting with the Redfast backend
api:
  file: custom-rendering-api.json
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