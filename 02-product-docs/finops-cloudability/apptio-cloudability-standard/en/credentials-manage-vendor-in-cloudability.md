---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Manage vendor credentials in Cloudability"
breadcrumb:
  - "Administration"
  - "Vendor Credentials"
  - "Manage vendor credentials in Cloudability"
source_path: "SSVCLNQ/admin/manage-vendor-credentials.html"
images:
  - "03-media/apptio-cloudability-standard/regenerate_cloudability_more_options.jpg"
  - "03-media/apptio-cloudability-standard/reverify-cloudability-icon.png"
  - "03-media/apptio-cloudability-standard/archivecredential.png"
  - "03-media/apptio-cloudability-standard/deleting__a_credential_19_34_am_png.jpg"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Manage vendor credentials in Cloudability

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
