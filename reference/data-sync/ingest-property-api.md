---
title: Ingest Property
excerpt: >-
  This API allows syncing of specific properties (also referred to as Traits)
  for a specific userId and/or anonymousUserId.
api:
  file: data-sync.json
  operationId: get_new-endpoint
hidden: true
---
Multiple properties may be specified in one API call. For example, the query string `properties[key1]=val1&properties[key2]=val2&userId=testUser123` results in the following properties associated with userId `testUser123`:

* key1=val1
* key2=val2