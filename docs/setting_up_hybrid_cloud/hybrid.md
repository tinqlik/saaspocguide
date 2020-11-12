---
layout: default
title: Hybrid Cloud
parent: Setting Up Hybrid Cloud
nav_order: 1
---

# Setting Up Hybrid Cloud
{:.no_toc}
Setting up a hybrid Qlik Sense architecture will allow users to leverage the capabilities of Qlik Sense while providing a cost-effective method for scaling out an analytics solution.  There are certain things to keep in mind though when distributing Qlik Sense apps from a client-managed environment into SaaS:\
    - Apps distributed to the cloud are read-only.  Users cannot make any changes in the Cloud hub, such as creating private or community sheets or stories in the app.  To work directly on the app in the Cloud hub, a user with the right privilege will need to export the app and then re-import it into the Cloud hub
    - On-Demand apps are not supported
    - Extensions are not supported for distributed apps.  Visualizations using extensions may not open in the Cloud hub properly as an error will appear indicating the visualization is not found

## Configuring Qlik Sense Client-Managed for Cloud Distribution
Before beginning, it is important to check that the Qlik Sense Enterprise on Windows license is using the **Signed License Key**.  In addition, the license should be the same as the SaaS tenant to leverage the same user licenses

1.  Enable the Qlik Sense Enterprise Client-Managed for Cloud distribution.  Navigate to the **Multi-Cloud Setup Console** by clicking on the **Cloud distribution** link in the QMC under **Configure System**
![hybrid1](images/hybrid1.png)
**Note**: *For Qlik Sense version prior to November 2020, you will need to navigate to the URL https://[host name]/api/msc/*