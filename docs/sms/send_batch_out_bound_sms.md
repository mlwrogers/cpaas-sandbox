---
layout: default
title: Send batch SMS
parent: SMS
parent: How-to's and Examples
grand_parent: SMS
---

# Send a batch of SMS with different content

Here is a complete example of a cURL request to send a batch of SMS to multiple destinations each with it's own message.

Note: In addition to adding your own real destination number, you will need to replace _<yourSubAccountId>_ and _<yourApiToken>_ with the correct values from your 8x8 Connect account.
You may also wish to modify the _"source"_ value to use your own SID (Sender ID), which can be a real virtual number or your own custom name as used in our example.

Not sure where to find those values?  Check out the ['basics'](https://mlwrogers.github.io/cpaas-wiki/docs/basics/) section.

```json
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
          "source": "<your_source_SID>",
          "text": "Message to the world"
     },
     "clientBatchId": "smsApiDemo",
     "includeMessagesInResponse": false
}'

```
