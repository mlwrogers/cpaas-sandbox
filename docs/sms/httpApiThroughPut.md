---
layout: default
title: What is the SMS throughput for the API?
parent: SMS_FAQ
grand_parent: SMS
---

## What is the SMS throughput for the API?

Throughput can be tailored to each customer’s requirement during our onboarding process.  The default API request rate limit is _1800_ HTTP requests per second per sub-account (this can be adjusted upon request), and _3000_ requests per second per, IP address with no maximum daily quota.

All requests exceeding the configured quota will be rejected by the API with `429 Too Many Requests` HTTP Status.
The API will also return the `Retry-After` HTTP header with the value indicating when the client can retry the request.

Both the SMS and Voice APIs allow you to send either 1 msg per API call or up to 10,000 SMS in a single API call.
The Voice API currently supports up to 2,000 concurrent voice calls, for the TTS msg requests.

If you need to submit a high volume of messages in bulk, we recommend the use of the [Send SMS batch](https://developer.8x8.com/connect/reference/send-many-sms) and/or [Send Many Voice](https://developer.8x8.com/connect/reference/send-many-1) APIs.  These allow you to submit up to 10,000 messages in a single API request, which currently is approximately equivalent to 25,000 messages per second.  
For bulk voice messages we would recommend submitting 2,000 per single request (though the API does support 10,000 as mentioned) our recommnedation is because the 2,000 is then inline with the concurrent voice call limit.
