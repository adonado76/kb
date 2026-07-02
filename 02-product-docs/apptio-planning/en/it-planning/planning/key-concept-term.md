---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Key Concepts and Terminology"
breadcrumb:
  - "Planning"
  - "Getting started"
source_path: "it-planning/planning/key-concept-term.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Key Concepts and Terminology

Understanding the foundational concepts in Apptio Planning will help you navigate the
application. Below are definitions of key terms frequently used in Planning.

**Cost Object (Departments)**

A **Cost Object i**s a financial structure used in Apptio Planning to organize and
allocate costs. It provides the foundation for assigning expenses, establishing cost
ownership, and tracking financial performance.

In Apptio Planning, Cost Objects are synonymous with **Departments** and can be structured
into a **hierarchy**, allowing costs to roll up from leaf-level departments to higher-level
groups. This hierarchy enables organizations to view and analyze costs at multiple levels of
detail, from individual departments to consolidated roll-ups.

**[Plan](create-plan.html)**

A **Plan** is a structured financial model in Apptio Planning where users enter, adjust,
and analyze data over a defined time horizon. Plans can represent budgets, forecasts, or
multi-year outlooks.

**Budget Plan**

A **Budget Plan** is a type of plan that does not include actuals. All periods are fully
editable, enabling planners to set projections from scratch or reset expectations without
being constrained by historical performance.

**Forecast Plan**

A **Forecast Plan** includes actuals from historical periods. Only future periods are
editable, allowing planners to adjust projections based on past performance while keeping
actual results fixed.

**[Snapshot](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=workflows-submit-review-approve-return-plans#subrevappret__snapshot__title__1 "(Opens in a new tab or window)") (Version)**

**Snapshots** are saved versions of a Department’s plan that capture its data at a
specific point in time. They provide a historical record of how a Department’s plan looked
when it was submitted or manually saved.

- Snapshots can only be created for **leaf Departments** (the lowest level in the
  department hierarchy).
- A snapshot is automatically generated whenever a Department submits its plan.
- Users can also create snapshots on demand to preserve the state of a Department’s plan
  at any time.
- When comparing plans, you can select a prior snapshot to compare, making it easier to
  track changes, validate assumptions, and measure progress against earlier versions.

**[Targets](set-financial-targets.html "You can set financial targets in Apptio Planning to define spending goals or limits for OpEx, CapEx, and Headcount at the department level. Targets establish top-down financial expectations that can be compared against bottom-up plan data throughout planning and forecasting cycles.")**

**Targets** represent financial or headcount goals set by administrators or leadership.
These serve as benchmarks for comparing plan values and ensuring alignment with organizational
objectives.

In Apptio Planning, targets can be set for **OpEx**, **CapEx**, and **headcount**,
and are applied at the **department level**. These targets provide guidance to planners,
helping ensure departmental plans roll up to meet overall organizational goals.

**[Spend Management](spend-management.html "Spend Management enables you to manage actual data by importing monthly transactions into Apptio Planning. By integrating actuals, you can align your plan and forecast models with real performance, enabling better visibility, variance tracking, and decision-making.")**

**Spend Management** is the process of importing and managing actuals (historical
financial data) in Apptio Planning. This ensures plans are based on accurate and up-to-date
financial performance.

**[Reference Data](edit-publish-reference.html)**

**Reference Data** provides standardized values—such as Departments, Cost Centers, or
Accounts—that can be reused across plans. It ensures consistency, accuracy, and alignment
across all planning activities.

When a new plan is created, it automatically uses the latest **published version** of
Reference Data. If Reference Data is later updated, you can manually refresh a plan to use the
newest published version.

Important: Updating Reference Data can sometimes result
in data loss. For example, if a Cost Center or Account is removed, any related line items in
the plan will also be deleted.

To help prevent destructive updates, you can adjust the **Disable Update Reference Data
Restrictions** setting in the Company Profile. When restrictions are disabled, the system
automatically creates a copy of the plan before applying Reference Data updates, giving you a
fallback option if you need to revert.

**[Standard Dimension](manage-reference-data.html)**

**Standard Dimensions** are the predefined, out-of-the-box dimensions provided by Apptio
Planning. They represent the core financial and organizational structures that are commonly
needed for planning, such as Departments, Accounts, Vendor, and Labor Rates. These dimensions
are always available and cannot be removed.

**[Custom Dimensions](manage-custom-reference.html "The tasks below can only be performed by users assigned to the Admin or Budget Process Owner roles. For additional information on roles, see Frontdoor permissions and roles.")**

Custom Dimensions are **user-created dimensions** that extend the standard data model.
They allow organizations to capture additional levels of analysis or categorization beyond the
out-of-the-box structure.

- You can create up to **40 Custom Dimensions**.
- Custom Dimensions can be added to schemas and referenced in line items to support
  reporting, filtering, and analysis tailored to your business needs.

**Attributes**

Attributes are **additional fields (columns)** that can be added to a Dimension or Schema.
They provide more descriptive or operational detail without requiring a new dimension. For
example:

- On a **Department** dimension, you might add attributes like *Department Owner*
  or *Region*.
- On a **Project** schema, you might add attributes such as *Project Priority* or
  *Funding Source*.

Attributes are especially useful for storing metadata that helps drive reporting or
filtering but doesn’t require a full dimension structure.

**Supported Attribute types**:

|  |  |
| --- | --- |
| **Type** | **Description** |
| String | Stores text values such as names, descriptions, or codes. Supports a maximum of 256 characters. |
| Date | Captures a specific calendar date (e.g., contract start date or hire date). |
| Integer | Stores whole numbers without decimals (e.g., headcount, number of licenses). |
| Numeric | Stores numeric values, including decimals, for financial or quantitative data (e.g., cost, rate). |
| Percentage | Represents numeric values as percentages (e.g., allocation rate, utilization). |
| Memo | Used for long-form text or notes, such as comments or detailed descriptions. Supports a maximum of 1024 characters. |
| List | Provides a predefined set of selectable values (e.g., region, department type). |
| User | References a user within Apptio Planning, allowing assignment of ownership or responsibility. |
| Boolean | Stores true/false values, used for toggles or binary indicators (e.g., active/inactive, yes/no). |
| Link | Stores clickable URLs that open in a new browser tab. Useful for referencing external resources such as Jira tickets, documentation, or dashboards. |

**[Schema](manage_schema.html "Schemas define the structure of data in Apptio Planning. They specify the tables, fields, and relationships that determine how information is stored, linked, and surfaced across Expense tabs such as Labor, Contracts, Assets, and Financials.")**

A **Schema** defines the structure of data in Apptio Planning, including tables, fields,
and relationships. It governs how information is stored, linked, and displayed in line-item
tables.

When a dimension matches across schema types (Labor, Contracts, Assets, Labor Activity,
Actuals and the Financial schema), that field will automatically roll up and display in the
Summary tab.

**Line Item Types**

**Line Item Types** define the kind of data being planned, tracked, or reported in Apptio
Planning. Each type aligns with a specific module or function:

- **Financial Line Items** – Capture operating (OpEx) or capital (CapEx) expenses;
  surfaced in the Summary and Other tabs.
- **Labor Line Items** – Represent headcount and labor costs; managed in the Labor tab.
- **Contract Line Items** – Track vendor agreements and associated costs; managed in
  the Contract tab.
- **Asset Line Items** – Record asset purchases and depreciation; managed in the Asset
  tab.
- **Labor Activity Line Items** – Capture project labor effort (hours) and
  cross-charges; managed in the Labor Activity tab.
- **Actuals** – Represent actual financial transactions; used in Spend Management and
  drives actual summarization rules.

**[Labor Allocation Rules](manage-labor-allocation-rules.html)**

**Labor Allocation Rules** define how labor costs are distributed across different
financial accounts. They are used to generate labor costs to various General Ledger accounts,
ensuring that the full burdened cost of each headcount (including salary, benefits, and
overhead) is accurately represented in financial planning and reporting.
