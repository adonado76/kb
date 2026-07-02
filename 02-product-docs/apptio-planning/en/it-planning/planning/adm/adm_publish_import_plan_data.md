---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Publish Plan Data to Apptio Costing"
breadcrumb:
  - "Planning"
  - "Integrations"
  - "Connect to Apptio Costing"
source_path: "it-planning/planning/adm/adm_publish_import_plan_data.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Publish Plan Data to Apptio Costing

Publishing plan data from Apptio Planning to Apptio Costing enables you to share
finalized budget and forecast data with your cost-allocation and cost-transparency environment.
Through the built-in integration and scheduling features of Automated Data Management (ADM), you
can export financial line items (Financials, Labor, Labor Activity, Contracts, Assets) from
Planning and push them directly into Apptio Costing.

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

Before publishing plan data, confirm that **Automated Data Management → Entity Mapping**
is correctly configured to map Apptio Planning entities to the appropriate Apptio Costing
datasets.

1. Go to **Settings (⚙) → Automated Data Management**.
2. Navigate to **Entity Management**.
3. In the **Entity** table, locate the Planning entities you want to publish, such as:
   - Financial Budget
   - Financial Forecast
   - Asset Budget
   - Asset Forecast
   - Contract Budget
   - Contract Forecast
   - Labor Budget
   - Labor Forecast
   - Labor Activity Budget
   - Labor Activity Forecast
4. For each entity, map the corresponding **Apptio Costing dataset** that will receive
   the published plan data.
5. Select **Update** to save your changes.

Learn more: [Entity Management](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=administration-entity-management "(Opens in a new tab or window)")

## Manual Publish

To manually publish data from a plan:

1. Open the plan in Apptio Planning.
2. Select the desired plan from the drop-down list.
3. Choose the Expense tab you wish to publish (for example: Labor, Labor Activity,
   Contracts, Assets, Summary/Other).
4. Click the **Actions menu → Publish to Apptio Costing...**
5. The publish request is queued and processed in the background
6. Monitor the status of the publish job via the **Settings (⚙) → Apptio Costing****Integration →****Status** page

## Scheduled Publish

To automate regular exports of plan data to Apptio Costing (e.g., daily, weekly, or
monthly):

1. Go to **Settings (⚙) → Automated Data Management →****Entity Schedule** to
   navigate to the Automated Data Management interface.
2. Click **Add Schedule**. Set:
   1. **Producer**: Apptio Planning
   2. **Plan**: Select the plan to publish
   3. **Entities (Line Item Types)**: Choose which line items to include (Financial
      Budget, Labor Budget, Contract Forecast, Asset Budget, etc.)
3. Define the publication period (e.g. current month, previous month, start of fiscal
   period, or a custom date), and schedule frequency (daily, weekly, monthly).
4. Set the start date/time and optional end date. Then **Create Schedule**.
5. Once configured, ADM will automatically export and publish the selected plan data to
   Costing at each scheduled interval.

Schedules can be edited or removed at any time via the same Entity Schedule page in ADM. Learn
more: [Schedule Plan Publishes](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=administration-schedule-plan-publishes "(Opens in a new tab or window)").

**Parent topic:** [Connect to Apptio Costing](../../../it-planning/planning/adm/adm_capabilities.html "Apptio Planning integrates with Apptio Costing using Automated Data Management (ADM). ADM is a shared platform service designed to provide a unified, secure, and scalable data exchange experience across Apptio applications.")
