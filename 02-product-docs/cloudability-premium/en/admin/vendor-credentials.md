---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "Vendor Credentials"
breadcrumb:
  - "Cloudability Premium"
  - "Administration"
source_path: "admin/vendor-credentials.html"
images:
  - "images/Vendor-Credentials-Details.png"
  - "images/vc1.jpg"
  - "images/vc2.jpg"
  - "images/vc3.jpg"
  - "images/vc5.jpg"
  - "images/vc6.jpg"
  - "images/vc_icon1.jpg"
  - "images/vc_icon2.jpg"
  - "images/vc_icon3.jpg"
  - "images/vc_icon4.jpg"
  - "images/vc_icon5.jpg"
  - "images/vc_icon6.jpg"
  - "images/vc_icon7.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Vendor Credentials

Overview:

Vendor Credentials page in Cloudability helps its Admin users view and connect to various data
sources available. This page also allows admins to view, update, or delete individual accounts under
data sources. Admins can search and filter the accounts, and also view the permission level on every
individual account.

Note: Cloudability shows the status of vendor credentials in multiple pages. In case you face any
issues, escalate to your organisation's Cloudability Administrator. If you are an administrator,
please reach out to your IBM CSM/TAM who can assist you in re-credentialing your accounts to ensure
Cloudability has necessary permissions.

Prerequisites

Admin access to the Cloudability Vendor Credentials

Getting Started

1. To add a new data source, click  Add Datasource  . This would show all
   the data sources available. ![VC add datasource screenshot](../../../../03-media/cloudability-premium/images/vc1.jpg)
2. Select a data source you would want to credential.

   Note: Some of the data sources would require
   a pre-setup. For instructions for your specific data source, find it in the list in the 
   Getting data into **Cloudability** section of the documentation.
3. Once credentialed, admins would be able to  view  a tab for individual
   datasource, for example AWS.![VC view added datasource screenshot](../../../../03-media/cloudability-premium/images/vc2.jpg)
4. Within the datasource tab, admins can  search  and  filter
    on individual columns.![VC search  datasource screenshot](../../../../03-media/cloudability-premium/images/vc3.jpg)
5. Export - Credentials Status for a datasource can also be exported in a csv format using the
   export option.
6. Click “…” to perform the following actions.
   - View Details – Displays the account's details along with its permissions

   ![](../../../../03-media/cloudability-premium/images/Vendor-Credentials-Details.png)

   - Edit Account – Enables to edit the existing credentials
   - Re-verify – Manually re-verifies the account's credentials and its permissions
   - Archive – Archives the account
   - Delete – Deletes the account
7. Accounts will be collapsed by default. However, there are icons which:
   - Expand all accounts![VC expand all accounts screenshot](../../../../03-media/cloudability-premium/images/vc5.jpg)
   - Collapse all accounts![VC collapse all accounts datasource screenshot](../../../../03-media/cloudability-premium/images/vc6.jpg)
8. The status of the accounts is displayed by various icons. The below table explains the icon and
   status mappings.

   | Cloudability Status | Turbonomic Status | Icon |
   | --- | --- | --- |
   | Verified Credential | Normal | verified credential icon  , verified credential 2 Icon |
   | Invalid Credential | Critical | invalid credential icon 2 , invalid credential icon |
   | Credential Needed | Unknown | not crdentialed Icon |
   | Incomplete Credentials | Major | incomplete icon |
   | Archived Credentials |  | archived icon |

**Re - Credentialing**

Cloudability frequently updates the services it supports across Cloud Service Providers for
either Optimization use cases like bringing more services under Rightsizing or Commitments or
enhancing an existing datasource connection. In order to get the full benefit of Cloudability
features, periodic re credentialing is recommended.

- **New Customers** - When New customers action on adding data sources , Cloudability provides
  the latest set of templates which involves the exhaustive permissions required to enable all the
  features based on Customer's Cloudability SKU.
- **Existing Customers** - Existing customers are required to **re-credential periodically**
  to continue getting the full value from Cloudability features and enhancements. In case of upgrading
  the Cloudability SKU e.g. **Upgrading to Cloudability Premium** , Customers **must
  re-credential** to get the full value of products supported in Cloudability Premium.

Note: Status of vendor credentials are displayed in the banner in vendor credentials page. In
Cloudability Premium deployments, it is shown in the Rightsizing -> Advanced page too. Make sure all
your vendor credentials have all the necessary permissions granted to ensure optimization
recommendations are generated right.

**Verification of permissions**

A bulk call is made by passing all relevant permission in the **AWS Simulate Policy Request**

- Example 1: Simulate Policy Allows All Permissions All permission are marked as verified
- Example 2: Simulate Policy Not Allowed.
  - We will take all the permission one by one and make a **dry run** call. Some APIs do not
    allow dry-run w/o a valid resource id. Hence we setup **dummy** resource id to test the calls.
  - No real resource of customer is utilised for this
    - Example : Simulate Policy Allows Partial Permissions - Let’s assume Cloudability tried to
      simulate 100 permission, simulation only allowed 70 permission. 70 permissions will considered as
      verified and we would make individual permission check for the remaining 30 permissions. Later, we
      would combine the results of both calls and mark all relevant permissions as verified.

Any permission/permissions which could not be verified by Simulate Policy or Dry-Run check would
be considered missing and UI will mark such permissions with a Red-Cross.

Frequently Asked Questions

- **Is the vendor credentials functionality same across all vendors**?
  - While the individual credentialing steps are different across different vendors, the process of
    filtering, expand, re verify etc is same across the various data sources supported by Cloudability.
- **What do the various status indicate for Cloudability?**
  - **Verified Credentials** - indicates that Cloudability has the minimum permissions on the
    account and Cloudability role or service principals were correctly installed.
  - **Invalid Credentials** - indicates sally some error in the account and Cloudability was
    unable to verify the account.
  - **Credential Needed** - indicates that this is new account and credentialing process is not
    started.
  - **Incomplete Credentials** - indicates that the accounts were saved but not verified. On
    verification these accounts would either move to the below based on the permission provided.
    - Verified Credentials
    - Invalid Credentials
  - **Archived Credentials** - indicates the account was archived
    - If this is a parent account, archiving an account would stop the cost data ingestion.
    - If this is a child account cost data ingestion would continue and archiving would only stop the
      data required for advance credentialing e.g. utilization/commitments data etc.
- **What do the various status indicate for Turbonomic?**
  - Mentioned above in the table.
- **The Cloudability account status and Turbonomic target status do not match in the Vendor
  Credentials screens? What could be the reasons?**

  - Existing Cloudability customers upgrading to Cloudability Premium need to re credential their
    accounts in order to get the latest Turbonomic permissions.

    Mismatch in Account status can be because of a few reasons:
    - Re-Credentialing was not done based on the latest templates/permissions.
    - If Re-Credentialing was done then possibly it was done using a previous template version and
      since then a few new permissions have been added for Cloudability Premium.
    - If Re-Credentialing does not help, please reach out to IBM support teams.
- **Where can I find the individual data sources documentation?**
  - Please refer to the **Getting data into Cloudability** section of the documentation.

- **[Vendor Credentials Email Alerts and Banners](../admin/email-alerts.html)**
- **[Manage vendor credentials in Cloudability](../admin/manage-vendor-credentials.html)**
