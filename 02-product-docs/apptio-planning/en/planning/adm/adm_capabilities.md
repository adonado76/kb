---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Automated Data Management Capabilities"
breadcrumb: []
source_path: "planning/adm/adm_capabilities.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Automated Data Management Capabilities

You can use Costing Standard Integration to import reference data dimensions and actuals from
Costing Standard. For more information, see [Working with Costing Standard Integration Panel](../cti_panel.html "(Opens in a new tab or window)"). However, importing data
from Costing Standard is a manual process. Automated Data Management lets you automate this
task.

## Automated Data Management for Reference Data

If you are an administrator, you need to know if and when changes have taken place in the
reference data on the Costing Standard side so that updated reference data is pulled whenever
required in the Planning. However, there is a wait time for the Costing Standard calculations to
complete and hence, the calculation queue should be actively monitored to finish before the data can
be pulled into Planning. Once the data is ready, you need to manually click buttons on the Costing
Standard Integration page in Planning and resolve any conflicts due to dependencies between
dimensions, as described in the [Reference Table Dependencies Diagram](https://community.apptio.com/docs/DOC-9956 "(Opens in a new tab or window)"). All this may contribute
to a tedious process especially when it comes to debugging and resolving conflicts. See [Troubleshoot Planning data upload
errors](../troubleshooting.dita "(Opens in a new tab or window)") to learn more about manually fixing data import errors.

Automated Data Management solves this problem by enabling you to automatically import reference
data from Costing Standard as soon as it is available. It is no longer required to coordinate
between the two systems to find identify the right time to pull the data, and there is no
requirement to manually click buttons to import dimensions. This, in turn, relieves you from the
pain of resolving dimension dependency conflicts as well.

## Automated Data Management for Actuals

To help manage spend, you can compare the budget plan or forecast with historical actuals. The
source of actuals may be your financial management system, TBM Studio, or Costing Standard. Once
integration is enabled, it is easy to import actuals from Costing Standard to the plan. See [Import actuals from Costing Standard](../integrate-ct.html "If your organization runs both Apptio Costing Standard and an Apptio planning application, you can integrate them to share data.") for more
information on importing actuals. However, just like reference data, it's a manual or on-demand
process to select different buttons each time you want updated actuals to be imported to the
plan.

Automated Data Management helps you manage the import process by setting up a configuration so
that whenever actuals are added for a specific period in Costing Standard, they can automatically be
made available in the plan.

## Automated Data Management for Plan Baseline Data

For the purpose of Planning, you can bring baseline data such as existing labor head count, fixed
assets, existing contracts etc. from external source systems to TBM Studio. You can then utilize the
modeling capability provided by TBM Studio to perform data mappings and data transformation so that
data imported from external systems is consumable for financial budget planning process. At present,
you have to manually export this data from Costing & Planning - Cost and then manually import to
a specific plan in Costing & Planning - Plan. This is a time consuming procedure.

With the introduction of Automated Data Management for Plan Baseline Data, you can define the
mapping between the dataset in TBM Studio and the expenses table in Costing & Planning - Plan
using the Entity Mapping feature. This allows you to fetch data with the click of a button
from within a specific plan, as and when required.
