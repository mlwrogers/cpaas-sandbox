---
layout: default
title: OTP example
parent: Verification
nav_order: 1
---

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
