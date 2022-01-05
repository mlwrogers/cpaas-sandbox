---
layout: default
title: Send a One Time Password
parent: Mobile Verification
nav_order: 1
---

**_DRAFT_**

# How to send a One Time Password _(OTP)_ via SMS

An example of the JSON body used to generate and send a code via SMS.

```js
// HTTP POST request used to generate and send the code via SMS
{
     "channel": "call",
     "codeLength": 4,
     "codeValidity": 300,
     "codeType": "NUMERIC",
     "language": "en-US",
     "resendingInterval": 10,
     "sms": {
          "source": "8x8Dev",
          "encoding": "AUTO"
     },
     "call": {
          "source": "<your_source_SID>",
          "speed": 0.8,
          "repetition": 2,
          "voiceProfile": "en-GB-Emma"
     },
     "destination": "+441234567899",
     "resetSession": false
}
```

## Building a simple Mobile Verification App

<iframe width="560" height="315" src="https://www.youtube.com/embed/Ft6-aOSxzmo" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
