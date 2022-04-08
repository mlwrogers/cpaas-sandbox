---
layout: default
title: Keyword detection, WhatsApp
parent: Automation
---

# Keyword Detection Demo

This will demonstrate how to create a simple workflow that when enabled will trigger each time an inbound message is received by our WhatsApp sandbox and then automatically send a reply back to the sender.
We start by creating and activating the workflow.

We do this using an HTTPs POST request to our CPaaS platform with a simple JSON body.  As soon as the API call is made and the status set to _enabled_, the workflow is active and ready for use.
To quickly try this out with our working example, keep scrolling...If you're the developer then you can also take a look at the example POST request to create this workflow definition.

HTTP POST request to: `https://automation.8x8.com/api/v1/accounts/<yourSubAccountId>/definition`
```json
// JSON body

{
    "subAccountId": "<yourSubAccountId",
    "trigger": "inbound_chat_apps",
    "status": "enabled",
    "definition":
    {
        "name": "keyword_example",
        "steps":
        [
            {
                "id": "check_for_keyword",
                "stepType": "Branch",
                "selectNextStep":
                {
                    "send_ok_reply_ca_msg": "{{stringContains(data.payload.content.text, '<yourKeyword>')}}",
                }
            },
            {
                "id": "send_ok_reply_ca_msg",
                "stepType": "ChatAppsMessage",
                "inputs":
                {
                    "subAccountId": "<yourSubAccountId",
                    "user":
                    {
                        "msisdn": "{{data.payload.user.msisdn}}"
                    },
                    "type": "text",
                    "content":
                    {
                        "text": "Thank you for trying out our Automation API demo, you sent the correct keyword!"
                    }
                }
            }
        ]
    }
}
```

## Try it out yourself!

There are two QR codes below, one of them includes a 5 digit code as part of the pre-filled text.  We are using that code for a simple keyword detection.  For this demonstration we are using a random set of characters as the keyword, if the keyword is detected in the incoming message then an automatic reply is sent.  If no keyword is detected, no reply is sent.

Scan (or click) this QR code to send us a WhatsApp message that _includes_ a specific keyword and receive an automatic response!

[![QR_with_keyword](/cpaas-wiki/image_assets/OFMUAVJ2CDYSP1_with_keyword.png)](https://wa.me/message/OFMUAVJ2CDYSP1)

Scan (or click) this QR code to send us a WhatsApp message with _no_ keyword, you will _not_ receive an automatic response!

[![QR_without_keyword](/cpaas-wiki/image_assets/HK7HY7VU5EPYN1_without_keyword.png)](https://wa.me/message/HK7HY7VU5EPYN1)
