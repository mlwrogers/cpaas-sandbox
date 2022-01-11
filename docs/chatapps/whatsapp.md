---
layout: default
title: How to link into WhatsApp
parent: ChatApps
nav_order: 1
---

# How to link into WhatsApp

Universal links are the preferred method of linking to a WhatsApp account, this is officially documented by WhatsApp [here.](https://faq.whatsapp.com/iphone/how-to-link-to-whatsapp-from-a-different-app/?lang=en)

## See It In Action

Dive right in and watch this 30 second demonstration on how to initiate a WhatsApp conversation with your customers via a QR code before getting to the details and trying it out for yourself!

<iframe width="560" height="315" src="https://www.youtube.com/embed/AtxO74GRW8o" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

# The basics

The base structure for these links is extremely simple to use: `https://wa.me/<whatsappphonenumber>` where `<whatsappphonenumber>` is the full phone number, in international format, of _your_ WhatsApp business account.  i.e. The destination account that the message will be sent to.

This simple scheme can be extended to include a pre-filled text message `https://wa.me/<whatsappphonenumber>/<?text=urlencodedtext>` enabling you to make things even easier for your customers to start engaging with you about a specific topic.

_Note: The pre-filled text must be url-encoded text.  There are many 3rd party tools available to generate url-encoded text if this is unfamiliar to you, such as this simple [online text tool:](https://onlinetexttools.com/url-encode-text)_
{:.text-purple-200}

These links can obviously be used in any number of places or hidden behind simple website buttons.  Here are a few working examples which will open up your own WhatsApp account ready to send a message to a specific WhatsApp business contact with a pre-composed message.  

## Buttons

A quick and easy way to use universal links from your website is to just make a few simple buttons.  You can use multiple links so as to have different pre-filled messages depending on the context, i.e. Support vs Sales vs Returns.
**Try it out!**

This button will initiate a conversation by sending a message into the 8x8 Converse Sandbox, from which an agent can respond and continue to have a 2-way conversation with the customer via WhatsApp.

_Note: for more information about 8x8 Converse, take a look at the overview at the [CPaaS documentation site here.](https://developer.8x8.com/connect/docs/converse-overview)_
{:.text-purple-200}

**Try Me**👇

[Converse](https://wa.me/6569507977?text=Hi%208x8%20team%2C%20I'd%20love%20to%20chat%20with%20someone%20about%20your%20APIs%20to%20help%20boost%20my%20customer%20engagement!%20%F0%9F%9A%80){: .btn .btn-green }

The pre-filled message used to initiate this interaction is: "Hi 8x8 team, I'd love to chat with someone about your APIs to help boost my customer engagement! 🚀 "  
The text is url-encoded and the final link used behind this button looks like this:  
```
https://wa.me/6569507977?text=Hi%208x8%20team%2C%20I'd%20love%20to%20chat%20with%20someone%20about%20your%20APIs%20to%20help%20boost%20my%20customer%20engagement!%20%F0%9F%9A%80
```

This button will initiate a conversation by sending a message into the 8x8 CPaaS Zendesk Account, from which a support agent can respond back and forth with the customer.

_Note: for more information on our WhatsApp and Zendesk integration, take a look at the [CPaaS documentation site here.](https://developer.8x8.com/connect/docs/zendesk-support)_
{:.text-purple-200}

**Try Me**👇

[Zendesk](https://wa.me/639212335185?text=Hi%208x8%20team%2C%20I%20need%20some%20technical%20assistance%20%F0%9F%9B%A0%EF%B8%8F%20.%20Please%20can%20you%20help%20me%3F%20%F0%9F%99%8F){: .btn .btn-blue }

The pre-filled message used to initiate this interaction is:  Hi 8x8 team, I need some technical assistance 🛠️ . Please can you help me? 🙏  
The text is url-encoded and the final link used behind this button looks like this:
```
https://wa.me/639216812646?text=Hi%208x8%20team%2C%20I%20need%20some%20technical%20assistance%20%F0%9F%9B%A0%EF%B8%8F%20.%20Please%20can%20you%20help%20me%3F%20%F0%9F%99%8F
```

## QR Codes

Another great way to help customers initiate conversations with your business via WhatsApp is by using QR codes.  The great thing about a QR code is that you can make a single QR image work for both desktop and mobile users.  As the majority of people use WhatsApp only on their mobile device, if they're viewing your QR code on their desktop/laptop computer they can simply scan it with their mobile phone camera! If they are viewing the QR code on the mobile itself, you can make the QR image clickable and invoke the same user experience.
**Try it out!**

This QR code will initiate a conversation by sending a message into the 8x8 Converse Sandbox, from which an agent can respond and continue to have a 2-way conversation with the customer via WhatsApp.
**Scan or click Me**👇

[![Initiate msg to Converse](https://mlwrogers.github.io/cpaas-sandbox/image_assets/UTG5HWVNLLZ7F1_converse_demo.png)](https://wa.me/message/UTG5HWVNLLZ7F1)

The pre-filled message used behind this QR to initiate this interaction is:  Hi 8x8 team, I need some technical assistance 🛠️ . Please can you help me? 🙏  
The final link used behind this QR code looks like this:
```
https://wa.me/message/UTG5HWVNLLZ7F1
```

_Note: This QR was generated using the QR tool available within the WhatsApp Manager.  This also provides a URL shortening service to obfuscate the WhatsApp business account Phone number.  If you want to create **funky** QR's with colours and logos this is also possible using one of the many 3rd party QR generator tools available._
{:.text-purple-200}
