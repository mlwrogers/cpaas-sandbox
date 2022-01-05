---
layout: default
title: Send Batch SMS, compact
parent: SMS
nav_order: 3
---

# Send a batch of SMS using a template (_compact_ method)

Here is a complete example of a cURL request to send a batch of SMS to multiple destinations using a single message template.
Note: In addition to adding your own real destination numbers, you will need to replace _<yourSubAccountId>_ and _<yourApiToken>_ with the correct values from your 8x8 Connect account.

```js

curl --location --request POST 'https://sms.8x8.com/api/v1/subaccounts/<yourSubAccountId>/messages/batch' \
--header 'Authorization: Bearer <yourApiKey>' \
--header 'Content-Type: application/json' \
--data-raw '{
     "messages": [
          {
               "encoding": "AUTO",
               "destination": "+441234567899",
               "text": "An SMS message just for Alice",
               "clientMessageId": "1001"
          },
          {
               "encoding": "AUTO",
               "destination": "+449876543211",
               "text": "An SMS message just for Bob",
               "clientMessageId": "1002"
          }
     ],
     "template": {
          "encoding": "AUTO",
          "source": "8x8 Dev",
          "text": "Message to the world"
     },
     "clientBatchId": "smsApiDemo",
     "includeMessagesInResponse": false
}'

```
