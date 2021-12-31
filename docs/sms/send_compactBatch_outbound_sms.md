---
layout: default
title: Send compactBatch SMS
parent: SMS
nav_order: 3
---

The JSON body used to send a batch of SMS to multiple destinations using a single template.

```js
{
  "clientBatchId": "campaignReach001",
  "destinations": [
    "+447764836779",
    "+447585350561"
  ],
  "template": {
    "source": "8x8Dev",
    "text": "Hello to everyone in the room!",
  },
  "includeMessagesInResponse": true
}
```
