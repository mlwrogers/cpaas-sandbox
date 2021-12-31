---
layout: default
title: Send single SMS
parent: SMS
nav_order: 1
---

A simple example of the JSON body used to send a single SMS.

```js
{
    "clientMessageId": "123xyz",
    "source": "<your_source_SID",
    "destination": "<the_destination_E.164_number",
    "text": "Show me the API is working!",
    "encoding": "AUTO"
}
```
