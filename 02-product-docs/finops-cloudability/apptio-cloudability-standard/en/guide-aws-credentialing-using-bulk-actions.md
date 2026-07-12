---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "AWS Credentialing using Bulk Actions"
breadcrumb:
  - "Getting data into Cloudability"
  - "Connecting with AWS - Customer Integration Guide"
  - "AWS Credentialing using Bulk Actions"
source_path: "SSVCLNQ/admin/aws-credentialing-bulk-actions.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# AWS Credentialing using Bulk Actions

Bulk Actions on Vendor Credentials screen allows admins to quickly complete the advance credentialing process within Cloudability.

1. Save multiple non credentialed accounts quickly
1. Update multiple accounts
1. Bulk verify multiple accounts to complete the credentialing process in an easier and faster way.

Prerequisites

Instructions

Save New Credentials

1. This screen will not show up if there are no accounts configured using Automated credentialing of linked accounts.

1. Select the accounts which are needed to be credentialed.
1. Click on Review Selection Add SCP region as required for AWS.
1. Click on Save.

1. Once save is complete, the accounts will move to Unverified status.
1. Please download the Cloud Formation template from one of the accounts which was saved and apply it to the AWS accounts in the AWS console as a stackset.
1. Once completed, please trigger verify account(s) for the accounts selected in the previous step.

Update Credentials

1. Select the accounts which are needed to be updated.
1. Click on “Review Selection” Add SCP region as required for AWS.
1. Click on Save.

This would trigger the bulk update process and the bulk actions button would be disabled until the process completes.

Once completed, please trigger Verify Credentials.

Verify Credentials

This screen displays all the accounts except the ones with Credentials Needed status (X).

1. Select the accounts which are needed to be verified.
1. Click on Review Selection
1. Click on Verify.

This would trigger the bulk verify process and the bulk actions button would be disabled until the process completes.
