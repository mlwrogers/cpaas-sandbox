---
layout: default
title: Auto reply, WhatsAPp
parent: Automation
---

# A simple Auto-Reply Demo for WhatsApp

This will demonstrate how to create a very simple workflow that sends an auto-reply whenever an inbound WhatsApp msg is received.
For you developers:

HTTP POST request to: `https://automation.8x8.com/api/v1/accounts/<yourSubAccountId>/definition`
```json
// JSON body
{
    "subAccountId": "<yourSubAccountId>",
    "trigger": "inbound_chat_apps",
    "status": "enabled",
    "definition": {
        "name": "Auto Reply ChatApps",
        "steps": [
            {
                "id": "send_CA",
                "stepType": "ChatAppsMessage",
                "inputs": {
                    "subAccountId": "<yourSubAccountId>",
                    "user": {
                        "msisdn": "{{data.payload.user.msisdn}}"
                    },
                    "type": "text",
                    "content": {
                        "text": "Hello, thank you for your message!"
                    }
                }
            }
        ]
    }
}
```
