---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Allocation Configuration reference data"
breadcrumb: []
source_path: "it-planning/planning/manage-allocation-configuration.html"
images:
  - "resources/images/icons/3-dots.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Allocation Configuration reference data

◆ Applies to: Apptio Planning applications with Project Financial Planning (see [Get started with the Project Financial Planning module](pfp/gs-project-financial.html "◆ Applies to: Planning with Project Financial Planning.")) or Service Demand Planning (see [Get started with the Service Demand Planning module](sdp/gs-service-demand.html))

The tasks below require you to license Project Financial Planning or Service Demand Planning,
then edit the Company Profile to enable Project Financial Planning or Service Demand Planning. See
[Edit the Company Profile](edit-company-profile.html "The Company Profile allows Admin and Budget Process Owner users to configure application-wide settings that customize the display, enable or disable features, and define workflow behavior across Apptio Planning.").
The tasks below can only be performed by users assigned to the Admin or Budget Process Owner roles.
For additional information on roles, see Frontdoor permissions and roles.

Watch this video from Apptio Education Services: [Configuring Reference Data: Project
Financial Planning Dimensions](https://community.ibm.com/community/user/viewdocument/configuring-reference-data-labor-d?CommunityKey=4100dfb8-fc23-4203-83c7-019253cf7c0b&tab=librarydocuments "(Opens in a new tab or window)"). TIP: Jump to 4:30 to
see information about the transfer account type.

Dimensions are the essential data categories in budget line items. Many built-in dimensions have
dependencies on other dimensions (see [Reference data attribute and dimensions dependencies](manage-reference-data.html) for more information). You
can import dimensions reference data from a .csv file or from Costing Standard and export dimensions
reference data templates and table data (see [Manage dimensions](manage-reference-data.html)).

The Transfer Account Default dimension allows the Project Owner, Service Owner, Business
Relationship Manager, and Business Unit Owner to determine the correct allocation of money for
consuming or supporting various projects or services. This feature requires that Service Demand Planning or Project Financial Planning be enabled. See [Edit the Company Profile](edit-company-profile.html "The Company Profile allows Admin and Budget Process Owner users to configure application-wide settings that customize the display, enable or disable features, and define workflow behavior across Apptio Planning.").

1. In the navigation menu, select Configuration > Reference Data > Transfer Account
   Default.
2. Select ![more](../../../../../03-media/apptio-planning/resources/images/icons/3-dots.png) in the top
   right corner of the table, select Export > Export All.
3. Open the downloaded .csv file and update the data table values as required:
   - Consumer Type - A Cost Object that consumes the resources of another Cost Object
   - Provider Type - A Cost Object that provides the resources to another Cost Object
   - Transfer In Account - The account receiving payment (requires account code)
   - Transfer Out Account - The account used to pay (requires account code)
4. Now, Configuration > Reference Data > Transfer Account Default, and then import the
   updated .csv file.

When entering Provider and Consumer data, refer to this table of allowable combinations:

| Provider | Consumer |
| --- | --- |
| External Labor Pool | Project |
| External Labor Pool | Services |
| Internal Labor Pool | Project |
| Internal Labor Pool | Services |
| Services | Business Unit |
| Services | Services |
| Services | Project |
| Services | Department |

Tip: You can integrate this dimension with Costing Standard to import transfer account
data from Costing Standard.
