---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Create report collections"
breadcrumb: []
source_path: "reports/creating-report-collections.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Create report collections

Applies to: TBM Studio 12.0 and later

In the Apptio system, report collections group related reports so users can easily navigate
between reports in a similar topic or perspective. Administrators configure report collections to
limit which user roles are able to access reports within a collection. Administrators can set role
permissions for report collections and create or delete custom report collections.

For more information on:

- Roles, see [Frontdoor permissions and roles](https://community.apptio.com/docs/DOC-10531 "(Opens in a new tab or window)").
- Report permissions, see [Work with report permissions](control-access-reports-11755.htm "(Opens in a new tab or window)").

## Create a custom report collection

Only Administrators can create report collections, and only in the Costing Standard project. Once
created, report collections are available across an entire project, and other users can add and
delete reports from a collection.

1. On the Project tab, in the Project Data group,
   click Report Collections.
2. In the Manage Report Collections dialog box, click Add
   Collection.![](../../resources/images/studio_images/studioimages/studio_manage%20report%20collections_add%20collection.png)A new entry is added to the list of collections. The entry is named New report
   collection. The new collection is displayed in the Selected
   Collection field.

   ![](../../resources/images/studio_images/studioimages/studio_manage%20report%20coll_new.png)
3. To change the name of the collection, click the New report collection
   entry in the list of collections, and then click the collection name in the Selected
   Collection field.

   ![](../../resources/images/studio_images/studioimages/studio_manage%20report%20collections_selected%20collection.png)

## Delete a custom report collection

Select the report in the Manage Report Collections dialog.

Click the Delete Collection button.

NOTES:

- Users can only delete custom report collections.
- Alternatively, in TBM Studio 12.7 and later, you can explore other options described in [Disable reports](disablereports.htm "(Opens in a new tab or window)") and [Work with report
  permissions](control-access-reports-11755.htm "(Opens in a new tab or window)").

## Add a report to a collection

1. Click the report in the Project Explorer.
2. On the Report tab, in the Grouping group, click
   Assign to Collection.

   ![](../../resources/images/studio_images/studioimages/studio_report_assign%20to%20collection.png)
3. Open the drop-down list and select the collection to which the report should be added. A report
   can only be assigned to one report collection.

## Remove a report from a collection

1. Navigate to the report and check out the report.
2. On the Report tab, in the Grouping group, click
   Assign to Collection.
3. In the menu that appears, click the red X next to the name of the collection.

![](../../resources/images/studio_images/studioimages/studio_report%20collection_custom.png)

Tip: If you have content creation access, you can delete a report from a collection
using the Manage Report Collections dialog. To remove a report this way,
click the red X on the right side of the record for that report within the collection:

![](../../resources/images/studio_images/studioimages/studio_manage%20report%20collections_custom%20finance%20report.png)

## Hide or show a report in a collection

Instead of deleting a report from a report collection, you can hide a report in a report
collection. For example, you can do this for out-of-the-box reports you don't want users to access
because the report's data is not yet available. Then, once the data to light up the report is
loaded, you can show the report.

Never delete an out-of-the-box report from a report collection. Instead, hide the report.

## Hide a report in a report collection

1. On the Project tab, in the Project Data group,
   click Report Collections. The Manage Report Collections dialog box
   appears.
2. In the Available Collections list on the left, select the report
   collection that contains the report to hide. The list of existing reports in the selected report
   collection appears on the right.
3. For the report(s) you want to hide, clear the Show in navigator checkbox
   next to the report name:![](../../resources/images/studio_images/studioimages/studio_manage%20report%20collections_cost%20center%20trend.png)
4. Click the Close button.

## Show a hidden report in a report collection

1. On the Project tab, in the Project Data group,
   click Report Collections. The Manage Report Collections dialog box
   appears.
2. In the Available Collections list on the left, select the report
   collection that contains the report to show.
3. For the report(s) you want to show, select the Show in navigator checkbox
   next to the report name, and then click OK.

## Add a report collection navigator to a report

The report collection navigator is a report component that gives users an easy way to move
between reports in a collection. When you add a report to a collection, the navigator component
automatically is added to the report.

![](../../resources/images/studio_images/rc-1_697x318.png)

![](../../resources/images/studio_images/rc-2_732x350.png)

## Custom Color Palettes

Applies to R12.10.10 and later.

The Admin (Customer admin, Apptio Admin, Partner Admin) can create corporate colors and have a
defined color palette to choose the colors for charts, for better user experience with visually
appealing information.

To know more about color palette application, refer [Custom Color Palettes](../admin/color-enhancement.htm "(Opens in a new tab or window)").

![](../../resources/images/studio_images/ccp-rcpopup.png)

Note: If one color palette is selected for a report collection and a different color palette is
selected for a report within it, then the color palette for that report alone will be change.
