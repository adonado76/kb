---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Reference Data Overview"
breadcrumb:
  - "Planning"
  - "Configuration and Administration"
source_path: "it-planning/planning/edit-publish-reference.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Reference Data Overview

Note: Admin or Budget Process Owner roles are required to manage Reference Data.

Reference data defines the core dimensions and lookup values used throughout Apptio Planning.
These dimensions categorize and contextualize financial, labor, contract, asset and project
data — ensuring consistency, accuracy, and clean data handling across all plans.

Think of reference data as the “vocabulary” your planning environment uses to classify costs,
resources, cost centers, projects, departments, accounts, and other key attributes.

## When to Manage Reference Data

As an Admin or Budget Process Owner, you will configure reference data when you:

- Set up a new environment or plan
- Onboard new cost centers, departments, projects, vendors, accounts, or other entities
- Need to update classification codes, add new values, or reorganize hierarchies
- Want to tailor reference data to your organization’s structure or chart of accounts

These tasks are performed under **Configuration > Reference Data**. Changes to reference
data apply automatically to all newly created plans. To apply those changes to an existing
plan, you must run **Update Reference Data** for that plan.

## Standard Dimensions

Apptio Planning ships with a set of built-in “standard dimensions” that cover the core
planning needs. The exact list may vary based on the enabled features in your environment.

|  |  |  |
| --- | --- | --- |
| **Category** | **Dimension Name** | **Description** |
| Financials | Account | The Account field categorizes what type of expense or revenue a line item represents, such as software, hardware, travel, salaries, or services. Accounts typically align to the organization’s chart of accounts and provide consistency between planning, budgeting, and financial reporting. |
| Account Category | Account Category groups similar financial accounts under broader reporting categories (e.g., Travel, Facilities, Salaries) for simplified planning and reporting. |
| Cost Center | A Cost Center represents an organizational unit used to track and manage where costs are incurred. |
| Department | A Department represents a functional group within the organization. Used to define ownership and accountability in Apptio Planning. |
| Location | The Location field identifies the geographic site or region associated with a line item, such as a data center, office, or country. |
| Variance Driver | Variance Driver is used to group and explain variances by identifying root causes or contributing factors. |
| Vendor | The Vendor field represents third-party providers of services or resources. Used to track and plan external spend by supplier. |
| Labor Planning | Labor Allocation Rules | Labor Allocation Rules define which GL accounts labor costs are posted to for a given labor headcount. These rules control how labor expenses are generated and allocated based on attributes such as role, vendor, location, or employee type, ensuring labor-related financials are mapped to the correct accounts consistently across plans. |
| Labor Rates | Labor Rates captures labor rate assumptions by attributes such as role, location, employee type, and vendor—used for headcount planning. |
| Role | The Role field represents job functions or titles used in labor planning to apply appropriate cost assumptions. |
| Contract Planning | Contract Type | Contract Type Defaults specifies default attributes for different contract types, including how costs are amortized and which accounts they map to. |
| VAT Rate | VAT Rate defines value-added tax percentages that can be applied to eligible contract line items. VAT rates ensure taxes are calculated consistently and accurately across plans based on regional or organizational tax requirements. |
| Asset Planning | Asset Class | Asset Class Defaults defines default accounting and depreciation settings for different types of capital assets (e.g., Hardware, Software, Building Improvements). |
| Project Planning | Project | The Project field represents planned or ongoing work, such as application development, infrastructure upgrades, or business transformation initiatives. Associating spend with projects enables organizations to track costs, labor, and resources against specific investments, providing visibility into total project spend and supporting portfolio-level analysis. |
| Project Group | Project Group organizes multiple related projects under a common structure for reporting or budgeting purposes. |
| Labor Activity Planning | Labor Activity Type | Labor Activity Type defines how labor costs are charged and cross-charged between cost centers when labor effort is allocated to projects. Each activity type maps a provider (department) account and a consumer (project) account, ensuring labor charges are correctly allocated to the appropriate accounts. |
| Project Labor Role | Project Labor Role specifies labor role definitions within the context of a project, including associated labor rates and billing currency. |
| Multicurrency | Actuals Currency Rate | Actuals Currency Rate represents the exchange rates used to convert actual spend from the source currency to the target currency. |
| Plan Currency Rate | Plan Currency Rate represents the exchange rates used during the planning process to convert planned amounts from the planning input currency to the reporting or corporate currency. |

## Dependencies Between Dimensions

Many dimensions are interdependent, meaning that certain attributes rely on values defined in
other dimensions. For example:

- A **Department** may reference a **Cost Center** code.
- An **Asset Class**or **Contract Type** may reference an **Account** code for
  depreciation or amortization account.
- A **Labor Allocation Rule** may reference an **Account** code for cost allocation.

These dependencies ensure data integrity and consistent classification across different types
of financial entries. When editing or deleting values, always review dependencies to avoid
breaking references.

## Custom Dimensions

Apptio Planning supports Custom Dimensions, allowing you to extend the standard data model to
capture organization-specific attributes. You can create up to 40 custom dimensions to support
your planning and reporting needs.

To create and manage custom dimensions, refer to Schemas.

## Updating Reference Data in a plan

When a plan is created, it automatically uses the latest published version of reference data
available at that time. If reference data is updated later, existing plans do not
automatically inherit those changes. You must explicitly update the plan to apply the latest
reference data.

How to Update Reference Data

1. Open the plan you want to update.
2. Ensure you are viewing **All Departments**.
3. Open the **ellipsis (…) menu** and select **Update Reference Data**.
4. Review the **impact summary** shown in the confirmation modal, which includes:
   1. Line items to be updated
   2. Line items to be deleted
   3. New items
   4. Removed items
   5. Parent codes changed
5. If the impact looks correct, select **Update** to apply the changes.

**Important Notes**

- By default, updates that woulddelete existing line items are blocked to prevent
  accidental data loss.
- To allow destructive updates, an Admin must enable **Disable Update Reference Data
  Restrictions** in the Company Profile.
- When destructive updates are allowed, a **backup plan is automatically created**
  before applying the reference data update.

- **[Standard Dimensions](../../it-planning/planning/manage-reference-data.html)**
