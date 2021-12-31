---
layout: default
title: Send batch SMS
parent: SMS
nav_order: 2
---

The JSON body used to send a batch of SMS to multiple destinations, each with its own message.

```js
{
     "messages": [
          {
               "encoding": "AUTO",
               "destination": "+441234567899",
               "text": "An SMS message for Alice",
               "clientMessageId": "1001"
          },
          {
               "encoding": "AUTO",
               "destination": "+449876543211",
               "text": "An SMS message for Bob",
               "clientMessageId": "1002"
          }
     ],
     "template": {
          "encoding": "AUTO",
          "source": "<your_source_SID>",
          "text": "Message to the world"
     },
     "clientBatchId": "smsApiDemo",
     "includeMessagesInResponse": false
}
```
