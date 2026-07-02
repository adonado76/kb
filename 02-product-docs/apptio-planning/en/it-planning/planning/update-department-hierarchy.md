---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Update department hierarchy"
breadcrumb: []
source_path: "it-planning/planning/update-department-hierarchy.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Update department hierarchy

## About this task

The tasks below can only be performed by users assigned to the Admin or Budget Process Owner
roles. For more information on roles, see Frontdoor permissions and roles.

Dimensions are the essential data categories in budget line items. Many built-in dimensions have
dependencies on other dimensions. For more information, see [Reference data
attribute and dimensions dependencies](manage-reference-data.html#dimensiondepend). You can import dimensions reference data from a
`.csv` file or from Costing Standard and export dimensions reference data templates
and table data. For more information, see [Manage dimensions](manage-reference-data.html).

The following dimensions are linked to the Department dimension:

- Cost Object Permissions
- Cost Center
- Plan Currency Rate

## Procedure

If you plan to update or rearrange the department hierarchy, you must:

1. Update the Cost Center and Department reference data. For more information, see [Manage Financial Dimensions
   reference data](manage-financial-dimensions.html)).
2. Update the Cost Object Permissions reference data. For more information, see [Manage Cost Object Permissions reference
   data](manage-cost-object.html)).
3. If support for multiple currency is enabled, you must update the Plan Currency Rate
   reference data. For more information, see [Manage Multi-Currency Conversion Rate Tables reference data](manage-multi-currency.html)).
4. Navigate to your plan and click Update Reference Data. For more
   information, see [Force a plan to use
   updated reference data](force-plan-use.html)).
