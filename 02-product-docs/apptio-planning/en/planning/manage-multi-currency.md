---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Multi-Currency Conversion Rate Tables reference data"
breadcrumb: []
source_path: "planning/manage-multi-currency.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Multi-Currency Conversion Rate Tables reference data

The tasks below can only be performed by users assigned to the Admin or Budget Process
Owner roles. For additional information on roles, see Frontdoor permissions and roles.

Dimensions are the essential data categories in budget line items. Many built-in
dimensions have dependencies on other dimensions (see [Reference data attribute and
dimensions dependencies](manage-reference-data.html) for more information). You can import dimensions reference data from
a .csv file or from Costing Standard and export dimensions reference data templates and table data
(see [Manage
dimensions](manage-reference-data.dital "(Opens in a new tab or window)")).

![](../../resources/images/it%20planning_images/icon_video.png)

Watch this video from Apptio Education Services: [Configuring Reference
Data: Multi-Currency Dimensions](https://community.apptio.com/videos/1992 "(Opens in a new tab or window)").

Or see all [Apptio planning video and training resources](https://community.apptio.com/viewdocument/apptio-products-video-catalog?CommunityKey=1bdb1f0b-9524-43d4-b987-5d2b8595eebf "(Opens in a new tab or window)")

## Manage Actuals Currency Rate reference data

Actuals Currency Rate reference data defines the currency conversion rates used to convert
multiple currencies to a common currency. This allows you to see summarized views of actuals.

1. Enable support for multiple currencies in the Company Profile (see [Edit the Company Profile](edit-company-profile.dita "(Opens in a new tab or window)")).
2. In the navigation menu, select Configuration > Reference Data.
3. In the Standard Dimensions table, select Actuals Currency Rate.
4. Select ![](../../resources/images/icons/icon-options_23x20.png) > Export.
5. In the Export file window, under Format options, you can change the format of the exported
   data.
6. Select Export.

   The reference data is exported as a .csv file.
7. Open and edit the exported .csv file.

   Do not change the column headings or data structure of
   the file.

   The From Currency column should contain the tenant currency code.

   The
   Effective From column should use the YYYY-MM-DD or MM-DD-YYYY date format.
8. Save the file in the .csv format.
9. Now, select Configuration > Reference Data > Actuals Currency Rate. Then, select![](../../resources/images/icons/icon-options_23x20.png)> Import.
10. Drag and drop the file with the data onto the highlighted area of the Import File window.
11. Select Import.
12. To publish the changes, select ![](../../resources/images/icons/icon-options_23x20.png) > Publish > Publish.
13. To cancel the changes, select ![](../../resources/images/icons/icon-options_23x20.png) > Revert > Revert.

## Manage Plan Currency Rate reference data

Plan Currency Rate reference data defines the currency conversion rates used to convert multiple
currencies to a common currency in budget plans and forecasts.

1. Enable support for multiple currencies in the Company Profile (see [Edit the Company Profile](edit-company-profile.dita "(Opens in a new tab or window)")).
2. In the navigation menu, select Configuration > Reference Data.
3. In the Standard Dimensions table, select Plan Currency Rate.
4. Select ![](../../resources/images/icons/icon-options_23x20.png) > Export.
5. In the Export file window, under Format options, you can change the format of the exported
   data.
6. Select Export.

   The reference data is exported.
7. Update the file as required.

   The From Currency column should contain the tenant currency
   code.

   The Effective From column should use the YYYY-MM-DD date format.
8. Now, select Configuration > Reference Data > Plan Currency Rate. Then, select![](../../resources/images/icons/icon-options_23x20.png)> Import.
9. Drag and drop the file with the data onto the highlighted area of the Import File window.
10. Select Import.
11. To publish the changes, select ![](../../resources/images/icons/icon-options_23x20.png) > Publish > Publish.
12. To cancel the changes, select ![](../../resources/images/icons/icon-options_23x20.png) > Revert > Revert.
