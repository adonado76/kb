---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Setting up Commitment Portfolio for GCP"
breadcrumb:
  - "Getting data into Cloudability"
  - "Connect Google Cloud"
  - "Setting up Commitment Portfolio for GCP"
source_path: "SSVCLNQ/admin/commitment-portfolio-gcp.html"
images:
  - "03-media/apptio-cloudability-standard/commitment-portfolio-3.jpg"
  - "03-media/apptio-cloudability-standard/vc_ss6.jpg"
  - "03-media/apptio-cloudability-standard/vc_ss7.jpg"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Setting up Commitment Portfolio for GCP

The Commitment Portfolio for GCP Spend-based commitments requires two additional permissions to populate beyond basic credentialing.

Before you start

You need to credential your account before following the steps to set up Commitment Portfolio. See Connect Google Cloud to credential your account.

Additional Permissions for Commitment Portfolio

Follow the below steps to set up credentials for additional permissions as mentioned above.

1. Sign into Cloudability , and then navigate to Settings > Vendor Credentials > GCP .
1. Find a Billing Account which has purchased GCP spend-based CUDs.
1. Hover over the ellipsis menu icon, and then click to select Edit a Credential .
1. Add your Organization ID.
1. Click Update Credential .

For more information on organizational resources, see Creating and managing organization resources .

Once the adjustment to credentialing is complete, the following new permissions are displayed under Master-Payer billing account Reservation section:

- consumerprocurement.orders.list

- consumerprocurement.orders.get

As part of the credentialing process, the next step is to create a new role under GCP organization scope. Apply this at the Billing Account scope along with the existing role at the Project scope with the BQ Table permissions for successful credentialing.
