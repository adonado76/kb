---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Allocation Calculation Behavior"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Model Studio Reference"
  - "Allocations"
source_path: "studio/new-uc/reference/model-studio-reference/allocation-calc-behaviour.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Allocation Calculation Behavior

**Unallocated Costs**

When allocations based on matching criteria fail, costs remain unallocated in the source object.

**Common Causes of Unallocated Costs**

- Data relationship values don’t match between source and target
- Target table is empty or missing expected rows
- Weighting column sums to zero
- Filter conditions exclude all matching rows

**Tip:** Use the allocation preview panel to identify unallocated rows before saving changes.

**Negative Weighting Behavior**

By default, TBM Studio does not allocate when weighting values include negatives. This prevents
unexpected calculation results.

**Workarounds for Negative Values**

|  |  |
| --- | --- |
| **Approach** | **Description** |
| Formula allocation | Use =SOURCE\*({Table.Weight}/~{Table.Weight}) to enable negative weighting selectively |
| Segregate values | Separate positive and negative values in source, use absolute value for weighting |
| Fix source data | Remove negative values from weighting column at the source |

See Negative weighting issues for detailed troubleshooting

**Parent topic:** [Allocations](../../../../studio/new-uc/reference/model-studio-reference/allocations.html)
