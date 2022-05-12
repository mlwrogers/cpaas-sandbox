---
layout: default
title: How to connect with SMPP.
parent: SMS
parent: How-to's and Examples
grand_parent: SMS
---

## How to connect with SMPP.


📘  You can find the complete documentation for our SMPP support on our [developer website here.](https://developer.8x8.com/connect/reference/smpp-connection)
{: .text-blue-000 }

A summary of how to connect to us using SMPP is below.

1. Before you can successfully bind to the 8x8 SMPP environment you must have a Connect account and have already spoken to you 8x8 Account manager to onboard your account for SMPP.
  - Due to the sensitivity and resource requirements of SMPP, you are required to have a dedicated account manager for SMPP connectivity. Please contact us if you have not yet been allocated to someone directly.
  - If you do not yet have a connect account, you check out the `basics` section of this wiki for instructions on [creating a new Connect account.](https://mlwrogers.github.io/cpaas-wiki/docs/basics/connect_createAccount/)
2. Once onboarded by working with your account Manager, we will provide you with the username and password required for your connection.
3. 8x8 SMPP environment has multiple servers. To benefit from our fault-tolerant, high availability platform we prefer SMPP customers to connect directly to our hostname. Based on location and traffic load your application will be automatically connected to the best server.
4. We have two primary regions for SMPP termination, our Signapore (SG) Data Center and our UK Data Center.  By default all new accounts are initially created in the SG DC unless explicitly requested.  Note that accounts can be moved from SG to UK by request.

📘  You should connect to 8x8 SMPP servers using SMPP version 3.4.
{: .text-blue-000 }

Below are the connection details required to connect:

| Setting          | Value (SG DC)    | Value (UK DC)    |
|:-----------------|:-----------------|:-----------------|
| IP address       | smpp.8x8.com     | smpp.8x8.uk     |
| Port             | 2775             | 2775             |
| Port for SSL/TLS | 2776 (TLS v1.2)  | 2776 (TLS v1.2)  |
| system_id	       | your `username`  | your `username`  |
| password	       | your `password`  | your `password`  |

### Username and Password

Your subAccount Id will be used as your SMPP `username / system_id` and will be provided by your 8x8 Account Manager as part of the onboarding and setup process.

### Binding
**SMPP Connection**
You can connect to 8x8 SMPP servers using bind_receiver and bind_transmitter or bind_transceiver. Typically we provide one account id with multiple sub-account ids; for different routing, products or services.

🚧  8x8 SMPP platform allows a maximum of 4 binds per subAccountId. Your bind will be rejected if your try to exceed this value.
{: .text-yellow-300 }

For relaying DLR
 back to your platform, 8x8 servers will send back deliver_sm to any bind connected with the same systemId of the originating submit_sm PDU. This includes if you are sending from multiple sites; we will send to any active bind.

📘  You can find the DLR documentation our [developer website here.](https://developer.8x8.com/connect/reference/smpp-delivery-receipts)
{: .text-blue-000 }

### Throughput
Throughput is tailored to each customer’s requirement during our onboarding process. By default you will be able to submit a maximum of 50 messages per second for each connected bind (50 TPS).  

We support 4 binds per subAccount, therefor you have a total of 200 TPS across 4 binds for each configured subAccount.  You can have multiple subAccounts.

If you have high volume requirements and need to increase the number of configured subAccounts or the TPS for your subAccount/s please contact your account manager to discuss your requirements.

### PDUs
The following PDUs are supported by 8x8 SMPP servers:

- bind_receiver
- bind_transmitter
- bind_transceiver
- submit_sm
- enquire_link
- deliver_sm_resp
- unbind

📘  You should send PDUs in the format as required by SMPP Protocol Specification v3.4.
{: .text-blue-000 }

📘  You can find the complete documentation for our SMPP support on our [developer website here.](https://developer.8x8.com/connect/reference/smpp-connection)
{: .text-blue-000 }
