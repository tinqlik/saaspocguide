---
layout: default
title: Okta
parent: Configuring IDP
nav_order: 1
---
<!--#
LASTVERIFIEDDATE=11/01/2020
$-->

# Configuring Okta
{:.no_toc}
By default, tenants are set up using Qlik’s Identity Provider.  Tenant administrators can change the environment to leverage the organization’s own Identity Provider (e.g. Auth0, Okta, KeyCloak, etc.).  Ideally this should be done before users have been invited to the tenant and started to create apps, but changing IdPs after assets have been created is supported.
The benefit for using a 3rd party IdP is that user lists can be imported through an organization’s directory instead of inviting users to create a Qlik account.  In addition, as of {{LASTVERIFIEDDATE}}, only 3rd party IdPs allow group information to be brought into the Qlik SaaS environment which will be useful when assigning access to the various Spaces.

## Summary
{:.no_toc}
Okta provides a [developer edition](https://developer.okta.com/signup/) of their IdP that is free to set up and use that does not expire.  

### Set-up Okta Application
Once you have an Okta account, an application needs to be created to interact with Qlik Sense.

1.  Navigate to the **Administration** console.  In the menu bar, click on **Applications**
![okta1](images/okta1.png)

2.  Click on the button, **Add Application**\
![okta2](images/okta2.png)

3.	Click on the button, **Create New App**\
![okta3](images/okta3.png)

4.	Select the following:
    1. **Platform** - Web
    2. **Sign on method** - OpenID Connect
    ![okta4](images/okta4.png)

5.	Fill in the form with the following:
    1. **Application Name** - QCS
    2. **Login redirect URIs** – QCS tenant URL + /login/callback (e.g. *https://tinqcs.us.qlikcloud.com/login/callback*)
    ![okta5](images/okta5.png)

6.  Once the application is Saved, Client Credentials will be generated.  This will be used to enable a secure communication between Okta and the Qlik Sense SaaS tenant.  Copy these values into a text editor like **Notepad** for easy reference when configuring Qlik Sense
![okta6](images/okta6.png)

7.  Click on the **Sign On** tab if you want to retrieve Group information for users from Okta.  This can be done using string-based filter, or using Okta expression language (https://developer.okta.com/docs/reference/okta-expression-language/).  In this example, we will bring in Groups that start with *Qlik*
![okta7](images/okta7.png)

Refer to the Section, [Qlik Groups](../sample_data/groups.md), for detailed instructions on creating the groups that will be used to set up this environment