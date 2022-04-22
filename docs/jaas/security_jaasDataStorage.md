---
layout: default
title: What data is stored on JaaS servers?
parent: Security & Compliance
grand_parent: JaaS
nav_order: 3
---

## What data is stored on JaaS servers?

All Jitsi/JaaS meeting rooms are ephemeral: that is to say that they only exist whilst the meeting is live.  

The room is created when the first participant joins and is completely destroyed when the last participant leaves. If someone joins the same room again, a brand new meeting room is created that uses the same name but there is absolutely no connection to any previous meeting that might have been held with the same name.

### But what about in-meeting content?

JaaS provides all the in-meeting content, such as chats, call recordings & transcriptions via webhook events to you the application developer.  This gives you the ability to access and/or store if required any in-meeting information on your own servers.  **Nothing** is left on JaaS servers.

You can find information on the available webhooks and what their payloads look like in our [developer documentation here.](https://developer.8x8.com/jaas/docs/webhooks-payload)

## Summary
To summarise, once a call is finished and is destroyed, absolutely nothing is stored on any JaaS server.
For any call where all participants have left and not re-joined, but the/your application has not explicitly destroyed the call, the call will automatically be destroyed after 15 mins.
