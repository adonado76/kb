---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "AWS Credentialing using Bulk Actions"
breadcrumb:
  - "Cloudability Premium"
  - "Getting data into Cloudability"
  - "Connecting with AWS - Customer Integration Guide"
source_path: "admin/aws-credentialing-bulk-actions.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# AWS Credentialing using Bulk Actions

**Overview**

Bulk Actions on Vendor Credentials screen allows admins to quickly complete
the advance credentialing process within Cloudability.

Currently this is available for AWS
Linked accounts where its possible to:

1. Save multiple non credentialed accounts quickly
2. Update multiple accounts
3. Bulk verify multiple accounts to complete the credentialing process in an easier and faster
   way.

**Prerequisites**

**Save New Credentials:**Please ensure you have opted into
the Automated credentialing of linked accounts for AWS while credentialing**.****Verify
Credentials:**No prerequisites is required, and you’ll be able to verify all
accounts.

**Instructions**

Clicking on **Bulk Actions** will launch a screen which has
multiple tabs.

Note: The functionality on the individual tabs is independent of each
other.

**Save New Credentials**

This feature is applicable to AWS accounts if
the prerequisites mentioned above are met.

1. This screen will not show up if there are no accounts configured using Automated credentialing
   of linked accounts.

The screen displays all the accounts with Credentials Needed status (Red X). In order to Save
the credentials

1. Select the accounts which are needed to be credentialed.
2. Click on **Review Selection**
   1. Add SCP region as required for AWS.
3. Click on **Save.**

This would trigger the bulk save process and the bulk actions button would be disabled
until the process completes.

1. Once save is complete, the accounts will move to Unverified status.
2. Please download the Cloud Formation template from one of the accounts which was saved and apply
   it to the AWS accounts in the AWS console as a stackset.
3. Once completed, please trigger verify account(s) for the accounts selected in the previous step.

**Update Credentials**

The screen displays all the accounts except the ones
with Credentials Needed status (X). In order to Update the credentials

1. Select the accounts which are needed to be updated.
2. Click on “Review Selection”
   1. Add SCP region as required for AWS.
3. Click on **Save.**

This would trigger the bulk update process and the bulk actions button would be disabled
until the process completes.

Once completed, please trigger Verify Credentials.

**Verify Credentials**

This screen displays all the accounts except the ones with
Credentials Needed status (X).

Before triggering bulk verify, please ensure that the template
was downloaded and applied to AWS console for the AWS linked accounts. In order to Verify the credentials

1. Select the accounts which are needed to be verified.
2. Click on **Review Selection**
3. Click on **Verify.**

This would trigger the bulk verify process and the bulk actions button would be disabled
until the process completes.

Once completed, the accounts will move to either a Verified
Credentialed status or Invalid Credential status (because of errors).

Note: In case the number of
accounts is huge this might take a few minutes.

**Parent topic:** [Connecting with AWS - Customer Integration Guide](../admin/aws-credentialing-premium-home.html)
