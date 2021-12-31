---
layout: default
title: Viber
parent: ChatApps
nav_order: 2
---

# How to link into Viber

Universal links are the preferred method of linking to a Viber account, this is officially documented by Viber here. [placeholder]()

The base structure for these links is extremely simple to use:

These links can obviously be used in any number of places or hidden behind simple website buttons.  Here are a few working examples which will open up your own WhatsApp account ready to send a message to a specific WhatsApp business contact with a pre-composed message.  

## Buttons
A quick and easy way to use universal links from your website is to just make a few simple buttons.  You can use multiple links so as to have different pre-filled messages depending on the context, i.e. Support vs Sales vs Returns.
**Try it out!**

This button will initiate a conversation by sending a message into the 8x8 Converse Sandbox, from which an agent can respond and continue to have a 2-way conversation with the customer via WhatsApp.

_Note: for more information about 8x8 Converse, take a look at the overview at the [CPaaS documentation site here.](https://developer.8x8.com/connect/docs/converse-overview)_
{:.text-purple-200}

**Try Me**👇

[Converse](https://wa.me/6569507977?text=Hi%208x8%20team%2C%20I'd%20love%20to%20chat%20with%20someone%20about%20your%20APIs%20to%20help%20boost%20my%20customer%20engagement!%20%F0%9F%9A%80){: .btn .btn-purple }

```js
// The pre-filled message used to initiate this interaction is: "Hi 8x8 team, I'd love to chat with someone about your APIs to help boost my customer engagement! 🚀 "
// The text is url-encoded and the final link used behind this button looks like this:
"link placeholder"
```
