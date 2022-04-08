---
layout: default
title: What is an MAU?
parent: JaaS_FAQ
grand_parent: JaaS
---

## What is an MAU?
or
## How does JaaS identify MAUs for billing/accounting?

MAU stands for Monthly Active User.  Each MAU represents a single participant who has attended at least one meeting with at least one other participant during your monthly billing cycle.
To identify an MAU, JaaS installs an identifier on the local storage of a user's meeting device (e.g., laptop, tablet, phone).

For example, if you invite three persons to join the meeting, then this will add three MAUs as usage data to your account if each participant joins from a single device. However, if someone joins from a laptop, as well as a phone, then the usage recorded will increase to four MAUs, since we're counting both devices for that same user. In this example, you can have up to nine MAUs recorded for three users if they join from multiple devices.

We provide an overview of the current usage for your account on the "Activity" page of your JaaS Console, so you can check the live status of your usage. To learn more, see the other articles in this FAQ and refer to the [JaaS Console documentation](https://developer.8x8.com/jaas/docs/jaas-console-activity)

## Extra examples

For these examples, lets assume a rate of $0.25. Let's look at two extremes, a light vs a heavy user.

### Alice
* Alice is a user of your app, which is using JaaS. She works in the finance department at her company.  
* Alice makes 5 calls a day from her laptop, each call has 4 participants, including herself.  
  * Each call is to other users inside the company.  They all use your app/JaaS. In total, 100 calls per working month.  
  * JaaS does not care how many minutes or hours those calls are.
* The monthly cost for Alice wold be just 1 MAU at only $0.25, despite all the calls she made.
This is because all the other people on all her calls are also users of your same app, each is therefore only counted once per month.
  * Each of those 4 persons are counted and charged at 1 MAU but its not on top of each other. i.e.
    * Alice - 0.25
    * Person 2 - 0.25
    * Person 3 - 0.25
    * Person 4 - 0.25
  * In the example we are only looking at Alices calls and cost.
* Alice could be classified as a light user, in terms of cost.

### Bob
* Bob is another user at the same company, again using your app which is using JaaS.  Bob works in the sales team.  
* Like Alice, Bob makes 5 calls a day, he also has 4 participants on each call including himself.
  * 60% of his monthly calls (60) are with internal users only.
  * Of the remaining 40 calls, each have 2 external customers (‘guests’) on the calls.
  * Half (20) of those calls are with his regular 5 customers.
  * JaaS does not care how many minutes or hours those calls are.
* For all 60 internal calls per month, Bob is counted as only 1 MAU at $0.25.  There are no additional MAU counts for other users added to bobs user cost.
* For the 20 calls with his 5 regular customers (1 call each week per customer), the same 2 people from each customer attends these weekly calls. - counted as only 10 MAU
* The last 20 calls are each with new potential customers, each call has 2 new people from the customer + Bob & his colleague - counted as 40 MAU, i.e. just the 2 new people per customer call.
* Bob is using 51 MAU this month.
* The monthly cost for Bob is  $12.75
* Bob could be classified as a heavy user, in terms of cost.

### In Summary
Obviously there is a big difference between the usage and cost of the two users in the above examples, which is why looking at your target customer/s and the averaging out usage across a whole service is so important when calculating your business model.  All UC/meetings/video/chat products work on a similar principle, some users will 'cost' more than others.
