---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "Manage vendor credentials in Cloudability"
breadcrumb:
  - "Cloudability Premium"
  - "Administration"
  - "Vendor Credentials"
source_path: "admin/manage-vendor-credentials.html"
images:
  - "images/archivecredential.png"
  - "images/deleting__a_credential_19_34_am_png.jpg"
  - "images/regenerate_cloudability_more_options.jpg"
  - "images/reverify-cloudability-icon.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Manage vendor credentials in Cloudability

Overview

This page provides information on how to manage vendor credentials within Cloudability.

Prerequisites 

- Admin access to the Cloudability Vendor Credentials
- Vendor accounts should be credentialed in Cloudability

**Getting Started**

In order to manage credentials , click on the … on the right side of the account and click one
of the options:

- Re-verify credentials
- Archive credentials
- Delete credentials

Re-verify a credential

Re-verifying credentials implies checking vendor connections to ensure all permissions are
available and updated with changes. If you have accidentally deleted or archived your account, be
rest assured your data will be preserved, once you Re-verify your credential.

**To manually re-verify your credential:**

1. From the main menu, navigate to Settings > Vendor Credentials .

   Note: Vendor Credentials page requires admin permissions to access.
2. Find the account you want to re-verify.
3. Hover your cursor over the ![Notes Icon](../../../../03-media/cloudability-premium/images/regenerate_cloudability_more_options.jpg) icon.
4. Click the Re-Verify
   ![reverify credential icon](../../../../03-media/cloudability-premium/images/reverify-cloudability-icon.png) icon in the drop-down list.

   This starts the validation and
   displays a check mark upon success.

**To bulk re-verify your credential:**

Click on **Bulk Actions** after the vendor is selected. This will launch a screen which has
multiple tabs.

Click on **Verify Credentials** tab.

Note: This is available for AWS and GCP.

This screen displays all the accounts except the ones with Credentials Needed status
(X).

In order to Verify the credentials

1. Select the accounts which are needed to be verified.
2. Click on **Review Selection**
3. Click on **Verify.**

This would trigger the bulk verify process and the bulk actions button would be disabled
until the process completes.

Once completed, the accounts will move to either a Verified
Credentialed status or Invalid Credential status (because of errors).

Note: In case the number of
accounts is huge this might take a few minutes.

Archive a credential

Archiving a credential deletes the vendor link keeping the historical data untouched. This is
used for decommissioned accounts.

1. From the main menu, navigate to Settings > Vendor Credentials.
2. Click Vendor Credentials.
3. Find the account you want to archive.
4. Hover your cursor over the ![Notes Icon](../../../../03-media/cloudability-premium/images/regenerate_cloudability_more_options.jpg) icon.
5. Click the Archive
   ![archive credential icon](../../../../03-media/cloudability-premium/images/archivecredential.png) icon and select
   **Confirm** when prompted.

   Note: Once archived, the account cannot be retrieved.

Delete a credential

To delete a credential:

1. From the main menu, navigate to Settings > Vendor Credentials.
2. Find the account you want to delete.
3. Hover your cursor over the ![Notes Icon](../../../../03-media/cloudability-premium/images/regenerate_cloudability_more_options.jpg) icon.
4. Select the Delete
   ![delete credential icon](../../../../03-media/cloudability-premium/images/deleting__a_credential_19_34_am_png.jpg) icon and click Confirm when prompted.

Your account is deleted.

Note: Deleting a payer account removes all the linked or child accounts.

Deleting a linked or a
child account only removes the selected account.

Frequently Asked Questions

- **Does Archiving an account deletes the data from Cloudability?**
  - No, Archiving an account does not delete the data from Cloudability
- **Does Deleting an account**
  **deletes the data from Cloudability?**
  - No, deleting an account does not delete the data from Cloudability
- **Can I restore an Archived account?**
  - No, you'll need to re credential the account.
- **Can I archive a non credentialed account?**
  - Yes, you can directly archive an account which is not credentialed.
- **I archived a child account (AWS Linked/Azure Subscription/GCP Project etc), will I still get
  the cost data for it?**
  - Yes Cost data will be pulled as cost data is tied to the parent account. Archiving or Deleting
    the child account would only stop the data required for advance credentialing e.g.
    utilization/commitments data etc.
- **How should I download updated template with latest permissions if there has been update of
  permissions?**

  - Updated Template can be downloaded by editing the existing billing account and downloading the
    latest template for it. Once downloaded follow the credentialing steps mentioned after download of
    template.
- **What do the different Icons indicate on Cloudability UI?**
  - Please refer [Vendor Credentials](vendor-credentials.html)
    page

**Parent topic:** [Vendor Credentials](../admin/vendor-credentials.html)
