---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Import Actuals from Apptio Costing"
breadcrumb:
  - "Planning"
  - "Integrations"
  - "Connect to Apptio Costing"
source_path: "it-planning/planning/adm/adm_import_actuals.html"
images:
  - "resources/images/it_planning_images/imprefdata.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Import Actuals from Apptio Costing

Importing Actuals brings historical spend data from Apptio Costing into Apptio Planning,
where it can be used for forecasting, variance analysis, and plan comparisons.

Actuals are imported using Automated Data Management (ADM), ensuring that actual spend data
stay aligned across applications.

Note: These tasks require the Admin role with the DataOrchestrationServiceFeatureFullAccess
permission.

Remember: Automated Data Management (ADM) is enabled

## Before you begin

Make sure the following prerequisites are met:

- **Automated Data Management (ADM)** is provisioned in your environment
- ADM is enabled in Apptio Planning:
  - Go to **Settings (⚙) → Company Profile**
  - Select **Enable Automated Data Management Integration**
- Required **Planning Integration datasets** are installed in Apptio Costing
- You have Admin role with the **DataOrchestrationServiceFeatureFullAccess**permission.

## Entity Management

Ensure that **Automated Data Management → Entity Mapping** includes the correct mappings
to the Apptio Costing datasets. When a new custom dimension is added in Apptio Planning, ADM
automatically creates a corresponding entry in the Entity Mapping table—no manual
configuration is required.

1. Go to **Settings (⚙) → Automated Data Management**
2. Navigate to **Entity Management**.
3. Locate the **Actuals** entity in the Entity table.
4. Map the corresponding **Apptio Costing dataset** to the entity. For e.g. Planning
   Actuals Master.
5. Select **Update** to save your changes.

Learn more: [Entity Management](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=administration-entity-management "(Opens in a new tab or window)")

## Import Actuals into Apptio Planning

With Automated Data Management enabled, reference data updates made in Apptio Costing are
automatically imported into Apptio Planning. The end-to-end process works as follows:

1. A user updates datasets mapped to the Actuals entity and performs a Check-in in Apptio
   Costing (Data Studio).
2. The changes are sent to the Costing calculation queue and processed.
3. Once calculations complete, Apptio Costing notifies the Automated Data Management
   service that updated data is available.
4. ADM retrieves the updated actuals from the Costing Staging Environment and imports it
   for use in Apptio Planning.
5. Reference data updates are applied first.
6. Actuals are imported into Apptio Planning for the relevant fiscal periods.

Note: If periods are marked as **Closed** in Spend Management, Automated Data Management
(ADM) will not update data for those periods.

If **Automatically publish reference data imported from Apptio Costing** is enabled in
**Company Profile**:

- Reference data conflicts are resolved automatically
- Actuals import complete without requiring manual publishing

If this option is disabled:

- Data is imported but held in a pending state
- Any reference data conflicts must be resolved manually
- The data must be published before it becomes available in plans

![](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/imprefdata.png)

**Parent topic:** [Connect to Apptio Costing](../../../it-planning/planning/adm/adm_capabilities.html "Apptio Planning integrates with Apptio Costing using Automated Data Management (ADM). ADM is a shared platform service designed to provide a unified, secure, and scalable data exchange experience across Apptio applications.")
