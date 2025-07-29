---
title: Reset API
excerpt: ''
api:
  file: custom-rendering-api.json
  operationId: reset-api
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
To be used only for testing & development - This API may be invoked to reset the state of all prompts targeted to the user. Prompts that were no longer returned due to a previous interaction will now reset and be returned on the next Ping.

```json
{
  "success": true,
  "configs": { "ping_frequency": 10 }
}
```
