---
layout: default
title: Keyword detection
parent: automation
nav_order: 1
---

## Keyword Detection Demo

This will demonstrate how to create a simple workflow that when enabled will trigger each time an inbound message is received by our WhatsApp sandbox and then automatically send a reply back to the sender.
We start by creating and activating the workflow.

We do this using an HTTPs POST request to our CPaaS platform with a simple JSON body.  As soon as the API call is made and the status set to _enabled_, the workflow is active and ready for use.
To try this out, keep scrolling...If you're the developer then the JSON used in the POST request to create the workflow definition would look a bit like this:

```JSON
{
    "subAccountId": "<yourSubAccountId>",
    "trigger": "inbound_chat_apps",
    "status": "enabled",
    "definition":
    {
        "name": "keyword_demo"
        "steps":
        [
            {
                "id": "check_for_keyword",
                "stepType": "Branch",
                "selectNextStep":
                {
                    "send_ok_reply_ca_msg": "{{stringContains(data.payload.body, 'keyword')}}",
                    "send_nok_reply_ca_msg": null
                }
            },
            {
                "id": "send_ok_reply_ca_msg",
                "stepType": "ChatAppsMessage",
                "inputs":
                {
                    "subAccountId": "<yourSubAccountId>",
                    "user":
                    {
                        "msisdn": "{{data.payload.user.msisdn}}"
                    },
                    "type": "text",
                    "content":
                    {
                        "text": "Thanks for trying our Automation API demo, keyword detected!"
                    }
                }
            },
            {
                "id": "send_nok_reply_ca_msg",
                "stepType": "ChatAppsMessage",
                "inputs":
                {
                    "subAccountId": "<yourSubAccountId>",
                    "user":
                    {
                        "msisdn": "{{data.payload.user.msisdn}}"
                    },
                    "type": "text",
                    "content":
                    {
                        "text": "No keyword detected. Thanks for trying our Automation API demo."
                    }
                }
            }
        ]
    }
}
```

#### Try it out yourself!

There are two QR codes below, one of them includes a 5 digit code as part of the pre-filled text.  We are using that code for a simple keyword detection, A different message is sent back based on if the keyword was used in the original message or not.

<p style="text-align: center;">Scan (or click) this QR code to send us a WhatsApp message that <em>includes</em> the keyword and receive an automatic response!</p>
<a href="https://wa.me/message/OFMUAVJ2CDYSP1">
    <img src="./images/OFMUAVJ2CDYSP1.png" alt="qrcode_reply" style="display: block; margin-left: auto; margin-right: auto;">
</a>

<p style="text-align: center;">Scan (or click) this QR code to send us a WhatsApp message with <em>no</em> keyword and receive a different response!</p>
<a href="https://wa.me/message/HK7HY7VU5EPYN1">
    <img src="./images/HK7HY7VU5EPYN1.png" alt="qrcode_no_reply" style="display: block; margin-left: auto; margin-right: auto;">
</a>
