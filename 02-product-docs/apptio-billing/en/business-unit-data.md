---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "business-unit-data.html"
title: "Add business unit data"
breadcrumb: []
source_path: "business-unit-data.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Add business unit data

If the CT - Business Units component has been installed and configured
in Cost Transparency, skip this step. If the component has not been installed, then you must add
data to the Business Unit Allocation Master Data table.

1. Upload a file containing the business data to a table in the Billing Standard project. Place
   the table in the General category and name it `Business Unit
   Data` . See [Upload a data file](../studio/data_studio/upload-data-file.html "Applies to: TBM Studio 12.0 and later. TBM Studio accepts data from flat files in comma-, tab-, pipe-, tilde-, colon-, and semi-colon-separated formats. Before you can upload data, you must create a table where the data will be loaded, if it does not already exist.") for more information .
2. Append the Business Unit Data table to the Business Unit Allocation Master Data table.
   See [Append
   data](../studio/data_studio/append-data.html "Applies to: TBM Studio 12.0 and later") for more information .

Required data from Business Unit Allocation Master Data

- Business Unit - A logical element or segment of a company representing
  a specific business function and a place on the organizational chart. The business unit is under the
  domain of a manager. In Billing Standard, the Business Unit is level 1 in the organization hierarchy
  and Department is level 2.
- Ident - A unique identifier for each business unit.

Recommended data from Business Unit Allocation Master Data

- Contractor Headcount - The number of external contractors working in
  the business unit.
- Employee Headcount - The number of full-time employees or non-contract
  labor working in the business unit.
- Location - The physical/geographical location of the business unit. On
  business unit reports, location is used to group data and provide an additional level of
  granularity.

Optional data from Business Unit Allocation Master Data

- Governing Body - The governing body is a higher level entity in the
  organization structure than the business unit.   
   Examples :
  operating entities, international entities.

**Parent topic:** [Billing Standard](home.html)
