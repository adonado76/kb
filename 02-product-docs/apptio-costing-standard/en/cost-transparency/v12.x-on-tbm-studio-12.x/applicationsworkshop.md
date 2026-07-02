---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Applications Workshop"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/applicationsworkshop.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Applications Workshop

Preparing your Application data

1. If you haven’t already done so, load your application data including:
   - List of applications
   - Supplemental application details
2. Following Apptio standard
   practices, categorize each raw data set into the category of Applications.
3. If appropriate, apply a date filter to your application data.

## About the Applications Identifier

The identifier for the Applications Master Data set is the Application ID. This should be a
unique identifier for each application being tracked within Apptio

## About the Application Keys

The keys in the Applications Master Data set are all system generated. The recommended logic is
in the table below.

| Key | Field key is based on | Recommended Logic |
| --- | --- | --- |
| Ticket\_App Key (In 11.6) | User-defined | ="Ticket\_App Key"&&Application ID Only use this key if you install the Service Desk component. To link between Service Desk and Applications, you must have an application ID tied to tickets about that application. |
| Project\_App Key | Application ID | ="Project\_App Key"&&Application ID Only use this key if you install the Projects component. To link between Projects and Applications, you must have an application ID tied to projects about that application. |
| Server\_App Key | User-defined | ="Server\_App Key"&&Application ID |
| App\_Service Key | User-defined | ="App\_Service"&&Application Name If you intend for your services to be groups of applications, you can use Application Group instead of Application Name in the formula above. |
| Storage\_App Key | User-defined | =”Storage\_App”&& Application ID |

## Common Computed Columns Needed for Applications

There are no specific computed columns you need to create. It will vary depending on your data
and what the customer's needs are for how they want to pivot the data.

## Map Data to Applications Master Data

Map your application data to the Applications Master Data set. Most of the mapping should be
self-explanatory at this point. Actual Units, Application Count, and Budgeted Units will most likely
be set to =1. In 12.7 you can now leverage the Column Map function in your raw dataset to map to the
Applications Master Data (Map Columns )

## Add joins to Applications Master Data

Join your Server and Storage Master Data sets to the Applications Master Data set. The Join step
links the current table to other tables by matching values in a column in the current table with
values in a column in another table. (Join data )

| Data Set | Actions |
| --- | --- |
| Applications Master Data | Add a join step. Create a new link between Applications Master Data and Servers Master Data.  **From**: `Applications Master Data.Application ID`  **To**: `Servers Master Data.App Consumer`  Create a new link between Applications Master Data and Storage Master Data.  **From**: `Applications Master Data.Application ID`  **To**: `Storage Master Data.App Consumer` |

## Review the Applications object on the models

| Model | Actions |
| --- | --- |
| Cost | Ensure values are flowing into the Applications object. From Projects to Applications, allocate using the Data-based Reference with an even weighting (this is the default setting). The keys joining Projects to Applications are the Project\_App Key columns in both data sets.  From Servers to Applications, allocate using the Data-based Reverence with an even weighting (this is the default setting). The keys joining Servers and Applications are the Server\_App Key columns in both data sets.  From Tickets to Applications, allocate using the Data-based Reference with an even weighting (this is the default setting). They keys joining Tickets and Applications are the Ticket\_App Key columns in both data sets.  From Storage to Applications, allocate using the Data-based Reference, with an even weighting (this is the default setting). The keys joining Storage and Applications are the Storage\_App Key on the Storage side and the Storage\_App Key on the Applications side. |
| Budget | Ensure values are flowing into the Applications object. From Projects to Applications, allocate using the Data-based Reference with an even weighting (this is the default setting). The keys joining Projects to Applications are the Project\_App Key columns in both data sets.  From Servers to Applications, allocate using the Data-based Reverence with an even weighting (this is the default setting). The keys joining Servers and Applications are the Server\_App Key columns in both data sets.  From Tickets to Applications, allocate using the Data-based Reference with an even weighting (this is the default setting). They keys joining Tickets and Applications are the Ticket\_App Key columns in both data sets.  From Storage to Applications, allocate using the Data-based Reference, with an even weighting (this is the default setting). The keys joining Storage and Applications are the Storage\_App Key on the Storage side and the Storage\_App Key on the Applications side. |
| CapEx | Ensure values are flowing into the Applications object. From Projects to Applications, allocate using the Data-based Reference with an even weighting (this is the default setting). The keys joining Projects to Applications are the Project\_App Key columns in both data sets. |
| CapEx Budget | Ensure values are flowing into the Applications object. From Projects to Applications, allocate using the Data-based Reference with an even weighting (this is the default setting). The keys joining Projects to Applications are the Project\_App Key columns in both data sets. |

## Review Application reports

The following reports are updated after you have configured the Applications object:

- Application Review
- Application Portfolio
- Application List
- Infrastructure Analysis by Application
- New & Retired Apps
- App Review - Detail
- App - Detail
- App - Detail - Cost Pools
- App - Detail - IT Towers
- App - Detail - Servers
- App - Detail - Storage
- App - Detail - Tickets
- App Infra Allocation Table
- App Review - Family Detail
- Applications Validity
- Data Dimensions - Applications
- Data Quality - IT Resources
- Data Quality - Services
- IT Tower Detail
- Infra - App Details

To see details of these reports (including navigation, roles, objectives, and questions answered
for each report), please see the Costing Standard User Guide available in the Online Help.

## Related information

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
