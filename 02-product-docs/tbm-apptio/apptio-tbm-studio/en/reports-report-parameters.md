---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Report Parameters"
breadcrumb:
  - "Reference"
  - "Model Studio Reference"
  - "Model Reports"
  - "Report Parameters"
source_path: "SSWRJM/studio/new-uc/reference/model-studio-reference/report-parameters.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Report Parameters

Configuration Options

| Parameter | Description |
| --- | --- |
| Parameter | Description |
| Report Name | Display name for the report (visible in Project Explorer) |
| Description | Optional documentation about the report purpose |
| Selected Metrics | Which metrics to calculate and display (affects performance) |
| Tier Structure | Number, order, and content of tiers |
| Report Collection | Optional assignment to a collection for easy access (v12.2.2+) |

Performance Optimization

Limit selected metrics to improve calculation speed in Staging and Production environments.

To Limit Metrics

1. Open the report and check it out
1. Click View > Show Document > Edit Metrics
1. Select only the metrics you need
1. Click OK and save
1. Check in the report

Tip: Selecting fewer metrics significantly reduces calculation time, especially for large models.

Assigning to Report Collection

1. Open the model report
1. Click the Modeling tab
1. Click Assign to Collection

1. Select the report collection from the dropdown
1. Save the report

→ See Section 3.3.5: Organize reports in collections for collection management

→ See Section 5.3: Report Studio Reference for general reporting features
