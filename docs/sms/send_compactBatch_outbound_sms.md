---
layout: default
title: Send compactBatch SMS
parent: SMS
nav_order: 3
---

# Send a batch of SMS using a template (_compact_)

The JSON body used to send a batch of SMS to multiple destinations using a single template.

```js
{
  "clientBatchId": "campaignReach001",
  "destinations": [
    "+441234567899",
    "+449876543211"
  ],
  "template": {
    "source": "8x8Dev",
    "text": "Hello to everyone in the room!",
  },
  "includeMessagesInResponse": true
}
```
