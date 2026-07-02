---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Change the identifier for Cost Objects and Dimensions"
breadcrumb: []
source_path: "planning/change-identifier.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Change the identifier for Cost Objects and Dimensions

The Code property serves as a unique identifier for many default data dimensions.

The Change Identifiers feature acts as a find-and-replace feature within Planning. It
enables an admin to update the identifier for cost objects and some dimensions.

Note: Changing the identifier will apply the change to all plans across time, regardless of whether
the plan is open or closed.

![](../../resources/images/it%20planning_images/change_identifier.png)

The Change Identifiers feature is available for the following dimensions:

- Account
- Cost Center
- Department
- Location
- Vendor
- All custom dimensions

If Project Financial Planning is enabled:

- Project
- Project group

## Change the identifier for Cost Objects and Dimensions

1. In the navigation menu, select Configuration > Reference Data.
2. Select the correct dimensions group tab, and select the appropriate dimension (for example,
   Account).
3. Select ![](../../resources/images/icons/3-dots.png)
   > Identifiers Template.
4. Review the export options, make adjustments as needed, and click Export.

   This initiates
   a spreadsheet download. The spreadsheet has two columns. The first column is populated with the
   original code values. The second column will contain the new code.
5. Open and edit the spreadsheet. Fill out the second column of the identifier template to map the
   old code to the new code values, then save the template.

   If there are just a few updates to be
   made, copy and paste the values from the first column into the second column. Then, update specific
   rows as needed.
6. In Reference Data select the dimension, then select ![](../../resources/images/icons/3-dots.png) > Change Identifiers.
7. Click inside the dialog box, and select the updated identifier template, then click
   Import.

   If you receive an error message, try the [troubleshooting
   option](change-identifier.html#ChangetheidentifierforCostObjectsandDimensions__Troubleshootchangeidentifieruploaderror).
8. Review changes for accuracy.
9. Make updates to other data dimensions that use the previous identifier. For a list of
   dependencies, see [Reference
   data attribute and dimensions dependencies](manage-reference-data.html#dimensiondepend).

   The Publish option appears when a new
   Cost Center or Department is updated. However, you do not need to select Publish for this
   change to take effect.

   - You can change Cost Center and Department independent of each other.
   - If you update the Code in Department reference data, it does not update Cost Center code or the
     Default Cost Center code. The old Cost Center is still associated with the Department.
   - If you update the Code in the Cost Center dimension, it will update Cost Center code and Default
     Cost Center in the Department reference data, but not the Department's Code, as it still associates
     the new Cost Center with the old Department.
   - Project Codes in existing plans will not reflect any changes performed by change identifiers if
     Investment Planning is enabled.

## Troubleshoot change identifier upload error

Follow these steps if you get an error when you upload the identifier template:

1. Open the template which contains the new identifiers.
2. Copy the column header for the first column and paste it into the header of the second
   column.
3. Add the word 'New' to the front of the new pasted value in the second cell.
4. In Reference Data, select the dimension, then select ![](../../resources/images/icons/3-dots.png) > Change Identifiers. Upload the
   template.
