---
layout: default
title: 2-way SMS in 2 mins
parent: SMS
nav_order: 4
---

**_DRAFT_**

# A 2-way SMS app in less than 2 mins!

Credit: This was contributed by [Filipe Leitao.](https://github.com/fleitao/)
{: .fs-2 }

This short guide will help you to build a simple node.js app that will enable you to send and receive SMS messages straight from your terminal/bash.

## What You'll Need

* [ngrok](https://ngrok.com/) (optional)
* [8x8 Connect Account](https://connect.8x8.com/login)
* 8x8 Virtual Number for SMS
* [node.js](https://nodejs.org/)

## Getting Started

### ngrok

Skip this step if your are working on a VPS with public IP address.
If you're using your own machine to host the webhook server, download ngrok if you have not already. It is a handy tool that provides an external URL to map to localhost:port.
The application defaults to port 8088, so launch ngrok http mapping to port 8088:

`$ ngrok http 8088`

Be sure to copy the forwarding ngrok url, we’ll need that later to configure the webhook.

### 8x8 Connect account

1. Create a 8x8 Connect Account ([here](https://connect.8x8.com/login/signup))
2. Reach out to your 8x8 Account Manager for testing credit and a 8x8 SMS number
3. Once in, fetch your credentials (AccountID, SubAccountID and API Key) directly from the [8x8 Connect API Key dashboard](https://connect.8x8.com/messaging/api-keys)

### node.js

For this app I'm using [axios](https://axios-http.com/) to execute HTTP requests and [express](https://expressjs.com/) to create the webapp/webhook that will be listening to incoming messages.
You can fetch and install those dependencies by executing the following on the root directory of the app:

`npm install axios`

`npm install express`

## The Basics

Before executing the scripts there are two things you'll need to take care first.

### Setup connect.json

Add your 8x8 Connect credentials to connect.json. Fetch your credentials from [8x8 Connect API Key dashboard](https://connect.8x8.com/messaging/api-keys) and edit `connect.json` by replacing the defaults with yours:

 ```
 {
    "accountID": "your_accountID_here",
    "subAccountID": "your_subAccountID_here",
    "apiToken": "your_apiKey_here",
    "number": "your_smsNumber_here"
}
 ```

### Setup the webhook

So that the messages sent to your 8x8 number reach your webhook we need to configure that first. If you are using your own VPS simply use your IP address + `/sms` + `:8088`. If you are using ngrok simply take the url provided when you launched the service and add '/sms'

`$ node 8x8-update-sms-webhook.js http://ngrok-url-from-your-machine/sms`

## Light It Up

You should be ready to try the app now. Lets test this out in the following order:

1. Start the webhook listener app
2. Use the script to send a message to your phone
3. Reply back to that number and see the message coming into your bash prompt


### Start the webhook

`$ node 8x8-receive-sms.js`

### Send a message to your phone

`$ node 8x8-send-sms.js +447771649919 "Hey are you there?`

### Reply to that message

Once the message gets into your phone simply reply back and you'll see it coming in through your webhook.

## See It In Action

<iframe width="560" height="315" src="https://www.youtube.com/embed/UbM2cLXkpQM" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Extra Resources

The node.js scripts used for this demonstration may be accessed from Filipe's Github repository [here.](https://github.com/fleitao/the-8x8-collection/tree/main/sms-simple-2-way)
