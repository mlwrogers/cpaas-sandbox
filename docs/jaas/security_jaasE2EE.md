---
layout: default
title: Does JaaS/Jitsi support End to End Encryption (E2EE)?
parent: Security & Compliance
grand_parent: JaaS
nav_order: 4
---

## Does JaaS/Jitsi support End to End Encryption (E2EE)?

In short, Yes.
Here is a good overview of how Jitsi/JaaS is working for both 1:1 and 1:N calls and how encryption is handled for each.

**Jitsi/JaaS meetings operate in 2 ways: peer-to-peer (P2P) or via the Jitsi Videobridge (JVB). This is completely transparent to the user.**

## Peer-to-Peer (P2P)

P2P mode is only used for 1:1 meetings. In this case, audio and video are encrypted using DTLS-SRTP all the way from the sender to the receiver, even if they traverse network components like TURN servers.  It means it’s actually fully End to End Encrypted (E2EE) between those two participants.  

📘  Optionally, you can disable P2P programmatically and force even 1:1 calls to go via the JVB should you wish.  In that case 1:1 calls would then operate the same as the 1:N calls described below.
{: .text-blue-000 }

📘 You need to be aware that if you start a call recording on a 1-1 call then the call will automatically become a 1:N call, as described below.
{: .text-blue-000 }

## Multiparty calls, 1:N

In the case of 1:N (multiparty) meetings all audio and video traffic is still encrypted on the network (again, using DTLS-SRTP) but this outer layer of DTLS-SRTP encryption is removed temporarily while packets are traversing the JVB; note that they are never stored to any persistent storage and only live in memory while being routed to other participants in the meeting.
This latter form of encryption for multi-party meetings is sometimes what other vendors and/or those who don’t really understand E2EE will still try to claim as E2EE.  It’s strong protection and still very good but it’s not actually true E2EE.

All types of JaaS endpoints support the above scenarios by default.

### E2EE for 1:N calls!

First of all, “True” End to End Encryption (E2EE) is not enabled by default for 1:N calls.  This is because most customers also want to support PSTN dial-in, call recording and similar features which by there own nature cannot be full E2EE. True E2EE can be easily enabled, that said Jitsi/JaaS offers _very strong protection_ even if you don’t explicitly turn on E2EE.

When you explicitly enable the Jitsi E2EE feature it works in addition to DTLS-SRTP and adds another 2nd layer of encryption inside the already encrypted stream using _Insertable streams_.  
It is very important to note that when packets are also E2EE, this second layer of encryption is _never_ removed (nor can it be) at any point until it reaches the destination endpoint.

📘 This extra layer of E2EE we currently only support on desktop endpoints, it will work in any browser that has support for WebRTC insertable streams. Today that means any browser which is based on Chromium 83 and above, i.e. Google Chrome, Microsoft Edge, Brave and Opera.   The actual W3 spec can be found here: https://www.w3.org/2019/09/18-mediaprocessing-harald-insertable-media-processing.pdf
Because of the extra resources required to support E2EE we currently also limit a true E2EE call to 20 participants.
{: .text-blue-000 }

📘 Because of how true E2EE works, this only works for 'on-net' meetings. i.e. If you add a PSTN participant or wish to record the call you cannot have true E2EE enabled for that call.  This is true for any solution, not just Jitsi/JaaaS.
{: .text-blue-000 }

## Summary
E2EE makes for interesting conversations with your security conscious customers as you can give them the choice between still being encrypted and secure and using features like call recording and PSTN dial-in  OR to be 100% e2ee for the utmost security when needed, but minus those features.  The end customer can then decide which is most important for them.

If you are technically minded, there is also an interesting [blog on the Webrtchacks](https://webrtchacks.com/true-end-to-end-encryption-with-webrtc-insertable-streams/) website that explains a bit about how this implementation with insertable streams is working should you/your team want to dive in deeper. 🙂

For some extra history, alongside the W3 spec for this is the IETF’s PERC working group (Privacy Enhanced RTP Conferencing) which was setup to create a transport design that could allow a reasonable path to end-to-end encryption (e2ee) in WebRTC conferences. The idea was that rather than try and tweak the existing DTLS-SRTP implementation, conferences can simply add the additional layer of E2EE protection on top of the existing mechanisms.
… and because Jitsi’s code is availability publicly as it's built from open-source, it ensures that claims of E2E encryption can be vetted and validated by any independent party. 🙂

📘  The Jitsi & 8x8 team obviously want to offer this same extra/True E2EE ability for Mobile Jitsi/JaaS endpoints as well.  We are actively working on this and hope to have support for it in production in the near future.

In addition to the call encryption available in Jitsi itself we also have plenty of documentation available to cover 8x8 organisational practices, T&C, GDPR, HIPAA etc. etc.

* [8x8 Privacy Policy:](https://www.8x8.com/terms-and-conditions/privacy-policy)
* [8x8 Security site:](https://www.8x8.com/why-8x8/security)

* [8x8 CPaaS Service Terms](8x8.com/cpaas-order-terms/cpaas-service-terms) — _Section 6. DATA PROTECTION AND SECURITY._
* [8x8 CPaaS Service Module – Jitsi-as-a-Service](8x8.com/cpaas-order-terms/jaas-module)
* [8x8 API Security](https://www.8x8.com/products/apis/security)

* [JaaS FaQ’s](https://developer.8x8.com/jaas/docs/faq)
* [Domains, IP’s whitelists.](https://developer.8x8.com/jaas/docs/technical-requirements-whitelists)
