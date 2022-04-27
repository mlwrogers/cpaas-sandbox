---
layout: default
title: Does JaaS support transcription (Closed Caption)?
parent: JaaS_FAQ
grand_parent: JaaS
---

## Does JaaS support real-time transcription (Closed Caption/CC)?

Yes.

JaaS can send the audio captured from all participants in the room to an external speech-to-text service. Currently, only the Google Cloud Speech-to-Text API is supported.

Close Captioning can be enabled by each particpant whilst in the meeting.  

The transcript file is temporarily stored in the 8x8 cloud for 24 hours.  At end of the meeting the transcript of the meeeting will be passed back using the TRANSCRIPTION_UPLOADED webhook event, which 
includes a preAuthenicatedLink to the location of that file to eanble you to downloaded it.

Once downloaded you can then store the transcript within your own data storage, for as long as you like.  

The transcript is deleted from the 8x8 cloud when the 24 hours expires. Once deleted, it is impossible to restore and it absolutely not stored on any 8x8 server, anywhere.

Learn more about the [TRANSCRIPTION_UPLOADED webhook here](https://developer.8x8.com/jaas/docs/webhooks-payload#transcription_uploaded)

This service is charged separately.

Learn more about [JaaS pricing here](https://jaas.8x8.vc/#/pricing).
