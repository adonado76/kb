---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "data-sharing"
title: "Schedule Plan Publishes"
breadcrumb: []
source_path: "data-sharing/scheduling-the-data-shares.html"
images:
  - "resources/images/icons/icon-delete.png"
  - "resources/images/icons/icon_details.png"
  - "resources/images/icons/pencil-icon.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Schedule Plan Publishes

## ADM scheduler capability

A scheduler capability in Automated Data Management (ADM) is built
to automate data sharing between :

- Apptio Planning plans (budget and forecast) data into Apptio Costing
- Cloudability into Apptio Costing.

This capability will enable flexible options to schedule jobs to publish Plan and
Cloudability data to Apptio Costing and a centralized place to
manage data sharing between Apptio’s product portfolio.

Admin users can now create daily, weekly and monthly schedules using Automated Data Management integration to publish Plan and Cloudability data from any
active plan in New, Open or Final state to Apptio Costing (Cost
Transparency). Additionally, they can also select the specific period in Apptio Costing for which the data should be published.

![Sceduler Capability](../resources/images/data%20sharing_images/adm-scheduler-capability.png)

## Prerequisite

- IT Planning, Automated Data Management, TBM Studio must be in
  the same environment.

  ![IT Planning, Automated Data Management, TBM Studio](../resources/images/data%20sharing_images/same-env.png)
- Ensure the permission DataOrchestrationServiceFeatureFullAccess is enabled on the role
  that will be managing Automated Data Management schedules. By
  default, Admin, Apptio Admin and Apptio Partner roles have this permission enabled.
- [Connection](data_sharing_connections.html) to TBM Studio
  project established in Automated Data Management
- Automated Data Management flag must be enabled in Apptio Planning
- Apptio Planning
  [entities](data_sharing_entity_mapping.html) are created
  and configured in Automated Data Management

  ![Prerequisite](../resources/images/data%20sharing_images/adm-prerequisite1.png)

  ![Prerequisite](../resources/images/data%20sharing_images/adm-prerequisite2.png)

Note:

Refer the [ADM configuration guide](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=costing-configure-automated-data-management "(Opens in a new tab or window)") to setup the integration
between Apptio Costing and Apptio
Planning.

## Configuring Planning to Costing

Navigate to the Entity Schedule page to create, edit or delete schedules to publish a Plan
to Costing. The schedule creation process generates multiple jobs based on the entities
selected and applies the same schedule config for each Planning line item type/entity.
However, the user has the flexibility to manage the publishes to Costing separately for each
entity/line item type if needed.

Automated Data Management keeps the 1:1 mapping between Apptio Planning line item type to Automated Data
Management entity to dataset name in Apptio Costing. The
dataset name can be changed in Automated Data Management based on
customers configuration.

Note: Manual triggers are available for adhoc publishes of Plan and Cloudability data to
Costing.

| **ADM Entity** | **Apptio Planning Line Item Type** | **Apptio Costing Default dataset name** | Manual trigger |
| --- | --- | --- | --- |
| Financial Budget | Finacial line Item type in a Budget plan type | Apptio PlanningF Budget | Plan > Expenses > Summary tab > Actions > Publish Financials to Cost Transparency... |
| Labor Budget | Labor line Item type in a Budget plan type | Apptio PlanningF Labor Budget | Plan > Expenses > Labor tab > Actions > Publish Labor to Cost Transparency... |
| Asset Budget | Asset line Item type in a Budget plan type | Apptio PlanningF Asset Budget | Plan > Expenses > Assets tab > Actions > Publish Assets to Cost Transparency... |
| Contract Budget | Contract line Item type in a Budget plan type | Apptio PlanningF Contract Budget | Plan > Expenses > Contracts tab > Actions > Publish Contracts to Cost Transparency... |
| Labor Activity Budget | Labor Activity line item type in a Budget plan type | Apptio PlanningF Labor Activity Budget | Plan > Expenses > Labor Activity tab > Actions > Publish Labor Activity to Cost Transparency... |
| Financial Forecast | Finacial line Item type in a Forecast plan type | Apptio PlanningF Financial Forecast | Plan > Expenses > Summary tab > Actions > Publish Financials to Cost Transparency... |
| Labor Forecast | Labor line Item type in a Forecast plan type | Apptio PlanningF Labor Forecast | Plan > Expenses > Labor tab > Actions > Publish Labor to Cost Transparency... |
| Asset Forecast | Asset line item type in a Forecast plan type | Apptio PlanningF Asset Forecast | Plan > Expenses > Assets tab > Actions > Publish Assets to Cost Transparency... |
| Contract Forecast | Contract line item type in a Forecast plan type | Apptio PlanningF Contract Forecast | Plan > Expenses > Contracts tab > Actions > Publish Contracts to Cost Transparency... |
| Labor Activity Forecast | Labor Activity line item type in a Forecast plan type | Apptio PlanningF Labor Activity Forecast | Plan > Expenses > Labor Activity tab > Actions > Publish Labor Activity to Cost Transparency... |

## Create Schedule for Planning

1. Go to **Enhanced Access Administration** and select **Automated Data Management**
2. Select **Entity Schedule** from the left-hand panel
3. Select **Add Schedule** (ApptioOne Planning is selected by default under Producer
   option)
4. Enter the Schedule Name in the **Schedule Name** field

   ![Add Schedule](../resources/images/data%20sharing_images/add-schedule1.png)
5. Select the **Plan Name** from the dropdown to create schedule
6. Select the **Entities** you want to create schedule (depending on the selected budget
   or forecast plan, the available entities will be updated)

   ![Add Schedule](../resources/images/data%20sharing_images/add-schedule2.png)
7. Set the time period in CT you want to publish
   - Current Month: This dynamic value will change as you move through time. Eg.when July month
     is selected, the Plan and Cloudability data will be published to July month in TBM
     Studio.
   - Previous Month: This dynamic value will change as you move through time. Eg. If this
     option is chosen, when the current month is July, the Plan and Cloudability data will
     be published to June month in TBM Studio.
   - Start Month of FY: This dynamic value will change as you move through time. Eg. when July
     is set as start of the fiscal year the Plan and Cloudability data will be published to
     the July month in TBM Studio.
   - Customize: The plan will be published in the month of the selected date. This option
     is used when the Plan start of fiscal year is different than the start of the fiscal
     year in TBM Studio
8. Select **Next** to setup the schedule cadence
9. Select the **Schedule Type** (daily or weekly or monthly)
10. Select the **Start Date** and **End Date** for the schedule. If **No End Date**
    is selected, **End Date** field will be disabled
11. Set the frequency to trigger the job
    - Select one or multiple times a day
    - Select one or multiple times a week
    - Select one or multiple days of the month
12. Select **Time** and **Time Zone** to trigger the job
13. Select **Create Schedule**

## Edit Schedule

1. Go to **Enhanced Access Administration** and **Automated Data Management**
2. Select **Entity Schedule** menu from the left-hand panel
3. Select pencil icon(![Edit Icon](../../../../03-media/apptio-planning/resources/images/icons/pencil-icon.png)) to edit schedule
4. Edit the plan and schedule details as required
5. Select **Save Schedule**

   ![Save Schedule](../resources/images/data%20sharing_images/edit-schedule-new.png)

## Delete Schedule

1. Go to **Enhanced Access Administration** and **Automated Data Management**
2. Select **Entity Schedule** menu from the left-hand panel
3. Select the pencil icon (![Edit Icon](../../../../03-media/apptio-planning/resources/images/icons/pencil-icon.png)) to delete schedule
4. Select Delete icon (![Delete Icon](../../../../03-media/apptio-planning/resources/images/icons/icon-delete.png)) and then select **Delete** from the confirmation popup

## Status Check

1. Go to **Enhanced Access Administration** and **Automated Data Management**
2. Select **Entity Schedule** menu from the left-hand panel
3. Select the notes icon (![Notes Icon](../../../../03-media/apptio-planning/resources/images/icons/icon_details.png)) to see the details about *Schedule status* and
   *Run History*

   ![Schedule status](../resources/images/data%20sharing_images/status-schedule.png)

## Creating Schedule for Cloudability

1. Go to **Enhanced Access Administration** and select **Automated Data Management**
2. Select **Entity Schedule** > **Entity Details** from the left-hand menu
3. Click the **Add Schedule** button.
4. Enter the **Schedule Name**.
5. Select the **Schedule Type** (daily or weekly or monthly).

   Enter

   | **Frequency** | **Best For** | **Example Use Case** |
   | --- | --- | --- |
   | Daily | Real-time cost monitoring | FinOps teams tracking daily spend |
   | Weekly | Regular reporting cadence | Weekly cost reviews with stakeholders |
   | Monthly | Budget tracking | Monthly financial reporting |
   | Custom | Specific business needs | Aligned with billing cycles |
6. Select the **Start Date** and **End Date** for the schedule. If **No End Date**
   is selected, **End Date** field will be disabled.
7. Select the appropriate values in **Time** and **Time Zone** fields to trigger the
   job.
8. Select **Next** to setup the schedule cadence.
9. Click the **Create Schedule** button.

Note: Some best practices to keep in mind while scheduling -

- Set the schedule during off-peak hours, preferably early morning.
- Ensure the schedule aligns with your local time zone.
- Allow sufficient time for data processing before the start of business
  operations.

Important: The following system constrains are applicable:

- Only one active schedule is allowed per environment.
- Each cloud vendor can have only one execution plan per schedule.

**Parent topic:** [Connect to Apptio Costing](../it-planning/planning/adm/adm_capabilities.html "Apptio Planning integrates with Apptio Costing using Automated Data Management (ADM). ADM is a shared platform service designed to provide a unified, secure, and scalable data exchange experience across Apptio applications.")
