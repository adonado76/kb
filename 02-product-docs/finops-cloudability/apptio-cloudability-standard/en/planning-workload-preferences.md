---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Workload Planning Preferences"
breadcrumb:
  - "Plan"
  - "Workload Planning"
  - "Workload Planning Preferences"
source_path: "SSVCLNQ/product/workload-planning-preferences.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Workload Planning Preferences

Workload Planning Preferences allow FinOps teams to centrally define, and restrict options in Workload Planning . Any update is optional, and not required to use Workload Planning .

By default, these preferences are only visible to Workload Planning Admin, who can modify them. “WorkloadPlanningPreferencesViewOnly” permission can be assigned to a custom role to allow non-admin users to view Workload Planning Preferences without editing rights.

1. Navigate to Settings > Work . Planning Preferences .
1. For each service provider, adjust parameters based on your organization preferences and policies, and click Save . Any change will take effect immediately.

Preference Details

| Field | Description |
| --- | --- |
| Allow Service Provider | It restricts the visibility of a specific service provider when users create a workload. If an existing workload leverages a service provider that has been disabled by admins, then it will be locked, and users won’t be able to edit it. |
| Preferred Lease Type | For AWS, Azure, and GCP, admins can decide to display “Committed Pricing” and “Spot Pricing” in Cloudability Workload Planning . "Committed Pricing" refers to the price associated with potential Savings Plans, Reservations, or Commitments, depending on the service provider’s offering, and user selection. For OCI, users can decide to display “Capacity Reservation Pricing”, which provides an additional 15% discount compared to On-Demand and is forfeited upon utilization. They can also decide to display “Spot Pricing”. |
| Commitment Default Options | These preferences will impact AWS, Azure and GCP “Committed Pricing”, when displayed in Cloudability Workload Planning . Admins have the authority to disable the option selection in the UI. |
| Discount /Uplift | For each service provider, admins can add an additional Discount or Uplift %. This percentage will be applied across all prices calculated by Cloudability Workload Planning for a given provider. It doesn’t apply to “Other” costs added to a workload. Any change would apply to the existing and new workloads. |
| Exclude recommendations where the recommended instance type contains the following values. | Using this option, you can specify those resource types that should not appear in the Workload Planning recommendations for your org. This can be done using either of these 2 options: by adding the keyword so that the recommendations would skip those resource types that contain the keyword. Eg: giving the value "xlarge" would exclude all those resources that has "xlarge" in their names. by adding asterix (*) along with the keyword so that the recommendations would skip those resource types that starts with that keyword. Eg: giving the value "t4*" would exclude all those resources that starts with "t4". |
