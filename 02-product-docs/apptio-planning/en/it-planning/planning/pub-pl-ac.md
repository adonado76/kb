---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Publish Projects List to Apptio Costing"
breadcrumb:
  - "Planning"
  - "Integrations"
  - "Connect to Apptio Costing"
source_path: "it-planning/planning/pub-pl-ac.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Publish Projects List to Apptio Costing

Note: These tasks require the Admin role with the DataOrchestrationServiceFeatureFullAccess
permission.

**Prerequisite:** Automated Data Management (ADM) enabled

The plan-level Projects List can be published to Apptio Costing using Automated Data Management
(ADM), ensuring project data stays aligned across applications.

## Before You Begin

Make sure the following prerequisites are met:

- **Automated Data Management (ADM)** is provisioned in your environment
- ADM is enabled in Apptio Planning:
- Go to **Settings (⚙) → Company Profile**
- Select **Enable Automated Data Management Integration**
- Required **Planning Integration datasets** are installed in Apptio Costing
- You have Admin role with the **DataOrchestrationServiceFeatureFullAccess** permission.

## Entity Management

Ensure that **Automated Data Management → Entity Mapping** includes the correct mappings to
the Apptio Costing datasets.

1. Go to **Settings (⚙) → Automated Data Management**
2. Navigate to **Entity Management**.
3. Locate the **Publish Project List** entity in the Entity table.
4. Map the corresponding **Apptio Costing dataset** to the entity.
5. Select **Update** to save your changes.

Learn more: [Entity Management](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=administration-entity-management "(Opens in a new tab or window)")

## Publish Projects List to Apptio Costing

To publish Project List from Plan to Apptio Costing:

1. Navigate to **Plan > Projects List**.
2. Select the **overflow menu (⋯)**.
3. Choose **Publish To Apptio Costing**.
4. Select the **Status** button to view the status of the publishing job.

To learn more about managing projects, refer to [Manage Projects](iip/project-list-document.html).

**Parent topic:** [Connect to Apptio Costing](../../it-planning/planning/adm/adm_capabilities.html "Apptio Planning integrates with Apptio Costing using Automated Data Management (ADM). ADM is a shared platform service designed to provide a unified, secure, and scalable data exchange experience across Apptio applications.")
