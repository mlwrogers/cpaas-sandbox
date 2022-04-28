---
layout: default
title: Where can i find JaaS information?
nav_order: 2
parent: JaaS
---

# Where can i find information?

## The JaaS Console  
[https://jaas.8x8.vc/#/](https://jaas.8x8.vc/#/)
This is the JaaS console and hopefully the starting point for your journey. :-).
Here you can sign up for a free developer account, which includes up to 25 MAU, to help get you going and start to test, evaluate and use JaaS.  This portal includes everything you need to start from creating your API key/s and first JWTs through to the basic branding, checking your activity and also contacting support.  Note that the advanced per room branding is handled programmatically, see information at link #2 below for that.  The other configurable items are handled either through the JWT documentation or through the use of configoverwrite and the Jitsi config.js.
Should you choose to use the contact support option in the portal during your early days please do also send the question to myself and MB as well and/or let me know the ticket number so that we can assist you directly as well as letting our support team know that we are in direct communication.

## JaaS documentation  
[https://developer.8x8.com/jaas/docs/jaas-onboarding](https://developer.8x8.com/jaas/docs/jaas-onboarding)
Here you can find the complete documentation for 8x8 JaaS.  This covers all of the 8x8 "layer", everything JaaS related that is not specific to the underlying Jitsi itself.  There are also several sections that have direct links into the Jitsi handbook for easy reference, such as:

* The Section on ui customisation using config overwrite. [https://developer.8x8.com/jaas/docs/customize-ui-overview](https://developer.8x8.com/jaas/docs/customize-ui-overview)
* The section on the advanced per room branding. [https://developer.8x8.com/jaas/docs/jaas-prefs-advanced-branding](https://developer.8x8.com/jaas/docs/jaas-prefs-advanced-branding)

## The Jitsi Handbook  
[https://jitsi.github.io/handbook/docs/dev-guide/dev-guide-iframe](https://jitsi.github.io/handbook/docs/dev-guide/dev-guide-iframe)
This is the Jitsi handbook, it is the holy grail for Jitsi!
There are two main approaches available to you with JaaS, using the iframe (and/or mobile sdks) or the low level lib-jitsi-meet API.  The large majority of our customers all use the iframe/sdk route as this offers the fastest route to market combined with ongoing ease of implementation and maintenance.  You may be surprised just how much you can still customize and control using the iFrame and/or SDK's instead of the low level API.
