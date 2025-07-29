---
title: Dismiss API
excerpt: ''
api:
  file: custom-rendering-api.json
  operationId: dismiss-api
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
This API should be invoked when the prompt is dismissed, declined or times out. Definitions for each are as follows:

* Dismiss: User decides to remove the prompt from view (presses the X close icon). The dismissed prompt is subject to be shown to the user again per Redfast configuration.
* Decline: User decides to decline the prompt from view (i.e. presses the button with the Cancel Button Text). The declined prompt will no longer be returned in the Ping API unless otherwise configured.
* Timeout: The specified prompt timeout period has expired and the prompt is automatically removed from view. The timed out prompt is subject to be shown again per Redfast configuration.
