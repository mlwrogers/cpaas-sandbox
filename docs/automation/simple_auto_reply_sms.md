---
layout: default
title: Auto reply, SMS
parent: Automation
---

# A simple Auto-Reply Demo for SMS

This will demonstrate how to create a very simple workflow that enables an auto-reply message is sent whenever an inbound SMS msg is received.

## See It In Action

Dive right in and watch this short demonstration to see just how quick and easy it is to create the workflow and see it in live in action!  

<iframe width="560" height="315" src="https://www.youtube.com/embed/IMGa7GhNRzg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

# The Technical part

In the video above we used [Postman](https://www.postman.com/downloads/) to quickly create and test this automation.

When you create a new Postman collection for your 8x8 API testing there are a couple initial steps you will need to do in order to get up & running:
1. Grab your API key from the 8x8 Connect portal.
  - If you've never done this before, you can take a look [here.](https://mlwrogers.github.io/cpaas-wiki/docs/basics/apiKey/)
2. Add your API key as the Bearer Token for authenticating requests in postman.
  - For convenience, you may wish to add the token to your collection so that each new request you create simple inherits the same token as shown in the screenshot below.
  ![PostManAuthentication_p1](https://mlwrogers.github.io/cpaas-wiki/image_assets/screenshots/postman_BearerAuth_p1.png)
3. Create a new POST request in your 8x8 API collection.  
  - HTTP POST request to: `https://automation.8x8.com/api/v1/accounts/<yourAccountId>/definition`  
    You need to replace _<yourAccountId>_ with your real 8x8 accountId.  
4. Set the authentication to inherit from your collection.  
  ![PostManAuthentication_p2](https://mlwrogers.github.io/cpaas-wiki/image_assets/screenshots/postman_BearerAuth_p2.png)    
5. Add the json body to the new POST request.  Be certain to changeout the placeholders in the template below with your real information.  
```json
{
    "subAccountId": "<input_your_8x8_subAccountId>",
    "trigger": "inbound_sms",
    "status": "enabled",
    "definition": {
        "name": "<name_your_workflow>",
        "steps": [
            {
                "id": "send_sms",
                "stepType": "SMS",
                "inputs": {
                    "subAccountId": "<input_your_8x8_subAccountId>",
                    "source": "<input_your_sms_virtual_number>",
                    "destination": "{{data.payload.source}}",
                    "text": "<input_the_message_you_want_to_use_in_your_Auto-reply>",
                    "encoding": "Auto"
                }
            }
        ]
    }
}
```  

Save it!  💾  

Send it!  🚀  
