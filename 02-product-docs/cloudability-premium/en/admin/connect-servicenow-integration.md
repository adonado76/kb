---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "Connect to ServiceNow"
breadcrumb:
  - "Cloudability Premium"
  - "Getting data into Cloudability"
source_path: "admin/connect-servicenow-integration.html"
images:
  - "images/ServiceNow-Creds.jpeg"
  - "images/servicenow_integration-1.jpg"
  - "images/servicenow_integration-2.jpg"
  - "images/vc_ss8.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Connect to ServiceNow

**Overview**

This guide walks you through the process of connecting your **ServiceNow** accountto
IBM Cloudability. Once connected, you’ll gain access to using ServiceNow within Cloudability.

**Prerequisites**

Before you begin, ensure the following:

- You are a  Cloudability  administrator.
- Your organization uses ServiceNow Cloud.
- The administrator for your ServiceNow instance is available during the setup process.
- You have the domain name for your ServiceNow instance.

**ServiceNow** Account Credentialing process involves a few steps which will require you to take
actions in both ServiceNow console and Cloudability at various phases.

During this process Cloudability will use your ServiceNow domain to connect with your
account.

**Step 1 - ServiceNow Console**

- Note the Domain Name of your ServiceNow Cloud. e.g. https://xxxyyy.service-now.com

**Step 2 - Cloudability**

In the Cloudability console:

1. In Cloudability , navigate to  **Settings**  > **Vendor Credentials**  >  **Add Datasource**  >  **ServiceNow**  . The  **Add
   ServiceNow Account**  panel opens.
2. Enter the domain name of your  **ServiceNow**  instance.

   Select  **Save**  .
3. Click  **Generate Script and Download the script**  .

**Step 3 - ServiceNow** 
**Console**

1. In your ServiceNow instance, navigate to  **System Definitions**  >  **Fix Scripts**  .
2. Click  **New**  .
3. Provide the Name as Cldy Script.
4. Paste the generated script from the previous step into the  **Script**  section.
5. Make sure  **Application**  is set to  **Global**  .
6. Click  **Submit**  .
7. Go to the created  **Cldy Script**  .
8. Click  **Run Fix Script and Proceed**  .
9. Navigate to  **System Security**  >  **Users**  .
10. Search for the Name  **CldyUser\_Script**  . Note the  **User ID.**
11. Click  **Set Password**  , and then type and save the password. Note the password down if
    required.

    ![servicenow integration screenshot](../../../../03-media/cloudability-premium/images/servicenow_integration-1.jpg)
12. Navigate to  **System OAuth**  >  **Application Registry**  .

    ![application registry screenshot](../../../../03-media/cloudability-premium/images/servicenow_integration-2.jpg)
13. Search for the name  **Cldy OAuth Client**  . Note the  **Client Id**  .
14. Click the lock button of the  **Client Secret**  . Copy the  **Client Secret**  .

![](../../../../03-media/cloudability-premium/images/ServiceNow-Creds.jpeg)

**Step 4 - Cloudability**

Navigate to the Cloudability console, and enter the following details which were captured in the
previous step:

1. Enter the  **User ID**  .
2. Enter the  **Password**  .
3. Enter the  **Client ID**  .
4. Enter the  **Client Secret**  .
5. Click  **Save**  .

   ![servicenow edit credential screenshot](../../../../03-media/cloudability-premium/images/vc_ss8.jpg)

**How to confirm success**

Check the status under  **Settings > Vendor Credentials > ServiceNow.**  A green tick
mark indicates that the integration is successful.

**Frequently Asked Questions**

**I followed the above steps but my account status is still red. What should I do?**

Please check if you have entered the details correctly e.g Domain name, User Id, Password,
ClientId and Client Secret.

**How can I edit the details of ServiceNow Integration?**

Click on the 3 dots beside the account and click edit. Add the details and save the
credential.

In case the domain has changed , please add a new credential by following all the steps mentioned
in this integration. Please delete the old account before doing so.
