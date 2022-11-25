---
layout: default
title: How do i configure SSO
parent: What is Connect?
grand_parent: The Basics
---

## Configuring SSO

This assumes that you already have an SSO application that will be used to configure your SSO. If you do not have one yet, you might want to check these popular SSO services like [OKTA](https://www.okta.com/products/single-sign-on/) and [OneLogin](https://www.onelogin.com/product/sso).  

Only users with “admin” access to 8x8 Connect are allowed to configure SSO. If you do not have “admin” access, please contact your system administrator or any user from your account that has “admin” access to the customer portal (8x8 Connect).  

SSO is only available to enterprise customers. If you want to check your account, please contact our support team [cpaas-support@8x8.com](mailto:cpaas-support@8x8.com) or get in touch with your account manager directly.

## Configuration Steps

1.  Login to the 8x8 Connect portal with an admin role https://connect.8x8.com/

2.  Select ‘Users’ from the main menu on the left, or click the upper-right gear icon and select “User management”

![UserManagement](/cpaas-wiki/image_assets/connect/UserManagement.png)

3.  Once inside the user management page, click the “Configure Single Sign-On” button, located top right.. 

![UsersButton](/cpaas-wiki/image_assets/connect/UsersButton.png)

4.  The SSO configuration page will appear, where you will need to complete the required information.  

You will need to copy the URL we have generated and paste it into your SSO identify providers' configuration.

![UsersButton](/cpaas-wiki/image_assets/connect/SsoConfig.png)

5.  Login to the admin portal for the SSO application you intend to use and navigate to your identity provider SAML settings. 

Copy the URL generated and displayed in the previous step and and paste it into the Single Sign-On URL in your SSO providers configuration.

For example, below you can see the URL has been input as the value under OKTA SAML settings.

![SamlSettings](/cpaas-wiki/image_assets/connect/SamlSettings.png)

6.  Next, copy the identity provider's URL (the SAML endpoint) from your SSO application and paste it into the “Identity Provider URL”  input field within the 8x8 Connect configuration.

![IdentityProviderUrl](/cpaas-wiki/image_assets/connect/IdentityProviderUrl.png)

7.  Next, copy the provider issuer ID or “Entity ID” from your SSO application and paste it on the “Identity Provider Issuer” input field within the 8x8 Connect SSO configuration.

![EntityId](/cpaas-wiki/image_assets/connect/EntityId.png)

Most SSO applications generate and provide this information for you. For example, OKTA provides this within the “Identity provider metadata”.

![OktaExample](/cpaas-wiki/image_assets/connect/OktaExample.png)

Here you can see the result after clicking the Identity provider metadata in OKTA configuration.

![OktaMetaData](/cpaas-wiki/image_assets/connect/OktaMetaData.png)

The URL itself is the Identity provider URL while an XML key called entityID is your Identity Provider issuer.

8.  Most SSO applications also provide x509 certificates, you can copy the contents of this certificate  (which looks something like this example image below) and paste it into the “Key x509 certificate” text area field within 8x8 Connect Configuration.  

![OktaX509](/cpaas-wiki/image_assets/connect/OktaX509.png)

9.  Once all config fields in the 8x8 Connect SSO configuration have been completed, click “Save”   

![OktaComplete](/cpaas-wiki/image_assets/connect/OktaComplete.png)

10.  Log out of the customer portal and now try to log in using SSO.

![LoginWithSso](/cpaas-wiki/image_assets/connect/LoginWithSso.png)

### Notes when using SSO:

By default, all users without “admin”(administrator) access will be forced to log in via SSO once it is configured. Users with “admin” access, they can choose to use the normal login using a username/password combination or via SSO.

## How to disable SSO

1.  Login to the customer portal using a user with “admin” privileges.

2.  Select ‘Users’ from the main menu on the left, or click the upper-right gear icon and select “User management”

![UserManagement](/cpaas-wiki/image_assets/connect/UserManagement.png)

3.  Once you are inside the user management page, the SSO setting should be visible on top and assuming it is already set. Just click “Change Setting” and then click “Disable SSO”

![DisableSso](/cpaas-wiki/image_assets/connect/DisableSso.png)

4.  Confirm your deletion by clicking “Yes, disable Single Sign-On”.

![ConfirmDisableSso](/cpaas-wiki/image_assets/connect/ConfirmDisableSso.png)
