---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Business Units Workshop"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/buworkshop.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Business Units Workshop

Preparing your Business Unit data

1. If you haven't already done so, load your business unit data including:
   - List of business units including headcounts
2. Following Apptio standard
   practices, categorize each raw data set into the category of Business Units.
3. If appropriate, apply a date filter to your business unit data.

## About the Business Unit Identifier

The identifier for the Business Units Master Data set is the Ident column. You can have up to
five levels built into your business unit hierarchy. The five levels defined in Apptio are:

- Governing Body
- Business Unit
- Program
- Project
- Location

The Ident column is often a concatenation of these five columns. However, you may decide that you
don't need all five levels as the level of detail you need in your reports. For example, you may
decide to just use the Business Unit column as the Ident column.

## About the Business Unit Keys

The keys in the Business Unit Allocation Master Data set are mostly all user-defined. The
recommended logic is in the table below.

| Key | Field key is based on | Recommended Logic |
| --- | --- | --- |
| **Service Allocations Direct\_BU Key (In 11.6)** | User-defined | ="Service Allocations\_BU" && Bunsiness Unit Identifier |
| **Project\_BU Key** | Business Unit | ="Project\_BU"&&Business Unit&&Project\_BU Key Metafield |

## Common Computed Columns Needed for Business Unit

The only computed column you may need to create is the Ident column if you want to concatenate
data together.

## Map data to Business Unit Allocations Master Data

Map your business unit data to the Business Unit Allocations Master Data set. Most of the mapping
should be self-explanatory at this point. In 12.7 you can now leverage the Column Map function in
your raw dataset to map to the Business Unit Allocations Master Data ([Map
Columns](https://community.apptio.com/docs/DOC-10561 "(Opens in a new tab or window)"))

## Review the Business Unit Allocation object on the models

| Model | Actions |
| --- | --- |
| **Cost** | Ensure values are flowing into the Business Unit Allocation object. From Service Allocations Direct to Business Unit Allocation, allocate using the Data-based Reference with an even weighting (this is the default setting). The keys joining Service Allocations Direct to Business Unit Allocation are the Service Allocations Direct\_BU Key columns in both data sets.  From Service Allocations Indirect to Business Unit Allocation, allocate using Headcount or other allocation options.  From Projects to Business Unit Allocation, allocate using the Data-based Reference with an even weighting (this is the default setting). The keys joining Projects to Business Unit Allocations are the Project\_BU Key columns in both data sets. |
| **Budget** | Ensure values are flowing into the Business Unit Allocation object. From Business Services to Business Unit Allocation, you can allocate costs using two possible options:   - By Headcount - By Revenue   To allocate by headcount, weight the allocation by Business Unit Allocation Master Data.Employees. |
| **CapEx** | Ensure values are flowing into the Business Unit Allocation object. From Service Allocations Direct to Business Unit Allocation, allocate using the Data-based Reference with an even weighting (this is the default setting). The keys joining Service Allocations Direct to Business Unit Allocation are the Service Allocations Direct\_BU Key columns in both data sets.  From Service Allocations Indirect to Business Unit Allocation, allocate using the Table based allocation.  From Projects to Business Unit Allocation, allocate using the Data-based Reference with an even weighting (this is the default setting). The keys joining Projects to Business Unit Allocations are the Project\_BU Key columns in both data sets. |

## Review Business Unit reports

The following reports are updated after you have configured the Business Units object:

- Business Unit Review
- Business Unit Review - Details
- Business Unit Portfolio
- Business Unit List
- Impact of Retiring Applications
- Business Unit Allocation Validity
- Business Unit
- Business Unit - Department
- Business Unit Invoice
- Service - BU Consumption Trend
- Data Dimensions - Business Units

To see details of these reports (including navigation, roles, objectives, and questions answered
for each report), please see the Costing Standard User Guide available in the Online Help.

## Related information

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
