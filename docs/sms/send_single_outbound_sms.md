---
layout: default
title: Send single SMS
parent: How-to's and Examples
grand_parent: SMS
---

# Send a single SMS

Here is a quick example of how to send to a single SMS straight from your bash/terminal using cURL.

Note: In addition to adding your own real destination number, you will need to replace _<yourSubAccountId>_ and _<yourApiToken>_ with the correct values from your 8x8 Connect account.
You may also wish to modify the _"source"_ value to use your own SID (Sender ID), which can be a real virtual number or your own alpha numeric name as used in our example.

Not sure where to find your subAccountId and/or your API token? Then Check out the ['basics'](docs/basics/basics.md) section.

```json
curl --request POST 'https://sms.8x8.com/api/v1/subaccounts/<yourSubAccountId>/messages' \
--header 'Authorization: Bearer <yourApiToken>' \
--header 'Content-Type: application/json' \
--data-raw '{
    "clientMessageId": "123xyz",
    "source": "8x8Dev",
    "destination": "+441234567899",
    "text": "Show us the value in APIs",
    "encoding": "AUTO"
}'

```
