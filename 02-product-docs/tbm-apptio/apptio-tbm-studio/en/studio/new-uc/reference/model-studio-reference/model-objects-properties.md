---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Model Object Properties"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Model Studio Reference"
  - "Model Objects"
source_path: "studio/new-uc/reference/model-studio-reference/model-objects-properties.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Model Object Properties

Each model object has configurable properties that control its behavior in the model.

**Core Properties**

|  |  |  |  |
| --- | --- | --- | --- |
| **Property** | **Type** | **Description** | **Notes** |
| Name | String | Display name of the model object | Must be unique within project |
| Table | Reference | The underlying transform table | Table must have Model step |
| Identifier | Column(s) | Columns that uniquely identify rows | Similar to primary key |
| Description | String | Optional documentation | Displayed in model diagram |
| Metrics | Multi-select | Which metrics apply to this object | Cost, Budget, Forecast, etc. |

**Table Identifier Configuration**

The table identifier determines the granularity of the model object. By default, TBM Studio
creates an identifier that uniquely identifies each row. You can customize this for reporting and
allocation precision.

**Identifier Configuration Options**

|  |  |  |
| --- | --- | --- |
| **Option** | **Behavior** | **Use Case** |
| Default (Row-Level) | Each row is treated as unique | Maximum granularity for tracing and reporting |
| Single Column | Groups rows by one column value | Group by department, account, or category |
| Multiple Columns | Groups rows by combination of columns | Unique combination needed (e.g., Vendor + Account) |

Tip: Consider calculation times & performance when choosing granularity. Higher
granularity provides better detail but increases processing time.

**Example: Creating a Custom Identifier**

To group costs by department instead of individual transactions:

1. Click the Model step in the table transform pipeline
2. Click the table in the Single-Table view
3. In the Rows panel, check the Department column
4. Save changes – costs are now grouped by department

Warning: Changing the identifier on an existing model object affects all allocations
that reference it. Review downstream allocations before making changes.

*→ See [Configure table identifiers for detailed procedure](../../howtoguides/build-cost-model/create-allocation.html)*

**Parent topic:** [Model Objects](../../../../studio/new-uc/reference/model-studio-reference/model-objects.html)
