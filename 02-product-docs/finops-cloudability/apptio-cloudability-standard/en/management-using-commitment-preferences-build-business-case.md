---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Using Commitment Preferences to Build a Business Case"
breadcrumb:
  - "Optimize"
  - "Guide to Commitment Management"
  - "Using Commitment Preferences to Build a Business Case"
source_path: "SSVCLNQ/product/using_commitment_preferences_to_build_a_business_case.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Using Commitment Preferences to Build a Business Case

## Configuring Recommendation Usage Filters (GCP Support Only)

To setup your organization, go to Settings and select Commitment Preferences . Here you will be able to configure up to 10 Cloudability dimensions to apply to your usage. Select dimensions from your configured Tags & Labels, Business Mappings, or Account Groups.

For best performance, choose dimensions that provide a moderate level of variability – such as business units or application names. Dimensions that have a large amount of variability such as resource name will lead to significant performance degradation. If a configured dimension is not available – it is likely due to excessive variability.

Any changes to your preferences will be implemented in the next processing cycle, allow up to 24 hours for any changes to take effect, and be available in the CUD recommendations page.

Dimensions are regularly checked for variability and will be added/removed from the list of available dimensions. If a dimension becomes too variable it will be removed and no longer available in your data set.
