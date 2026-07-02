---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "technology-integration"
title: "Data Connectivity &amp; Architecture"
breadcrumb: []
source_path: "technology-integration/architecture.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Data Connectivity &amp; Architecture

The following diagram illustrates the data flow from IBM Turbonomic to IBM Apptio's Datalink. The steps are outlined below:

![](../../resources/images/ct_images/trb-arch-1.jpg)

1. IBM Turbonomic Setup and Data Discovery  : IBM Turbonomic performs its
   normal setup and discovers data for each target added. A full list of supported targets is available
    [here](https://www.ibm.com/docs/en/tarm/8.13.0?topic=documentation-target-configuration "(Opens in a new tab or window)")  . Turbonomic discovers resources, monitors utilization, and
   recommends actions. The diagram shows a few sample targets in blue.
2. IBM Apptio Target Type Configuration  : Set up the IBM Apptio Target
   Type in IBM Turbonomic as per the prerequisites. This setup pushes data from IBM Turbonomic to IBM
   Apptio's Datadrop. Ensure IBM Apptio’s Datadrop has been configured correctly. Instructions for
   setting up Datadrop/SFTP Server on the Apptio side can be found in the [Apptio Help Center](#).
3. File Loading and Refreshing  : Files in JSON format are loaded daily
   into Apptio's cloud-based Datadrop/SFTP server. The payload consists of four datasets: Pending and
   Executed Actions for both On-Prem and Cloud environments. Each day, four new files will appear in
   the Datadrop viewer repository. For details on file content, refer to the Data Payload section.
4. Datalink Connectors Setup  : Create Datalink connectors to pull data
   from the Datadrop repository into TBM Studio:
   - For Pending Actions, set the upload behavior to "OVERWRITE." Each daily file from IBM Turbonomic
     shows the latest Pending Actions, so it should overwrite the previous file in TBM Studio.
   - For Executed Actions, set the upload behavior to "APPEND." The file contains Executed Actions
     for the last 24 hours, so append the data to create a Month-To-Date view.
   - TBMA can schedule connector runs (Daily, Weekly, or Monthly). To automate the process, assign
     the table destination names directly to the datasets created by the IBM Apptio Framework.
5. Data Integration into TBM Studio  : After running the connectors, the
   payload will be stored in the following TBM Studio tables:
   - Turbo Cloud Pending Actions
   - Turbo On-Prem Pending Actions
   - Turbo Cloud Executed Actions
   - Turbo On-Prem Executed Actions

## IBM Apptio Framework

![](../../resources/images/ct_images/trb-framework.jpg)

The framework diagram provides an overview of the Hybrid IT Optimization architecture powered by
IBM Turbonomic’s Pending and Executed Actions. It introduces new tables and master datasets from an
IBM Turbonomic perspective (installed via the IBM Turbonomic – Actions component) and from a broader
Hybrid IT Optimization perspective (installed via the Hybrid IT Optimization component).

This architecture relates new data points to existing data in the IBM Apptio model. There are 12
configuration steps, with red bubbles indicating user-required configurations and orange bubbles for
automated/pre-configured steps. These steps are detailed in the Configuration section.

## IBM Apptio Model Allocations

![](../../resources/images/ct_images/trb-model-alloc.jpg)

The IBM Apptio framework provides an overview of new tables and datasets, while the diagram
above focuses on new model metrics and allocations:

Hybrid Cost/Hybrid Charge

These are new, parallel metrics that leverage existing cost/charge models, focusing solely on
the infrastructure layer's total cost. The existing metrics are not reused to avoid double
allocations and conflicts.

Users need to create drivers for these models. Once allocations to the new infrastructure model
object are set up, the remaining model will follow the depicted flow.

Action Count

New standalone metrics for month-to-date (MTD) and year-to-date (YTD) reporting on Pending and
Executed Action counts.

Potential Savings/Realized Savings

These are key metrics in the Hybrid IT Optimization framework.

- Potential Savings are based on Pending Actions.
- Realized Savings are based on Executed Actions. Both metrics are divided into two dimensions,
  Cost and Charge
  - Cost  : For Cloud, the $ Savings are sourced directly from IBM
    Turbonomic. For On-Prem, the savings are calculated using the action value change (e.g., 12 vCPU
    reduced to 2 vCPU, yielding a 10 vCPU savings) and the unit cost of the technical services.
    Adjustments are made based on the % Addressable set by the user.
  - Charge  : This follows a similar approach, using the price of the
    technical services and adjusting based on the % Addressable set by the user. These savings are
    targeted for the Business-Facing Service or Application Consumer.

Level of Addressable

Users must set and edit the % Addressable for both unit cost and price. Setting this percentage
impacts both cost and charge savings calculations. The breakdown of savings is split into:

- Direct Savings
- Delayed Savings
- Cost Avoidance

Users have full autonomy to define the allocation of % Addressable across these categories. This
can be set via the Workbench Tab on the Infrastructure Optimization – Provider View report.

![](../../resources/images/ct_images/trb-arch-addr.jpg)

Columns in light grey are expected to be appended to the Editable Table, sourced from the
existing Service Catalogue, while the columns in white are to be defined by the user.

![](../../resources/images/ct_images/trb-arch-et.jpg)

**Parent topic:** [Costing Standard](../home.html)
