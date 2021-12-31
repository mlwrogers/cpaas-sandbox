---
layout: default
title: How to link into WhatsApp
parent: ChatApps
nav_order: 1
---

# How to link into WhatsApp

Universal links are the preferred method of linking to a WhatsApp account, this is officially documented by WhatsApp [here.](https://faq.whatsapp.com/iphone/how-to-link-to-whatsapp-from-a-different-app/?lang=en)

The base structure for these links is extremely simple to use: `https://wa.me/<whatsappphonenumber>` where the `<whatsappphonenumber>` is the full phone number, in international format, of _your_ WhatsApp business account.  i.e. The destination for the message to be sent.

This simple scheme can be extended to include a pre-filled text message `https://wa.me/<whatsappphonenumber>/<?text=urlencodedtext>` which enables you to make things even easier for your customers to start engaging with you about a specific topic.
Note that the pre-filled message must be url-encoded text.  There are many tools available to help you generate url-encoded text if this is unfamiliar to you, such as this simple [online text tool:](https://onlinetexttools.com/url-encode-text)

These links can obviously be used in any number of places or hidden behind simple buttons.  Here are a few working examples which will open up your own WhatsApp account ready to send to a specific business contact with a pre-composed message.  

## Buttons
A quick an easy way to use universal links from your website is to just make a few simple buttons.  You can use multiple links so as to have different pre-filled messages depending on the context, i.e. support vs sales vs returns.
**Try it out!**

This button will initiate a conversation by sending a message into the 8x8 Converse Sandbox, from which an agent can respond and continue to have a 2-way conversation with the customer via WhatsApp.
_Note: for more information on 8x8 Converse, take a look at the overview on the [CPaaS documentation site here.](https://developer.8x8.com/connect/docs/converse-overview)_

[Converse](https://wa.me/6569507977?text=Hi%2C+I+need+support.+Could+you+assist+me%3F){: .btn .btn-green }

```js
// The link used behind this button looks like this:
https://wa.me/6569507977?text=Hi%2C+I+need+support.+Could+you+assist+me%3F
```

This button will initiate a conversation by sending a message into the 8x8 CPaaS Zendesk Account, from which a support agent can respond back and forth with the customer.
_Note: for more information on our WhatsApp and Zendesk integration, take a look on the [CPaaS documentation site here.](https://developer.8x8.com/connect/docs/zendesk-support)_

[Zendesk](https://wa.me/639216812646?text=Hi%208x8%20team%2C%20I%20need%20some%20technical%20assistance%20%F0%9F%9B%A0%EF%B8%8F%20.%20Please%20can%20you%20help%20me%3F%20%F0%9F%99%8F){: .btn .btn-blue }

```js
// The link used behind this button looks like this:
https://wa.me/639216812646?text=Hi%208x8%20team%2C%20I%20need%20some%20technical%20assistance%20%F0%9F%9B%A0%EF%B8%8F%20.%20Please%20can%20you%20help%20me%3F%20%F0%9F%99%8F
```
## QR Codes
Another great way to help customers initiate conversations with your business via WhatsApp is by using QR codes.  The great thing about a QR code is that you can make a single QR image work for both desktop and mobile users.  As the majority of people use WhatsApp only on their mobile device, if they're viewing your QR code on their desktop/laptop computer they can simply scan it with their mobile phone camera! If they are viewing the QR code on the mobile itself, you can make the QR image clickable and invoke the same user experience.
**Try it out!**

Scanning this QR code will initiate a conversation by sending a message into the 8x8 Converse Sandbox, from which an agent can respond and continue to have a 2-way conversation with the customer via WhatsApp.
_Note: This QR was generated using the QR tool within the WhatsApp Manager which is also shortening the URL to obfuscate the WhatsApp business account Phone number.  There are also many 3rd party QR generator tools available_

![Image](./image_assets/UTG5HWVNLLZ7F1_zendesk_demo.png)
```js
// The link used behind this QR code looks like this:
https://wa.me/message/UTG5HWVNLLZ7F1
```
