---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Unique Labor Resource Identification"
breadcrumb: []
source_path: "planning/iip/unique-labor-resource-identification.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Unique Labor Resource Identification

## Problem

In Labor Activity schema the resource is allocated to a project using Resource name.

If there are two resources with same name, it is not possible to uniquely identify the resource
for the allocation to project when using UI. As per the below screenshot, Resource dropdown shows 2
entries of John, it is hard to tell whether you are assigning 1st L-1 or L-2 line from labor to a
project.

![](../../../resources/images/it%20planning_images/3.65-1.png)

![](../../../resources/images/it%20planning_images/3.65-2_861x233.png)

If labor activity lines are imported using a csv file that contains two resources with same name,
the lines don’t get imported giving a duplicate resource error, when actually these two resources
are separate individuals but having same name. Please check the reference screenshot below.

![](../../../resources/images/it%20planning_images/3.65-3.png)

Due to this limitation, customers must adopt workarounds to make resource names unique using some
prefix or suffix to the original name. This poses further challenge when customers want to refresh
the labor data each time using the source data from labor management software because there isn’t an
easy way to update the labor activities and names will not match due to workarounds used.

## Solution

From Settings > Company Profile, enable External Code option. The External Code column
will appear.To learn more, see [External Unique Identifier](../external-unique-identifier.htm "(Opens in a new tab or window)").

For Existing labor please enter Employee Id, Employee Number or equivalent unique identifier from
external labor management systems as External Code. In case of Planned labor please enter
corresponding Position Id or equivalent unique identifier from external labor management systems as
External Code. Once the planned position is filled and Employee Id is available, you can edit the
Position Id to corresponding Employee Id.

![](../../../resources/images/it%20planning_images/3.65-4.png)

Navigate to Labor Activity tab and check the Resource column. The dropdown values will show
resources as <code> - <name>. Note that, only the dropdown view will be updated to show both
code and name but once value is allocated it shows as a name same as other attributes such as
account, cost center etc. This change will solve the issue of uniquely identifying resources with
identical names when using UI.

![](../../../resources/images/it%20planning_images/3.65-5.png)

For Import, the behavior is same as Account or Cost Center attribute. Export the template and
ensure that the Resource External Code column is included in the exported file.

![](../../../resources/images/it%20planning_images/3.65-6.png)

While importing, it is mandatory to provide the value for Resource External Code, otherwise the
line will be omitted (similar to importing expenses without providing Account Code in the csv). The
updated import logic will be effective when importing Labor Activity data from CT via ADM as
well.
