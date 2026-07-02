---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "Setting up Custom Pricing Support for GCP"
breadcrumb:
  - "Cloudability Premium"
  - "Getting data into Cloudability"
  - "Connect Google Cloud"
source_path: "product/gcp-rightsizing-custom-pricing-support.html"
images:
  - "images/gcp-standard-billing-1.jpg"
  - "images/gcp-standard-billing-2.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Setting up Custom Pricing Support for GCP

Custom pricing support is now extended to GCP for Cloudability so that contractual discounts and other customer specific pricing is applied to GCP
rightsizing recommendations and  **Workload Planning**  .

Follow the below steps to enable export of custom pricing data for GCP accounts.

1. Go to the GCP billing account.
2. Select  **Billing**  >  **Billing export**  .

   ![GCP standard billing screenshot](../../../../03-media/cloudability-premium/images/gcp-standard-billing-1.jpg)
3. Under  **Pricing**  , Click on “  **Enable Pricing Export**  ”.
4. Select  **Pricing > Edit Settings**  .
5. Based on your choice of  **GCP Billing**  (  **Standard Billing**  vs  **Detailed Billing** ), you need to ensure the following:
   - Select  **Project name**  and  **Dataset name**  same as  **Selected**  for “ **Standard Usage Cost**  ” if you are using  **Standard Billing**  .

   ![Notes Icon](../../../../03-media/cloudability-premium/images/gcp-standard-billing-2.jpg)

   - Select  **Project name**  and  **Dataset name**  same as  **Selected**  for “ **Detailed Usage Cost**  ” if you are using  **Detailed Billing**  .

**Parent topic:** [Connect Google Cloud](../admin/connect-google-cloud-premium.html)
