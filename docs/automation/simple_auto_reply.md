---
layout: default
title: Simple Auto Reply
parent: Automation
---

# A simple Auto-Reply Demo

This will demonstrate how to create a very simple workflow that sends an auto-reply whenever an inbound SMS msg is received.

For you developers, the JSON body looks like this:

```json
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
