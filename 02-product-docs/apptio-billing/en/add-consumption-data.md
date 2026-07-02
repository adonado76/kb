---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "add-consumption-data.html"
title: "Add consumption data for Price x Quantity calculations"
breadcrumb: []
source_path: "add-consumption-data.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Add consumption data for Price x Quantity calculations

Use consumption data when you want to charge business units based on their consumption of
services rather than cost allocations based on factors such as head count. If no additional
consumption data is known, use a list of the Service IDs, which may be provided via appending the
raw data for the Service Library. Do not append the table for the Service Library itself, however
appending the data appended to the Service Library is allowed.

Consumption data usually is pulled from many sources such as VM Clusters data and CMDB applications. When you upload the consumption data, name the tables after the system providing the data, and put the tables in a Consumption category.

After you upload the consumption feed data, append the tables to the Consumption Feed Master
Data table. See [Append data](../studio/data_studio/append-data.html "Applies to: TBM Studio 12.0 and later")  for more information.

The Consumption Feed Master Data fields descriptions follow. All fields are required.

- Business Unit ID
  : A unique identifier for each business unit at the most granular level, matching the Ident in the Business Unit Allocation Master Data table.
- Published
  : Customer specific field for providing more information regarding the charge for an individual line exposed only when a user looks at the details of the service consumption. Valid values are "Yes" or "No"
- Quantity
  : The amount or quantity used for weighting and apportioning the Business Service costs from Service Allocations Direct object to the Business Unit. The quantity depends on the unit of measure selected. For example, email may be allocated based on the number of mailboxes per department or the total amount of email storage per department. Other examples might include the number of business application users per department.
- Service ID  : The unique identifier for the name of the service at the most
  granular level, matching the Service ID in the All Business Services table.
- Source
  : The table that is being appended into the master data set.

**Parent topic:** [Billing Standard](home.html)
