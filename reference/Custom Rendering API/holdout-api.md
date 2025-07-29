---
title: Holdout API
excerpt: ''
api:
  file: custom-rendering-api.json
  operationId: holdout-api
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
In the case an experiment is running with a Holdout/Control group, the Path object will be returned with an attribute indicating whether the user is part of the holdout group.

```json
{
  "paths": [
    {
      "name": "Test prompt",
      ...
      "holdout": true,
      ...
    }
  ]
}
```

If "holdout": true, the prompt should not be rendered, but rather the Holdout API should be invoked at the time the prompt would normally be triggered. Once the Holdout API has been invoked, subsequent Ping responses will no longer include this particular Path object.
