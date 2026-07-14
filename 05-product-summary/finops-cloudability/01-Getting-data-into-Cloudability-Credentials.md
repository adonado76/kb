---
source_system: "apptio-cloudability-standard"
practice: "finops"
language: "en"
doc_type: "cloudability-standard"
consolidated_file: "01-Getting-data-into-Cloudability-Credentials"
source_files_count: 3
last_updated: "2026-07-13"
---

# 01-Getting-data-into-Cloudability-Credentials

## Vendor Credentials

<!-- sub-header -->
- **breadcrumb:** Administration > Vendor Credentials
- **source_path:** SSVCLNQ/admin/vendor-credentials.html
- **original_file:** administration-vendor-credentials.md
- **images:**
  - 03-media/apptio-cloudability-standard/vc1.jpg
  - 03-media/apptio-cloudability-standard/vc2.jpg
  - 03-media/apptio-cloudability-standard/vc3.jpg
  - 03-media/apptio-cloudability-standard/Vendor-Credentials-Details.png
  - 03-media/apptio-cloudability-standard/vc5.jpg
  - 03-media/apptio-cloudability-standard/vc6.jpg
  - 03-media/apptio-cloudability-standard/vc_icon1.jpg
  - 03-media/apptio-cloudability-standard/vc_icon2.jpg
  - 03-media/apptio-cloudability-standard/vc_icon3.jpg
  - 03-media/apptio-cloudability-standard/vc_icon4.jpg
  - 03-media/apptio-cloudability-standard/vc_icon5.jpg
  - 03-media/apptio-cloudability-standard/vc_icon6.jpg
  - 03-media/apptio-cloudability-standard/vc_icon7.jpg

## Vendor Credentials

Overview:

Vendor Credentials page in Cloudability helps its Admin users view and connect to various data sources available. This page also allows admins to view, update, or delete individual accounts under data sources. Admins can search and filter the accounts, and also view the permission level on every individual account.

Prerequisites

Admin access to the Cloudability Vendor Credentials

Getting Started

1. To add a new data source, click Add Datasource . This would show all the data sources available.
1. Select a data source you would want to credential. Note: Some of the data sources would require a pre-setup. For instructions for your specific data source, find it in the list in the Getting data into Cloudability section of the documentation.
1. Once credentialed, admins would be able to view a tab for individual datasource, for example AWS.
1. Within the datasource tab, admins can search and filter on individual columns.
1. Export - Credentials Status for a datasource can also be exported in a csv format using the export option.
1. Click “…” to perform the following actions. View Details – Displays the account's details along with its permissions Edit Account – Enables to edit the existing credentials Re-verify – Manually re-verifies the account's credentials and its permissions Archive – Archives the account Delete – Deletes the account
1. Accounts will be collapsed by default. However, there are icons which: Expand all accounts Collapse all accounts
1. The status of the accounts is displayed by various icons. The below table explains the icon and status mappings. Cloudability Status Turbonomic Status Icon Verified Credential Normal , Invalid Credential Critical , Credential Needed Unknown Incomplete Credentials Major Archived Credentials

Re - Credentialing

Cloudability frequently updates the services it supports across Cloud Service Providers for either Optimization use cases like bringing more services under Rightsizing or Commitments or enhancing an existing datasource connection. In order to get the full benefit of Cloudability features, periodic re credentialing is recommended.

- New Customers - When New customers action on adding data sources , Cloudability provides the latest set of templates which involves the exhaustive permissions required to enable all the features based on Customer's Cloudability SKU.
- Existing Customers - Existing customers are required to re-credential periodically to continue getting the full value from Cloudability features and enhancements. In case of upgrading the Cloudability SKU e.g. Upgrading to Cloudability Premium , Customers must re-credential to get the full value of products supported in Cloudability Premium.

Verification of permissions

A bulk call is made by passing all relevant permission in the AWS Simulate Policy Request

- Example 1: Simulate Policy Allows All Permissions All permission are marked as verified
- Example 2: Simulate Policy Not Allowed. We will take all the permission one by one and make a dry run call. Some APIs do not allow dry-run w/o a valid resource id. Hence we setup dummy resource id to test the calls. No real resource of customer is utilised for this Example : Simulate Policy Allows Partial Permissions - Let’s assume Cloudability tried to simulate 100 permission, simulation only allowed 70 permission. 70 permissions will considered as verified and we would make individual permission check for the remaining 30 permissions. Later, we would combine the results of both calls and mark all relevant permissions as verified.

Any permission/permissions which could not be verified by Simulate Policy or Dry-Run check would be considered missing and UI will mark such permissions with a Red-Cross.

Frequently Asked Questions

- Is the vendor credentials functionality same across all vendors ? While the individual credentialing steps are different across different vendors, the process of filtering, expand, re verify etc is same across the various data sources supported by Cloudability.
- What do the various status indicate for Cloudability? Verified Credentials - indicates that Cloudability has the minimum permissions on the account and Cloudability role or service principals were correctly installed. Invalid Credentials - indicates sally some error in the account and Cloudability was unable to verify the account. Credential Needed - indicates that this is new account and credentialing process is not started. Incomplete Credentials - indicates that the accounts were saved but not verified. On verification these accounts would either move to the below based on the permission provided. Verified Credentials Invalid Credentials Archived Credentials - indicates the account was archived If this is a parent account, archiving an account would stop the cost data ingestion. If this is a child account cost data ingestion would continue and archiving would only stop the data required for advance credentialing e.g. utilization/commitments data etc.
- What do the various status indicate for Turbonomic? Mentioned above in the table.
- The Cloudability account status and Turbonomic target status do not match in the Vendor Credentials screens? What could be the reasons? Existing Cloudability customers upgrading to Cloudability Premium need to re credential their accounts in order to get the latest Turbonomic permissions. Mismatch in Account status can be because of a few reasons: Re-Credentialing was not done based on the latest templates/permissions. If Re-Credentialing was done then possibly it was done using a previous template version and since then a few new permissions have been added for Cloudability Premium. If Re-Credentialing does not help, please reach out to IBM support teams.
- Where can I find the individual data sources documentation? Please refer to the Getting data into Cloudability section of the documentation.

---

## Manage vendor credentials in Cloudability

<!-- sub-header -->
- **breadcrumb:** Administration > Vendor Credentials > Manage vendor credentials in Cloudability
- **source_path:** SSVCLNQ/admin/manage-vendor-credentials.html
- **original_file:** credentials-manage-vendor-in-cloudability.md
- **images:**
  - 03-media/apptio-cloudability-standard/regenerate_cloudability_more_options.jpg
  - 03-media/apptio-cloudability-standard/reverify-cloudability-icon.png
  - 03-media/apptio-cloudability-standard/archivecredential.png
  - 03-media/apptio-cloudability-standard/deleting__a_credential_19_34_am_png.jpg

## Manage vendor credentials in Cloudability

Overview

This page provides information on how to manage vendor credentials within Cloudability.

- Admin access to the Cloudability Vendor Credentials
- Vendor accounts should be credentialed in Cloudability

Getting Started

In order to manage credentials , click on the … on the right side of the account and click one of the options:

- Re-verify credentials
- Archive credentials
- Delete credentials

Re-verify a credential

Re-verifying credentials implies checking vendor connections to ensure all permissions are available and updated with changes. If you have accidentally deleted or archived your account, be rest assured your data will be preserved, once you Re-verify your credential.

To manually re-verify your credential:

1. From the main menu, navigate to Settings > Vendor Credentials . Note: Vendor Credentials page requires admin permissions to access.
1. Find the account you want to re-verify.
1. Hover your cursor over the icon.
1. Click the Re-Verify icon in the drop-down list. This starts the validation and displays a check mark upon success.

To bulk re-verify your credential:

Click on Bulk Actions after the vendor is selected. This will launch a screen which has multiple tabs.

Click on Verify Credentials tab.

This screen displays all the accounts except the ones with Credentials Needed status (X).

1. Select the accounts which are needed to be verified.
1. Click on Review Selection
1. Click on Verify.

This would trigger the bulk verify process and the bulk actions button would be disabled until the process completes.

Archive a credential

1. From the main menu, navigate to Settings > Vendor Credentials .
1. Click Vendor Credentials .
1. Find the account you want to archive.
1. Hover your cursor over the icon.
1. Click the Archive icon and select Confirm when prompted. Note: Once archived, the account cannot be retrieved.

Delete a credential

1. From the main menu, navigate to Settings > Vendor Credentials .
1. Find the account you want to delete.
1. Hover your cursor over the icon.
1. Select the Delete icon and click Confirm when prompted.

Your account is deleted.

Deleting a linked or a child account only removes the selected account.

Frequently Asked Questions

- Does Archiving an account deletes the data from Cloudability? No, Archiving an account does not delete the data from Cloudability
- Does Deleting an account deletes the data from Cloudability? No, deleting an account does not delete the data from Cloudability
- Can I restore an Archived account? No, you'll need to re credential the account.
- Can I archive a non credentialed account? Yes, you can directly archive an account which is not credentialed.
- I archived a child account (AWS Linked/Azure Subscription/GCP Project etc), will I still get the cost data for it? Yes Cost data will be pulled as cost data is tied to the parent account. Archiving or Deleting the child account would only stop the data required for advance credentialing e.g. utilization/commitments data etc.
- How should I download updated template with latest permissions if there has been update of permissions? Updated Template can be downloaded by editing the existing billing account and downloading the latest template for it. Once downloaded follow the credentialing steps mentioned after download of template.
- What do the different Icons indicate on Cloudability UI? Please refer Vendor Credentials page

---

## Vendor Credentials Email Alerts and Banners

<!-- sub-header -->
- **breadcrumb:** Administration > Vendor Credentials > Vendor Credentials Email Alerts and Banners
- **source_path:** SSVCLNQ/admin/email-alerts.html
- **original_file:** credentials-vendor-email-alerts-banners.md
- **images:**
  - 03-media/apptio-cloudability-standard/email_alerts1.png
  - 03-media/apptio-cloudability-standard/email_alerts.png
  - 03-media/apptio-cloudability-standard/email_alerts2.png
  - 03-media/apptio-cloudability-standard/SampleVCemail.jpeg
  - 03-media/apptio-cloudability-standard/SampleVCemailPremium.png
  - 03-media/apptio-cloudability-standard/CLDYBanner.jpeg
  - 03-media/apptio-cloudability-standard/PremiumBanner.jpeg
  - 03-media/apptio-cloudability-standard/Rightsizng_vendorcreds_banner.png

## Vendor Credentials Email Alerts and Banners

Cloudability supports enabling email alerts on the Vendor Credentials page. These email alerts will trigger an email with the summary of the account status.

Admins can opt in to these alerts using the Email Alerts button.

![Email Alerts](../images/email_alerts1.png)

Click Email Alerts to open Email Alerts window. Set these alerts based on your preferred cadence.

![Email alerts](../images/email_alerts.png)

These email alerts get triggered based on your time zone preference. To learn more, see Setting up Time Zone Preferences .

You can unsubscribe these alerts using the Edit Alert window.

![Email alerts](../images/email_alerts2.png)

Sample Email for Cloudability Customers (except Premium)

Sample Email for Cloudability Premium Customers

Banners on Vendor Credentials

Banners will be shown on the data sources which are credentialed in Cloudability.

These banners, which act as quick filters, highlight the number of invalid and incomplete accounts where action is needed.

Banners for Cloudability Customers (except Premium)

Banners for Cloudability Premium Customers

Banners for Cloudability Premium - Rightsizing

---
