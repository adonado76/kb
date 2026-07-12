---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "configuration"
title: "Upload the Data Quality Dimensions data"
breadcrumb: []
source_path: "configuration/dataqualitydim.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Upload the Data Quality Dimensions data

To populate the validity scores on the Data Dimensions quality report, upload the four
data tables: Cost Source Validity, Labor Validity, Projects Validity, and Vendor
Validity.

Applies to: Costing Standard on TBM Studio 12.0 and later

## Introduction

Validity measures the match between the cost source, labor, projects, and vendor data and a set
of accepted values for the data. The accepted values are stored in four master data tables under the
Data Quality Dimensions category:

- Cost Source Validity
- Labor Validity
- Projects Validity (if tracking project costs)
- Vendor Validity (if tracking vendor costs)

For each master data table, you upload a single data set that is appended and mapped to the
matching master data set. The uploaded data set must contain columns that can be mapped to the
appropriate columns in the master data table.

## Cost Source Validity column descriptions

The columns in the Cost Source Validity master data set are described in the table below. The
columns are listed in the order they appear in the data set. Required columns are marked with an
asterisk ( \* ). Valid possible values for a column are case-sensitive.

The abbreviations below are used in the Type column.

- A = Label
- # = Numeric
- D = Date
- ID = Unique Identifier
- K = Key field used in allocation between model objects

| Column | Type | Description |
| --- | --- | --- |
| Account | A | The account name or identifier. |
| Cost Center | A | A department or other unit within an organization to whom direct or indirect costs are allocated. |
| Cost Center Owner | A | The owner of the cost center. |
| Cost Pool | A | The name of the cost pool. Valid values: Hardware, Software, Labor, Outside Services, Facilities Power, Telecom, Other |
| Cost Sub Pool | A | A sub-category of cost pool expenditures. For example, HW-Maintenance Support is a cost sub-pool element of the Hardware cost pool. Valid values: Consulting, External Labor, Facilities & Power, HW-Depreciation, HW-Expense, HW-Lease, HW-Maint & Support, Internal Labor, Other, Servie Providers, SW-Amortization, SW-Expense, SW-Lease, SW-Maint & Support, Telecom. |
| Expense Type | A | The Cost Source object model metric driver that is populated by the data from this line item - possible values are: CapEx, OpEx, CapEx Budget, and OpEx Budget. |
| Fixed Variable | A | Designates whether the cost should be categorized as a fixed cost or a variable cost. Valid values are: Fixed, Variable. |
| Owner | A | The person that has responsibility for the line item. |
| Valid | # | This is a system field. Do not enter a value. |

## Labor Validity column descriptions

The columns in the Labor Validity master data set are described in the table below. The columns
are listed in the order they appear in the data set. Required columns are marked with an asterisk (
\* ). Valid possible values for a column are case-sensitive.

The abbreviations below are used in the Type column.

- A = Label
- # = Numeric
- D = Date
- ID = Unique Identifier
- K = Key field used in allocation between model objects

| Column | Type | Description |
| --- | --- | --- |
| Employee Type | A | The type of the labor resource, such as External Personnel or Internal Personnel. |
| Labor ID | A | A user-defined unique identifier for the Labor data set. This column must not have duplicate values. |
| Labor Name | A | The name of the labor resource, such as John Smith. |
| Location | A | The location associated with the labor resource. |
| Position | A | The name of the employee's job position.For example: Helpdesk, support, desktop administrator, storage administrator. |
| Region | A | The geographical region associated with this labor resource. |
| Valid | # | This is a system field. Do not enter a value. |

## Projects Validity column descriptions

The columns in the Projects Validity master data set are described in the table below. The
columns are listed in the order they appear in the data set. Required columns are marked with an
asterisk ( \* ). Valid possible values for a column are case-sensitive.

The abbreviations below are used in the Type column.

- A = Label
- # = Numeric
- D = Date
- ID = Unique Identifier
- K = Key field used in allocation between model objects

| Column | Type | Description |
| --- | --- | --- |
| Business Initiative | A | Specific projects or programs undertaken to achieve specific objectives in the near-term, such as to reduce costs, increase efficiency, and improve sales performance. |
| Business Sponsor | A | Individual or entity who organizes and is committed to the development of a product, program, or project. |
| IT Project Owner | A | The owner of the project. |
| Project ID | A | An identifier for the project. |
| Project Manager | A | The primary contact for this project within the business. |
| Project Name | A | A unique name for the project, such as Oracle v9 Migration or Virtualization Deployment. The project name is used in reports to breakdown costs. |
| Project Portfolio | A | A high-level categorization of the project. A portfolio may contain one or more projects. |
| Spend Type | A | The investment categorization of the IT expenditure or budget.  Valid values are typically: Run the Business, Change the Business, and Transform the Business.  Valid values: **RTB**, **CTB**, or **TTB** |
| Valid | # | This is a system field. Do not enter a value. |

**Parent topic:** [Costing Standard](../home.html)

## Related information

- ![](../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
