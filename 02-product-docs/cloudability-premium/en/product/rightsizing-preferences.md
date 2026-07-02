---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "Rightsizing Preferences"
breadcrumb:
  - "Cloudability Premium"
  - "Optimize"
  - "Rightsizing in Cloudability Premium"
  - "Rightsizing"
source_path: "product/rightsizing-preferences.html"
images:
  - "images/preferences-screenshot_S3.jpg"
  - "images/preferences-screenshot_VM.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Rightsizing Preferences

Navigate to Settings > Rightsizing Preferences.

Compute (VM) Preference

This preference tab allows you to set up global preferences for rightsizing recommendations.

![Compute VM preferences screenshot](../../../../03-media/cloudability-premium/images/preferences-screenshot_VM.jpg)

| Field Name | Description |
| --- | --- |
| Generations and Instances | Options for excluding non-current instance types or to recommend only within existing instance family (e.g. to ensure continued coverage with existing commitments / reservations) when generating rightsizing recommendations. |
| Processor Architecture | Choose to exclude specific processor types from rightsizing recommendations and allow cross -architecture recommendations. Ensure workload compatibility before switching the processor type. |
| Capacity Reduction | Options for including recommendations that would result in a reduction in resource capacity (e.g. reducing total available memory) if utilization metrics for the dimension are not provided. |
| Cost Saving Threshold | Optional setting for determining the minimum savings recommendations must be predicted to achieve in order to be included in those displayed.  Minimum 30-Day Savings Amount - A value of zero indicates the setting will be ignored. |
| Resource Lifespan | Optional setting for eliminating recommendations for the resources that have been inactive for a specified period of time. A value of zero indicates the setting will be ignored. |

Enter data in the appropriate fields and select the Save button. The message *Successfully saved preferences* appears.

Multiple ways to filter rightsizing recommendations

In Cloudability, there are many ways to filter rightsizing recommendations. First, you can filter the recommendations by using the global preferences available under Settings > Rightsizing Preferences page. Another way to filter using the options available on the rightsizing pages themselves under Optimize > Rightsizing. There are additional filtering options provided in the 'details' pane for the recommendations themselves.

Object Storage (S3) Preferences

This preference tab allows you to exclude specific classes for Object Storage for Rightsizing Recommendations.

To exclude a storage class:

1. select "Add Value" button.
2. Add a value (storage class) to the input field
3. Continue to add as may values to exclude as needed

S3 storage classes:

- Standard
- Intelligent Tiering
- Standard Infrequent Access
- Once Zone Infrequent Access
- Glacier Instant Retrieval
- Glacier Flexible Retrieval
- Glacier Deep Archive

![object storage preferences screenshot](../../../../03-media/cloudability-premium/images/preferences-screenshot_S3.jpg)

**Parent topic:** [Rightsizing](../product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)
