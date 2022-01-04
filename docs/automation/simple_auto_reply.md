---
layout: default
title: Simple auto reply, SMS
parent: Automation
---

# A simple Auto-Reply Demo for SMS

This will demonstrate how to create a very simple workflow that sends an auto-reply whenever an inbound SMS msg is received.
For you developers:

HTTP POST request to: `https://automation.8x8.com/api/v1/accounts/<yourSubAccountId>/definition`
```json
// JSON body
{
    "subAccountId": "<yourSubAccountId>",
    "trigger": "inbound_sms",
    "status": "enabled",
    "definition": {
        "name": "Auto Reply SMS",
        "steps": [
            {
                "id": "send_sms",
                "stepType": "SMS",
                "inputs": {
                    "subAccountId": "<yourSubAccountId>",
                    "source": "8x8 Dev",
                    "destination": "{{data.payload.source}}",
                    "text": "Hello, thank you for your message!",
                    "encoding": "Auto"
                }
            }
        ]
    }
}
```
