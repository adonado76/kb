---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Entity Management"
breadcrumb: []
source_path: "it-planning/planning/adm/custom-dimension-entitiy-metric.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Entity Management

In Planning customers can create up to 13 custom dimensions to
define the data category sets that extend and enhance your financial planning and
analysis.

To learn more about custom dimensions, see [Custom Reference Data](../manage-custom-reference.htm "(Opens in a new tab or window)").

For (Automated Data Management) ADM to automatically update changes in the custom dimensions to
Planning, it is necessary to update Entity Mapping
table in ADM about the newly created custom dimension so that user can add the dataset name in the
TBM Studio from where the source data is coming.

Adding/deleting custom dimension in Entity Mapping is fully automated.

When a new Custom Dimension is added in Planning, Automated
Data Management> **Entity Mapping** will be automatically updated with new entry in
the Entity table.

1. [Create](../manage-custom-reference.htm "(Opens in a new tab or window)")

   ![image](../../../resources/images/it%20planning_images/create-custom-dim_949x656.png)
2. Navigate to Automated Data Management > Entity Mapping. The “Purchase Order” dimension is
   automatically available in ADM Entity Mapping.

   ![image](../../../resources/images/it%20planning_images/ent-mapp.png)

When a Custom Dimension is deleted in Planning, the corresponding entity
mapping in the Automated Data Management will also be deleted if there is no
other application subscribing the deleted dimension. In case there is active subscription other than
Planning present for the entity being deleted, only the Planning subscription for that dimension will be removed.

**Parent topic:** [Connect to Apptio Costing](../../../it-planning/planning/adm/adm_capabilities.html)
