---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "GCP Credentialing using Bulk Actions"
breadcrumb:
  - "Cloudability Premium"
  - "Getting data into Cloudability"
  - "Connect Google Cloud"
source_path: "admin/gcp-credentialing-bulk-actions.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# GCP Credentialing using Bulk Actions

**Overview**

Bulk Actions on Vendor Credentials screen allows admins to quickly
complete the advance credentialing process within Cloudability.

Currently this is available for
GCP projects where its possible to:

1. Save multiple non credentialed accounts quickly
2. Bulk verify multiple accounts to complete the credentialing process in an easier and faster
   way.

**Prerequisites**

**Save New Credentials**Please ensure you have opted into the
Automated credentialing of GCP projects for using the Organization ID for GCP while
credentialing **Verify Credentials**No prerequisites required, you’ll be able to verify
all accounts.

**Instructions**

Clicking on **Bulk Actions** will launch a screen
which has multiple tabs.

Note: The functionality on the individual tabs is independent of each
other.

**Save New Credentials**

This feature is applicable to the GCP accounts
where the prerequisites mentioned above are met.

1. This screen will not show up if there are no accounts configured using the GCP Organization
   ID

The screen displays all the accounts with Credentials Needed status(Red X). In order to Save
the credentials

1. Select the accounts which are needed to be credentialed.
2. Click on **Review Selection**.
3. Click on **Save.**

This would trigger the bulk save process and the bulk actions button would be disabled
until the process completes.

1. Once Save is completed, the accounts will move to Unverified status.
2. Please download the GCP template from one of the accounts which was saved and apply it to the
   GCP accounts in the GCP console.
3. Once completed, please trigger verify credentials for the accounts selected in the previous
   step.

**Verify Credentials**

This screen displays all the accounts except the
ones with Credentials Needed status (Red X).

Before triggering bulk verify, please ensure that
the template was downloaded and applied in the GCP console.

1. Select the accounts which are needed to be verified.
2. Click on “Review Selection”
3. Click on **Verify.**

This would trigger the bulk verify process and the bulk actions button would be disabled
until the process completes.

Once completed, the accounts will move to either a Verified
Credentialed status or Invalid Credential status (because of errors).

Note: The duration of Bulk
actions completion is dependent on the number of accounts.

**Parent topic:** [Connect Google Cloud](../admin/connect-google-cloud-premium.html)
