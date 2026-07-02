---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Event types"
breadcrumb: []
source_path: "planning/event-types.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Event types

The [Change history](change-history.htm "(Opens in a new tab or window)") tracks
the following Event types.

The Area, Container, Item Type, and Item are displayed as columns in the Event Log. If the Event
causes an attribute to change, the Attribute, with Before value and After value are displayed in the
Properties pane under the Details tab.

## Line Item Events

| Event type | Area | Container | Item Type | Item | Attribute | Before | After |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Add Line Item | Plan | Plan Name | Labor Line Item, Asset Line Item, Other Line Item, etc. | Line Item Code | All attributes of the line item | (blank) | Attribute values |
| Update Line Item | Plan | Plan Name | Labor Line Item, Asset Line Item, Other Line Item, etc. | Line Item Code | Dimension or Metric updated | Old value | New value |
| Delete Line Item | Plan | Plan Name | Labor Line Item, Asset Line Item, Other Line Item, etc. | Line Item Code | (blank) | (blank) | (blank) |
| Import Line Items | Plan | Plan Name | Labor Line Item, Asset Line Item, Other Line Item, etc. | (blank) | (blank) | (blank) | (blank) |
| Export Line Items | Plan | Plan Name | Labor Line Item, Asset Line Item, Other Line Item, etc. | (blank) | (blank) | (blank) | (blank) |
| Import Actuals | Spend Management | Plan Name | (blank) | (blank) | (blank) | (blank) | (blank) |
| Export Actuals | Spend Management | Plan Name | (blank) | (blank) | (blank) | (blank) | (blank) |
| Import Actuals | Costing Standard Integration | Actuals | (blank) | (blank) | 1. CT Dataset 2. End Period 3. Instance 4. Job Number 5. Project Domain 6. Project Name 7. Rows Added 8. Rows Committed 9. Rows Modified 10. Rows Omitted 11. Start Period 12. Status | (blank) | 1. Dataset Name 2. Month (for example, March FY2020) 3. CT Instance name 4. CT Job Number 5. CT Project Domain Name 6. CT Project Name 7. count (for example, 0) 8. count (for example, 310) 9. count (for example, 0) 10. count (for example, 0) 11. Start month (for example, December FY2019) 12. Success/Failure |
| Import Reference Data | Costing Standard Integration | <Dimension Name> (for example, Department) | (blank) | (blank) | 1. CT Dataset 2. End Period 3. Instance 4. Job Number 5. Project Domain 6. Project Name 7. Rows Added 8. Rows Committed 9. Rows Modified 10. Rows Omitted 11. Start Period 12. Status | (blank) | 1. Dataset Name 2. Month (for example, March FY2020) 3. CT Instance name 4. CT Job Number 5. CT Project Domain Name 6. CT Project Name 7. count (for example, 0) 8. count (for example, 310) 9. count (for example, 0) 10. count (for example, 0) 11. Start month (for example, December FY2019) 12. Success/Failure |
| Publish Plan Data | Costing Standard Integration | Plan Name | Dimension | Line Item Code | 1. CT Dataset 2. Instance 3. Job Number 4. Project Domain 5. Project Name 6. Status | (blank) | 1. Dataset Name 2. CT Instance name 3. CT Job Number 4. CT Project Domain Name 5. CT Project Name 6. Success/Failure |

## Plan Management Events

| Event type | Area | Container | Item Type | Item | Attribute | Before | After |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Create Plan | Plan | Plan Name | (blank) | (blank) | 1. Auto Fill Plan Data 2. Baseline 3. Forecast Start Period 4. Name 5. Plan Length (Year) 6. Plan Start Year 7. Plan Type | (blank) | 1. True/False 2. Baseline plan 3. First period of the forecast, for example "August" 4. Name of the Plan 5. Plan length in years 6. Given in YYYY format 7. For example, "Forecast" |
| Rename Plan | Plan | Plan Name | (blank) | (blank) | Name | Old name | New name |
| Delete Plan | Plan | Plan Name | (blank) | (blank) | Name | (blank) | (blank) |
| Archive Plan | Plan | Plan Name | (blank) | (blank) | (blank) | (blank) | (blank) |
| Restore Plan | Plan | Plan Name | (blank) | (blank) | (blank) | (blank) | (blank) |
| Finalize Plan | Plan | Plan Name | (blank) | (blank) | (blank) | (blank) | (blank) |
| Reopen Plan | Plan | Plan Name | (blank) | (blank) | (blank) | (blank) | (blank) |
| Reject Cost Object Plan | Plan | Plan Name | Cost Object | Cost Object Name | (blank) | (blank) | (blank) |
| Approve Cost Object Plan | Plan | Plan Name | Cost Object | Cost Object Name | (blank) | (blank) | (blank) |
| Submit Cost Object Plan | Plan | Plan Name | Cost Object | Cost Object Name | (blank) | (blank) | (blank) |
| Unlock Cost Object Plan | Plan | Plan Name | Cost Object | Cost Object Name | (blank) | (blank) | (blank) |

Note: The Submit Cost Object Plan and Unlock Cost Object Plan events are logged for each individual
status change per cost object.

## Configuration Events

| Event type | Area | Container | Item Type | Item | Attribute | Before | After |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Add Column | Configuration | Labor Line Item, Asset Line Item, Other Line Item, etc. | Labor Line Item, Asset Line Item, Other Line Item, etc. | Column Name | 1. Type 2. Column Name | (blank) | 1. Memo, List, Number, etc. 2. Column Name |
| Update Column | Configuration | Labor Line Item, Asset Line Item, Other Line Item, etc. | Labor Line Item, Asset Line Item, Other Line Item, etc. | Column Name | 1. Mandatory for Data Entry 2. Sensitive Data | (blank) | 1. True/False 2. True/False |
| Delete Column | Configuration | Labor Line Item, Asset Line Item, Other Line Item, etc. | Labor Line Item, Asset Line Item, Other Line Item, etc. | Column Name | 1. Type 2. Column Name | (blank) | (blank) |
| Change Identifier | Configuration | Account | (blank) | (blank) | (blank) | (blank) | (blank) |
| Publish Reference Data | Configuration | Dimension Name | (blank) | (blank) | (blank) | (blank) | (blank) |
| Revert Reference Data | Configuration | Dimension Name | (blank) | (blank) | (blank) | (blank) | (blank) |
| Export Reference Data | Configuration | Dimension Name | (blank) | (blank) | (blank) | (blank) | (blank) |
| Import Reference Data | Configuration | Account | (blank) | (blank) | (blank) | (blank) | (blank) |
| Add Custom List | Configuration | Custom List Name | (blank) | (blank) | Added Custom List Value | (blank) | Custom List Values |
| Update Custom List | Configuration | Custom List Name | (blank) | (blank) | Any of the following:  1. Added Custom List Value 2. Updated Custom List Value 3. Deleted Custom List Value | 1. (blank) 2. Old Custom List Value 3. Custom List Value | 1. Custom List Value 2. New Custom List Value 3. (blank) |
| Delete Custom List | Configuration | Custom List Name | (blank) | (blank) | (blank) | (blank) | (blank) |
| Add Custom Dimension | Configuration | Custom Dimension Name | (blank) | (blank) | 1. Referencing Entities 2. Custom Dimension Name 3. Custom Dimension Description | (blank) | 1. Any entities which reference the Custom Dimension 2. Custom Dimension Name 3. Brief description of the Custom Dimensions (optional) |
| Update Custom Dimension |  |  |  |  |  |  |  |
| Delete Custom Dimension | Configuration | Custom Dimension Name | (blank) | (blank) | (blank) | (blank) | (blank) |
| Add Line Item Filter | Configuration | Line Item Filter Name | (blank) | (blank) | 1. Column Name 2. Filter By 3. Line Item Filter Name | (blank) | Values selected when adding the Line Item Filter |
| Edit Line Item Filter |  |  |  |  |  |  |  |
| Delete Line Item Filter | Configuration | Line Item Filter Name | (blank) | (blank) | (blank) | (blank) | (blank) |
| Update Reference Data In Plan |  |  |  |  |  |  |  |
