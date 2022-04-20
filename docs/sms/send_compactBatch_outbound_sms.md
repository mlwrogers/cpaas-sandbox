---
layout: default
title: Send Batch SMS, compact
parent: SMS
parent: How-to's and Examples
grand_parent: SMS
---

# Send a batch of SMS using a template (_compact_ method)

Here is a complete example of an API request you can make straight from your bash/terminal to send a batch of SMS to multiple destinations using a single message template.
Note: In addition to adding your own real destination numbers, you will need to replace _<yourSubAccountId>_ and _<yourApiToken>_ with the correct values from your 8x8 Connect account.
You may also wish to modify the _"source"_ value to use your own SID (Sender ID), which can be a real virtual number or your own custom name as used in our example.

Not sure where to find those values?  Check out the ['basics'](https://mlwrogers.github.io/cpaas-wiki/docs/basics) section.

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
