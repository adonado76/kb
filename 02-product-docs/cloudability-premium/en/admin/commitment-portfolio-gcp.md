---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "Setting up Commitment Portfolio for GCP"
breadcrumb:
  - "Cloudability Premium"
  - "Getting data into Cloudability"
  - "Connect Google Cloud"
source_path: "admin/commitment-portfolio-gcp.html"
images:
  - "images/commitment-portfolio-3.jpg"
  - "images/vc_ss6.jpg"
  - "images/vc_ss7.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Setting up Commitment Portfolio for GCP

The Commitment Portfolio for GCP Spend-based commitments requires two additional permissions to
populate beyond basic credentialing.

Before you start

You need to credential your account before following the steps to set up Commitment Portfolio.
See  [Connect Google Cloud](connect-google-cloud.html)  to credential your account.

Additional Permissions for Commitment Portfolio

Follow the below steps to set up credentials for additional permissions as mentioned above.

1. Sign into Cloudability , and then navigate to  Settings
    >  Vendor Credentials  >  GCP  .
2. Find a Billing Account which has purchased GCP spend-based CUDs.
3. Hover over the ellipsis menu icon, and then click ![edit icon](../../../../03-media/cloudability-premium/images/commitment-portfolio-3.jpg) to
   select  Edit a Credential  .

   ![edit credential screenshot](../../../../03-media/cloudability-premium/images/vc_ss6.jpg)
4. Add your Organization ID.
5. Click  Update Credential  .

For more information on organizational resources, see  [Creating and managing organization resources](https://cloud.google.com/resource-manager/docs/creating-managing-organization "(Opens in a new tab or window)")  .

Once the adjustment to credentialing is complete, the following new permissions are displayed
under Master-Payer billing account Reservation section:

- consumerprocurement.orders.list

- consumerprocurement.orders.get

As part of the credentialing process, the next step is to create a new role under GCP
organization scope. Apply this at the Billing Account scope along with the existing role at the
Project scope with the BQ Table permissions for successful credentialing.

![credential details screenshot](../../../../03-media/cloudability-premium/images/vc_ss7.jpg)

**Parent topic:** [Connect Google Cloud](../admin/connect-google-cloud-premium.html)
