---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "GCP Credentialing using Bulk Actions"
breadcrumb:
  - "Getting data into Cloudability"
  - "Connect Google Cloud"
  - "GCP Credentialing using Bulk Actions"
source_path: "SSVCLNQ/admin/gcp-credentialing-bulk-actions.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# GCP Credentialing using Bulk Actions

Overview

Bulk Actions on Vendor Credentials screen allows admins to quickly complete the advance credentialing process within Cloudability.

1. Save multiple non credentialed accounts quickly
1. Bulk verify multiple accounts to complete the credentialing process in an easier and faster way.

Prerequisites

Instructions

Save New Credentials

1. This screen will not show up if there are no accounts configured using the GCP Organization ID

1. Select the accounts which are needed to be credentialed.
1. Click on Review Selection .
1. Click on Save.

1. Once Save is completed, the accounts will move to Unverified status.
1. Please download the GCP template from one of the accounts which was saved and apply it to the GCP accounts in the GCP console.
1. Once completed, please trigger verify credentials for the accounts selected in the previous step.

Verify Credentials

This screen displays all the accounts except the ones with Credentials Needed status (Red X).

1. Select the accounts which are needed to be verified.
1. Click on “Review Selection”
1. Click on Verify.

This would trigger the bulk verify process and the bulk actions button would be disabled until the process completes.
