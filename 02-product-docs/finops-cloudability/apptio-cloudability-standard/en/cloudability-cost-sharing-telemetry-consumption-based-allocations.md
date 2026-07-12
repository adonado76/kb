---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Cost Sharing -Telemetry and Consumption Based Allocations"
breadcrumb:
  - "Setup"
  - "Sharing Cost in Cloudability"
  - "Cost Sharing -Telemetry and Consumption Based Allocations"
source_path: "SSVCLNQ/product/cost-sharing-telemetry.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Cost Sharing -Telemetry and Consumption Based Allocations

Overview

Telemetry Based Allocations enables you to distribute shared costs across your cloud environment using actual usage metrics from your systems. By uploading telemetry data, you can create more accurate and data-driven allocation rules within Cost Sharing.

Benefits

Using telemetry data for cost allocation provides several key advantages, as in:

- Usage-Based Cost Distribution : Allocate costs based on actual system usage rather than static percentages or estimated metrics
- Improved Cost Accuracy : Create a direct correlation between resource consumption and cost distribution
- Defensible Allocation Model : Support cost allocations with concrete usage data, making it easier to justify charge-back models
- Flexible Metric Support : Use any measurable metric (API calls, compute usage, storage operations) to drive allocation decisions

Before you begin

The file used for uploading your telemetry data should be a CSV file with the following required fields:

- Date: The time stamp for the metric measurement
- Category: Maps to your business dimension category
- Value: The metric measurement (e.g., number_of_api_requests, compute_hours)

The following example displays a CSV file format.

| Date | Category | Number of API requests |
| --- | --- | --- |
| 2025-01-01 | Team A | 15000 |
| 2025-01-01 | Team B | 8500 |
| 2025-01-01 | Team C | 12000 |

Using Telemetry in Cost Sharing

Follow the steps below to use Telemetry and consumption based allocations:

1. Select Organize/Cost Sharing in the left-hand navigation Pane
1. Select the New Allocation button
1. Select a Dimension in the New Allocation modal dialog and then select the Create button
1. Select the Telemetry Data tab
1. Select the Upload Telemetry File button and upload the CSV file
1. The CSV file will appear in the Telemetry table in the Telemetry Data tab
1. Select the Rules tab
1. Select the New Rule button
1. Select Telemetry / Consumption in the Allocation Method drop down
1. Select at least one option in the Source (from) list
1. The destination values appear disabled because the destination values are defined in the CSV that was uploaded
1. Save your Allocation Rule

The system will automatically compute allocation ratios based on your telemetry data and apply them to your shared costs.

Best Practices

Follow the best practices in Telemetry as below:

- Ensure your telemetry data covers the same time period as your cost allocation periods.
- Validate that your Category field values align with your existing business dimension categories.
- Regular updates to telemetry data will provide the most accurate cost distribution.
- Consider seasonality and usage patterns when selecting appropriate metrics for allocation.
