---
layout: default
title: Does JaaS support call Recording?
parent: JaaS_FAQ
grand_parent: JaaS
---

## Does JaaS support call Recording?

Yes!  JaaS supports video call recording at an extra cost of $0.01 per min.

Learn more about [JaaS pricing here](https://jaas.8x8.vc/#/pricing).

Recording can be initiated by the moderator (with recording permissions set in the [JWT](https://developer.8x8.com/jaas/docs/jaas-onboarding#the-jitsi-jwt1) or via the [iFrame API](https://jitsi.github.io/handbook/docs/dev-guide/dev-guide-iframe/#startrecording)

Call recording files are temporarily stored in the 8x8 cloud for 24 hours and can be retrieved via a link available in the UI and/or delivered via a Webhook event (data retention period is 24 hours).
Alternatively users can select to store via Dropbox, only if enabled.

**To retrieve via webhook** At the end of a call, when the recording stops, JaaS uses the _RECORDING_ENDED_ webhook event to pass you the details for the call recording, including a preAuthenicatedLink to the location of that file to eanble you to downloaded it.

Learn more about the [RECORDING_ENDED webhook here](https://developer.8x8.com/jaas/docs/webhooks-payload#recording_ended)

Once downloaded you can store the call recording within your own data storage, for as long as you like.  

The call recording is deleted from the 8x8 cloud when the 24 hours expires. Once deleted, it is impossible to restore and it absolutely not stored on any 8x8 server, anywhere.
