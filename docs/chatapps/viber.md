---
layout: default
title: Viber
parent: ChatApps
nav_order: 2
---

## How to link into Viber

Universal links are the preferred method of linking to a Viber account, this is officially documented by Viber here. [placeholder]()

The base structure for these links is extremely simple to use as outlined below.

**To open a Viber Chat:**
viber://chat?service=xxx
Where xxx is serviceId of the Viber business account from Viber portal

For Example: viber://chat?service=19459 (opens a direct chat)

**To open a Viber business profile page:**
viber://ca/info?id=yyy
Where yyy is the business ID

For example: viber://ca/info?id=4422 (opens business profile)

## Buttons

These links can obviously be used in any number of places or hidden behind simple website buttons.  Here are a few working examples which will open up your own Viber account ready to send a message to a specific Viber business contact.

A quick and easy way to use universal links from your website is to just make a few simple buttons.
**Try it out!**

This button will initiate a conversation by sending a message into the 8x8 Converse Sandbox, from which an agent can respond and continue to have a 2-way conversation with the customer via Viber.

_Note: for more information about 8x8 Converse, take a look at the overview at the [CPaaS documentation site here.](https://developer.8x8.com/connect/docs/converse-overview)_
{:.text-purple-200}

**Try Me**👇

[Converse](viber://chat?service=19459){: .btn .btn-purple }
