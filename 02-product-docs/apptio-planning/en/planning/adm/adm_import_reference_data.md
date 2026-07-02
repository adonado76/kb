---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Import Reference Data"
breadcrumb: []
source_path: "planning/adm/adm_import_reference_data.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Import Reference Data

Planning uses reference data as baseline information for planning purposes, and includes
information such as chart of accounts, department hierarchy, or lists of cost centers and
vendors.

Ensure that Automated Data Management > Entity Mapping has the appropriate ApptioOne Cost
dataset mapping. With Automated Data Management, the reference data changes in ApptioOne Cost will
be automatically imported and published into Planning. The following is the process flow:

1. As soon as a user makes changes to the datasets that are mapped to the reference data entities
   and performs check-in action in the TBM Studio, the changes are sent to the Calculations build queue
   in costing.
2. Once the calculations are complete, Costing notifies Automated Data Management service about the
   availability of new data updates.
3. Automated Data Management downloads these updates from Costing and makes them available in
   Planning

If the Automatically publish reference data imported from Cost
Transparency checkbox is enabled, then any conflicts due to dimension data dependencies
will be auto-resolved and all the imported changes will be published on the Planning side. However,
if this option is not enabled, the changes will be imported but data conflicts will need to be
manually resolved before the data can be published. For more information, see [Select the Automatically publish reference data imported from
Cost Transparency checkbox.](adm-import-baseline-data.html "When Automated Data Management is enabled (see Enable Automated Data Management Integration in ApptioOne Plan), the Entity Mapping page in Automated Data Management is updated with the following new entities:")

Note: On-demand import of dimension data from Costing to Planning is currently not supported with
Automated Data Management, which means you have to re-upload the data in Costing with
appropriate changes to resolve the data conflicts to make these changes reflect on the Planning
side.
