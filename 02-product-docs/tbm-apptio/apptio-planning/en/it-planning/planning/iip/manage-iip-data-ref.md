---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Configure Projects"
breadcrumb:
  - "Planning"
  - "Project Planning"
source_path: "it-planning/planning/iip/manage-iip-data-ref.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Configure Projects

Important: *Available with the* ***Apptio Planning Standard****subscription*

Remember: *Integrated Investment Planning (IIP) feature is enabled*

When using Project Planning in Apptio Planning, you must configure the Project reference data
table to enable project-based planning. Projects can be organized as a flat list or within a
hierarchy and are used to tag plan line items, navigate plans by project, and assign user
permissions at the project level.

## Configure Project Planning

Note: *Admin or Budget Process Owner roles are required to perform these tasks.*

Before you start entering project line items, you’ll need to enable Integrated Investment
Planning (IIP) and set up reference data so projects behave consistently in your model.

Enabling Integrated Investment Planning activates the related Reference Data tables and
adds the Project dropdown to navigate plans**.**

**Enable Project Planning** 

1. Go to **Settings** (Gear icon) **→ Company Profile**.
2. Select **Enable Integrated Investment Planning.**
3. Click **Save and Exit**.

**Setup Project Group Reference Data** 

The **Project Group** reference
data defines the hierarchical structure that Projects roll up to. Project Groups are
typically used to represent portfolios, value streams, or strategic programs that organize
related projects under a single management or reporting layer.

Project Groups are
optional if you have a flat-list of Projects.

1. Navigate to **Configuration → Reference Data → Project Group.**
2. Export the template and populate key fields:

   |  |  |  |
   | --- | --- | --- |
   | **Field** | **Required** | **Description** |
   | Code | x | A unique identifier for the Project Group. Used as the key for project hierarchy mapping. |
   | Name | x | The display name for the Project Group (e.g., “Customer Experience Portfolio” or “Data Center Modernization”). |
   | Parent Code | Conditional | Required if your Project Group hierarchy includes multiple levels (e.g., Value Stream → Portfolio → Program). Leave blank for top-level groups. |
   | Currency Code | Conditional | Required if multi-currency is enabled. Defines the default currency for all projects within this Project Group. |
   | Cost Center Code |  | Cost centers associated with this project group. Enter the corresponding Cost Center Codes, separated by commas. This field is optional—cost centers can also be defined at the project level. |
   | Price Group |  | Optional field to group similar projects or services for internal pricing or rate modeling. |
3. Import the updated CSV and **Publish** the changes so they are available for new
   plans.

**Setup Project Reference Data** 

The **Project** reference data table
defines all **leaf-level projects or investments** that represent the lowest level of
your project hierarchy. These are the records you’ll assign to budget line items in Apptio
Planning.

1. Navigate to **Configuration → Reference Data → Project.**
2. Export the template and populate key fields:

   |  |  |  |
   | --- | --- | --- |
   | **Field** | **Required** | **Description** |
   | Code | x | A unique identifier for the project. Used as the key for data imports, mappings, and reporting. |
   | Name | x | The project’s display name, typically the full project or investment name. |
   | Parent Code | x | The code of the parent Project Group this project rolls up to. Defines hierarchy alignment between Projects and Project Groups. |
   | Allow Any Cost Center | x | Boolean value (True/False). When set to **True**, allows the project to be associated with any cost center during planning. When **False**, restricts planning to the mapped cost centers only. |
   | Default Cost Center |  | The default cost center associated with the project. When a line item is tagged with this project, the cost center is automatically populated. Enter the corresponding Cost Center Code. Make sure this Cost Center Code is listed in the Cost Center Code field. |
   | Cost Center Code | x | Cost centers where this project’s expenses are incurred. Enter the corresponding Cost Center Codes, separated by commas. |
   | Description |  | Optional text field describing the project’s purpose, scope, or key deliverables. |
   | Project Manager |  | The individual responsible for the day-to-day execution and delivery of the project. |
   | Start Date |  | The planned project start date. Can be used for timeline-based reporting or filtering. |
   | Initiative |  | A grouping field to associate this project with a higher-level strategic initiative or program. Can be used for reporting or filtering |
   | Invest Type |  | Defines the type of investment. Can be used for reporting or filtering. |
   | Priority |  | Indicates the project’s priority or ranking within the portfolio. Useful for PMO or strategic alignment reports. |
   | Project Owner |  | The individual or role accountable for project funding, direction, and decision-making. |
   | Sponsor BU |  | The sponsoring business unit funding or benefiting from the project. |
3. Import the updated CSV and **Publish** the changes so they are available for new
   plans.
