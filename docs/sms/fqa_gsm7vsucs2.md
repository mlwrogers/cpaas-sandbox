---
layout: default
title: Do you support GSM-7 and/or UCS2 encoding?
parent: SMS_FAQ
grand_parent: SMS
---

## Do you support GSM-7 and/or UCS2 encoding?

We support both!

The 8x8 platform will automatically send your SMS messages in the most compact encoding possible.  Typically this is GSM-7.  However, if you include _any_ non GSM-7 characters in your message body, we will automatically fall back to UCS-2 encoding.  UCS-2 encoding will limit message bodies to 70 characters each.

### Sending via API.

If you are using the API to send messages you can also explicitley select which encoding you want to use by configuring the _encoding_ value (included in the example below).

Supported **_encoding_** values are:|AUTO|GSM7|UCS2

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

### Sending via Connect web portal.

If you are using our Connect portal to send messages, the preview window within the _sender_ will automatically tell you which encoding will be used to send the message body you've entered.

### How to check which SMS encoding will be used?

Using Connect is is also a great way to check your message bodies prior to sending via API or SMPP (as well as via COnnect of course) if you're unsure on the characters in your message body.

There are some common _mistakes_ such as using the correct apostrophe which is very subtle but could be costly if not realised.  You can check the [basic character set for GSM-7 here: ](https://en.wikipedia.org/wiki/GSM_03.38#GSM_7-bit_default_alphabet_and_extension_table_of_3GPP_TS_23.038_.2F_GSM_03.38)

**Example of GSM-7 message body**

![Encoding GSM image](https://mlwrogers.github.io/cpaas-wiki/image_assets/connect/encoding_gsm.png)

**Example of UCS2 message body**
![Encoding UCS2 image](https://mlwrogers.github.io/cpaas-wiki/image_assets/connect/encoding_ucs2.png)
