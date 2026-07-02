---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "Connecting with AWS - Upgrading existing Cloudability customers to Cloudability Premium"
breadcrumb:
  - "Cloudability Premium"
  - "Getting data into Cloudability"
  - "Connecting with AWS - Customer Integration Guide"
source_path: "admin/aws-credentialing-premium-upgrading.html"
images:
  - "images/alert.png"
  - "images/turbo.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Connecting with AWS - Upgrading existing Cloudability customers to Cloudability Premium

If you have upgraded to Cloudability Premium, your existing Cloudability credentials
will continue to work in Cloudability - but not for Turbonomic. For both the tools to work together
you will need to re-credential your AWS accounts. This is because more IAM permissions are required
for Turbonomic to work seamlessly with Cloudability.

1. In Cloudability, navigate to **Settings > Vendor Credentials >AWS.**
2. Select an existing Consolidated account by clicking on the …
3. Select the pencil icon to open Edit a Credential.
4. Choose Advanced Rightsizing options as **Read only** vs **Automate Actions**
   - **Read Only** selection implies that you are allowing both Cloudability cost, Turbonomic cost
     and Turbonomic monitoring permissions to read your environment and not take actions.
   - **Automate Actions** selection implies that you are allowing all Cloudability and all
     Turbonomic permissions including the ones for automated actions i.e. Turbonomic execution and
     Turbonomic billing execution.
5. Click Save to Download the template.
6. Update the existing IAM permissions by executing the template in AWS console per this section
   (link to Automated Credentialing of Linked accounts)
7. Re-verify the account via Cloudability UI.
8. Successful verification with be indicated with a green tick.

This needs to be done both for the Consolidated Account and Linked Accounts.

Note: In your
individual linked accounts, the Automate Actions status will display as:

- **OFF** if the **Advanced Rightsizing** toggle was selected as **Read Only** (inherited
  from the Consolidated Account)
- **ON** if the **Advanced Rightsizing** toggle was selected as **Automate Actions**
  (again, inherited from the Consolidated Account)
- AWS linked accounts status cannot be changed on individual linked accounts when opted for
  Automated Credentialing.

Note: If the Automated credentialing is not enabled.

- Both Consolidated account and Linked accounts can have different **ON/ OFF** status under
  Automate Actions.
- The **ON/ OFF** status can be changed individually without any dependency between
  Consolidated account and Linked accounts.

Note: When switching from **Automate Actions** to **Read only**, a pop-up notification
is displayed requiring confirmation.

![alert](../../../../03-media/cloudability-premium/images/alert.png)

Display of Turbonomic Permissions

As previously mentioned,
there are additional Turbonomic permissions that are added for basic (Billing Data), Advanced
(Utilization Data) and Automate Actions (to execute actions) which are documented in detail in the
IBM Turbonomic section of the help center documents. <INSERT LINK HERE PLEASE>. Once your IAM
permissions have been updated and all accounts have been verified; the list of permissions can be
viewed by choosing the **Details** option on each AWS account listed under
Cloudability.

![turbo](../../../../03-media/cloudability-premium/images/turbo.jpg)

It is worth
noting that per the above screenshot, Turbonomic monitoring can be selected to view READ permissions
put in place, while Turbonomic execution can be selected to view EXECUTE permissions in
place.

**Parent topic:** [Connecting with AWS - Customer Integration Guide](../admin/aws-credentialing-premium-home.html)
