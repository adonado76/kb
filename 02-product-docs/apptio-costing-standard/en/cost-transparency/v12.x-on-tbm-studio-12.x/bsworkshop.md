---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Business Services Workshop"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/bsworkshop.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Business Services Workshop

## Steps to populate your Business Services

At this point, you need to populate your Business Services with your business services data. If
you do not have a list of business services, you can use a list of your applications or groups of
applications. The steps below describe how to populate the Business Services.

1. If you have a Business Services List you can load that into Apptio and place under the Business
   Services
2. If you do not have a list you can do the following:
   1. Locate the All Business Services Reference List
   2. Export the list out of Apptio
   3. Load into a new table call "Customer" Business Services List
   4. Configure with lookups to pull any needed information and append to the Business Services.

## About the Business Service Identifier

The identifier for the All Business Services data set is the Service ID. This should be a unique
identifier for each service.

## About the Business Service Keys

The keys in the All Business Services Data set are mostly all user-defined. The recommended logic
is in the table below.

| Key | Field key is based on | Recommended Logic |
| --- | --- | --- |
| **App\_Service Key** | User-defined | ="App\_Service"&&Service ID If you are using a list of applications as your services, the recommended logic is:  ="App\_Service"&&Application ID |
| **Project\_Service Key** | Service ID | =”Project\_Service” && Service ID |
| **ITRT\_Service Key** | User-defined | ="ITRT\_Service" && Service ID |
| **Service\_Service Allocations Direct Key (In 11.6)** | User-defined | ="Service\_Service Allocations Direct Key" && Service ID |

## Common Computed Columns Needed for Business Services

There are no specific computed columns you need to create. It will vary depending on your
data.

## Map data to All Business Services Data

When you published the Service Library, the All Business Services data set was populated. You do
not need to map any data at this point.

## Review the Business Services object on the models

| Model | Actions |
| --- | --- |
| **Cost** | Ensure values are flowing into the Service Allocations Indirect object. From Business Services to Service Allocations Indirect, allocate using the Data-based Reference with an even weighting (this is the default setting). The keys joining Applications to Business Services are the Service ID Key columns in both data sets.  From Service Allocations Indirect to Business Unit Allocation, allocate using weighting such as headcount. |
| **CapEx** | Ensure values are flowing into the Service Allocations Indirect object. From Business Services to Service Allocations Indirect, allocate using the Data-based Reference with an even weighting (this is the default setting). The keys joining Applications to Business Services are the Service ID Key columns in both data sets.  From Service Allocations Indirect to Business Unit Allocation, using weighting such as Headcount. |

## Review Business Services reports

The following reports are updated after you have configured the Business Services object:

- Services Review
- Services Portfolio
- Service List
- Service Category - Detail
- Service Detail
- Service Offering Detail
- Service Review - Detail
- Services - Group Detail
- Services - Unit Cost Trend
- Application Portfolio - Detail - Cost Pools
- Application Portfolio - Detail - IT Towers

To see details of these reports (including navigation, roles, objectives, and questions answered
for each report), please see the Costing Standard User Guide available in the Online Help.

## Related information

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
