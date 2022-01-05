---
layout: default
title: Send Batch SMS, compact
parent: SMS
nav_order: 3
---

# Send a batch of SMS using a template (_compact_ method)

Here is a complete example of a cURL request to send a batch of SMS to multiple destinations using a single message template.
Note: In addition to adding your own real destination numbers, you will need to replace _<yourSubAccountId>_ and _<yourApiToken>_ with the correct values from your 8x8 Connect account.

```json
curl --location --request POST 'https://sms.8x8.com/api/v1/subaccounts/<yourSubAccountId>/messages/batch' \
--header 'Authorization: Bearer <yourApiKey>' \
--header 'Content-Type: application/json' \
--data-raw '{
  "clientBatchId": "campaign001",
  "destinations": [
    "+441234567899",
    "+449876543211"
  ],
  "template": {
    "source": "8x8Dev",
    "text": "Hello to everyone in the room!",
  },
  "includeMessagesInResponse": true
}'

```
