---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Report Parameters"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Model Studio Reference"
  - "Model Reports"
source_path: "studio/new-uc/reference/model-studio-reference/report-parameters.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Report Parameters

**Configuration Options**

|  |  |
| --- | --- |
| **Parameter** | **Description** |
| Report Name | Display name for the report (visible in Project Explorer) |
| Description | Optional documentation about the report purpose |
| Selected Metrics | Which metrics to calculate and display (affects performance) |
| Tier Structure | Number, order, and content of tiers |
| Report Collection | Optional assignment to a collection for easy access (v12.2.2+) |

**Performance Optimization**

Limit selected metrics to improve calculation speed in Staging and Production environments.

**To Limit Metrics**

1. Open the report and check it out
2. Click View > Show Document > Edit Metrics
3. Select only the metrics you need
4. Click OK and save
5. Check in the report

**Tip:** Selecting fewer metrics significantly reduces calculation time, especially for large
models.

**Assigning to Report Collection**

1. Open the model report
2. Click the Modeling tab
3. Click Assign to Collection

1. Select the report collection from the dropdown
2. Save the report

*→ See Section 3.3.5: Organize reports in collections for collection management*

*→ See Section 5.3: [Report Studio Reference for general reporting features](../report-studio-reference/report-studio-reference.html)*

**Parent topic:** [Model Reports](../../../../studio/new-uc/reference/model-studio-reference/model-reports.html)
