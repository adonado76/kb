---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Project Configuration reference data"
breadcrumb: []
source_path: "planning/pfp/manage-project-configuration.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Project Configuration reference data

◆ Applies to: Apptio planning applications with [Project Financial Planning](gs-project-financial.htm "(Opens in a new tab or window)"). The tasks below require you to
license Project Financial Planning. To enable Project Financial Planning features, see [Edit the Company
Profile](../edit-company-profile.htm "(Opens in a new tab or window)").

The tasks below can only be performed by users assigned to the Admin or Budget Process Owner
roles. For additional information on roles, see Frontdoor permissions and roles.

|  |  |
| --- | --- |
|  | Watch this video from Apptio Education Services: [Configuring Reference Data: Project Financial Planning Dimensions](https://community.apptio.com/videos/1995 "(Opens in a new tab or window)").  Or see all [Apptio planning video and training resources](https://community.apptio.com/viewdocument/apptio-products-video-catalog?CommunityKey=1bdb1f0b-9524-43d4-b987-5d2b8595eebf "(Opens in a new tab or window)"). |

## Manage Project reference data

Dimensions are the essential data categories in budget line items. Many built-in dimensions have
dependencies on other dimensions (see [Reference data attribute and dimensions dependencies](../manage-reference-data.html#dimensiondepend) for more information). You
can import dimensions reference data from a .csv file or from Costing Standard and export dimensions
reference data templates and table data (see [Manage dimensions](../manage-reference-data.html "(Opens in a new tab or window)")).

Tip: Users assigned to the Admin role have a shortcut for publishing Project reference
data. On the List tab of the Summary view for all projects, use the Actions
button, Publish to Reference Data command. Be aware that once Project data is published this
way, you cannot revert back to previous Project reference data. If you want to archive that data,
export it to .csv format before publishing this way.

Projects are a type of Cost Object. The following information describes the Project dimensions'
fields.

1. In the navigation menu, select Configuration > Reference Data.
2. Select the Project tab on the Reference Data page.
3. In the Project table, select Project.
4. Select ![](../../../resources/images/icons/icon-options_23x20.png) > Export.
5. In the Export file window, under Format options, you can change the format of the exported
   data.
6. Select Export. The reference data is exported as a .csv file.
7. Open the downloaded .csv file. Do not change the column headings or data structure of the file.
   Update the data table values as required:
   - Code - The unique identifier for a project.
   - Name - The project's name.
   - Parent Code - Represents your project hierarchy. A Parent Code value is the code value of
     its immediate higher-level or parent account (if any).
   - Allow Any Cost Center - A value of TRUE allows you to assign the project to any Cost
     Center. A value of FALSE defaults to the current Cost Center.
   - Benefit Amount - The expected monetary value of the completed project. This value and the
     Benefit Period are used to calculate return on investment.
   - Benefit Period - The number of months until the project returns a monetary benefit. This
     period and the Benefit Amount value are used to calculate return on investment.
   - Currency Code - The common currency for the project. This value is required when support
     for multiple currencies is enabled in the Company Profile (see [Support for multiple
     currencies](../support-multiple-currencies.htm "(Opens in a new tab or window)")). The common currency value should be the three letter ISO code for the currency.
     If no currency code is entered, the default common currency is used.
   - Description - A summary of the project.
   - Duration - The expected project lifespan in number of months.
   - Est. CapEx (non-labor) - The estimated capital expenditures (CapEx) value for the
     project. This is used for demand vs. capacity evaluation.
   - Est. External Labor - The estimated external labor headcount (for example, vendors) for
     the project. This is used for demand vs. capacity evaluation.
   - Est External Labor Rate - The estimated pay rate for external labor for the projects.
     This is used for demand vs. capacity evaluation.
   - Est. Internal Labor - The estimated internal labor headcount for the project. This is
     used for demand vs. capacity evaluation.
   - Est. Internal Labor Rate - The estimated pay rate for internal labor for the project.
     This is used for demand vs. capacity evaluation.
   - Est. Labor Capitalization - The estimated labor capitalization rate for internal and
     external labor for the project. This is used for demand vs. capacity evaluation.
   - Est. OpEx (non-labor) - The estimated operating expenditures (OpEx) value for the
     project. This is used for demand vs. capacity evaluation.
   - Group Rank - A numeric value indicating the project's relative ranking among all project
     groups.
   - Price Group - Determines the price group for the project for Region-based or
     Tiered-pricing models.
   - Project Manager - The assigned project manager. Choose from user accounts defined via
     Enhanced Access Administration.
   - Project Status - Project status value.
   - Rank - A numeric value indicating the project's relative ranking among all projects.
   - Score - A numeric value indicating the project's relative overall score among all project
     groups.
   - Score Overridden – This dimension is used on Project reference data export and import.
     When exporting data, this dimension indicates if the Score value has been automatically calculated
     (False value), or manually overridden (True). When importing data, True means the Score value will
     override any automatically calculated value. False means to ignore the uploaded Score value, and
     automatically calculate one instead.
   - Start Date - The planned start date for the project.
   - Cost Center Code - The identifier for corresponding Cost Centers. When importing actuals,
     they are allocated per Cost Center, then mapped to Cost Object. A project can be associated with
     multiple Cost Centers and can include line items (volumes, labor, or expenses) recorded for more
     than one Cost Center. Add multiple Cost Centers to the table cell using a comma to separate
     them.
8. Save the file in the .csv format. Now, select **Configuration > Reference Data >
   Project**.
9. Select ![](../../../resources/images/icons/icon-options_23x20.png) > Import. Drag and
   drop the file with the data onto the highlighted area of the Import File window **>
   Import**.
10. To publish the changes, select ![](../../../resources/images/icons/icon-options_23x20.png) > Publish > Publish.
11. To cancel the changes, select ![](../../../resources/images/icons/icon-options_23x20.png) > Revert > Revert.

The Cost Object Permissions reference data determines who can edit each Project, and who can
approve budget plan submissions.

## Manage Project Group reference data

The Project Group reference data represents the hierarchical project structure of your
organization. Project Groups are visible in the Plan Sub-Section menu and on the
Projects, Summary page.

1. In the navigation menu, select Configuration > Reference Data.
2. Select the Project tab on the Reference Data page
3. In the Project table, select Project Group.
4. Select ![](../../../resources/images/icons/icon-options_23x20.png) > Export.
5. In the Export file window, under Format options, you can change the format of the exported
   data.
6. Select Export. The reference data is exported as a .csv file.
7. Open the downloaded .csv file. Do not change the column headings or data structure of the file.
   Update the data table values as required:
   - Code - The unique identifier for the Project Group.
   - Name - The Project Group name.
   - Parent Code - Represents your Project Groups hierarchy. A Parent Code value is the code
     value of its immediate higher-level or parent account (if any).
   - Currency Code - The common currency for the Project Group. This value is required when
     support for multiple currencies is enabled in the Company Profile. The common currency value should
     be the three-letter ISO code for the currency. If no currency code is entered, the default common
     currency is used.
   - Price Group - Determines the price group for the project for Region-based or
     Tiered-pricing models.
   - Cost Center Code - The identifier for corresponding Cost Centers. When importing actuals,
     they are allocated per Cost Center, then mapped to a Cost Object. A project can be associated with
     multiple Cost Centers and can include line items (volumes, labor, or expenses) recorded for more
     than one Cost Center. Add multiple Cost Centers to the table cell using a comma to separate
     them.
8. Save the file in the .csv format. Now, select **Configuration > Reference Data > Project
   Group**.
9. Select ![](../../../resources/images/icons/icon-options_23x20.png) > Import. Drag and
   drop the file with the data onto the highlighted area of the Import File window **>
   Import**.
10. To publish the changes, select ![](../../../resources/images/icons/icon-options_23x20.png) > Publish > Publish.
11. To cancel the changes, select ![](../../../resources/images/icons/icon-options_23x20.png) > Revert > Revert.

## Manage Activity Types reference data

The Activity Types dimension is used by Labor Activity Planning. See [Early Access feature: Labor
activity planning](../labor-activity-planning.htm "(Opens in a new tab or window)"). This dimension is used to associate Allocation and Demand line items with
an Activity Type.

1. In the navigation menu, select Configuration > Reference Data.
2. Select the Standard Dimensions tab on the Reference Data page.
3. Select > Activity Types.
4. Select ![](../../../resources/images/icons/icon-options_23x20.png) > Export.
5. In the Export file window, under Format options, you can change the format of the exported
   data.
6. Select Export. The reference data is exported as a .csv file.
7. Open the downloaded .csv file. Do not change the column headings or data structure of the file.
   Update the data table values as required:
   - Name - Describes the nature of the work for the activity.
   - Is Capitalizable - Identifies the activity as a capitalizable activity.
   - Transfer In Account - The account code of the Project general ledger from which the
     activity’s cost is debited.
   - Transfer Out Account - The account code of the Department general ledger to which the activity’s
     cost is credited.
8. Save the file in the .csv format. Now, select **Configuration > Reference Data > Project
   Group**.
9. Select ![](../../../resources/images/icons/icon-options_23x20.png) > Import. Drag and
   drop the file with the data onto the highlighted area of the Import File window **>
   Import**.
10. To publish the changes, select ![](../../../resources/images/icons/icon-options_23x20.png) > Publish > Publish.

## Manage Department Labor Activity Rates reference data

The Department Labor Activity Rates dimension is used by Labor Activity Planning. See [Early Access feature: Labor
Activity Planning](../labor-activity-planning.htm "(Opens in a new tab or window)"). This dimension is used to set a labor rate for specific roles.

1. In the navigation menu, select Configuration > Reference Data .
2. Select the Standard Dimensions tab on the Reference Data page.
3. Select Department Labor Activity Rates.
4. Select ![](../../../resources/images/icons/icon-options_23x20.png) > Export.
5. In the Export file window, under Format options, you can change the format of the exported
   data.
6. Select Export. The reference data is exported as a .csv file.
7. Open the downloaded .csv file. Do not change the column headings or data structure of the file.
   Update the data table values as required:
   - Department - The unique identifier of the Department.
   - Cost Center - The identifier for corresponding Cost Centers.
   - Employee Type - An internal or external (such as vendors or contractors) labor
     resource.
   - Role - Available options for this dimension are provided by Roles reference data.
   - Currency - The common currency for labor activity allocation. Required when support for
     multiple currencies is enabled (see [Support for multiple currencies](../support-multiple-currencies.htm "(Opens in a new tab or window)")). The Department's common currency value
     should be the three-letter ISO code for the currency. If no currency code is entered, the default
     common currency is used.
   - Labor Rate - The default hourly compensation rate.
8. Save the file in the .csv format. Now, select **Configuration > Reference Data > Department
   Labor Activity Rates**.
9. Select ![](../../../resources/images/icons/icon-options_23x20.png) > Import. Drag and
   drop the file with the data onto the highlighted area of the Import File window **>
   Import**.
10. To publish the changes, select ![](../../../resources/images/icons/icon-options_23x20.png) > Publish > Publish

## Manage Project Labor Activity Rates reference data

The Project Labor Activity Rates dimension is used by Labor Activity Planning. See [Early Access feature: Labor
activity planning](../labor-activity-planning.htm "(Opens in a new tab or window)"). This dimension is used to set a labor rate for specific labor
activities.

1. In the navigation menu, select Configuration > Reference Data .
2. Select the Standard Dimensions tab on the Reference Data page
3. Select Project Labor Activity Rates.
4. Select ![](../../../resources/images/icons/icon-options_23x20.png) > Export.
5. In the Export file window, under Format options, you can change the format of the exported
   data.
6. Select Export. The reference data is exported as a .csv file.
7. Open the downloaded .csv file. Do not change the column headings or data structure of the file.
   Update the data table values as required:
   - Role - Available options for this dimension are provided by Roles reference
     data.
   - Vendor - Available options for this dimension are provided by Vendor reference
     data.
   - Currency - The common currency for labor activity allocation. Required when support for
     multiple currencies is enabled (see [Support for multiple currencies)](../support-multiple-currencies.htm "(Opens in a new tab or window)"). The Department's common currency value
     should be the three-letter ISO code for the currency. If no currency code is entered, the default
     common currency is used.
   - Labor Rate - The default hourly compensation rate.

     NOTE: Project labor activity rates are different from resources’ salary compensation. The
     activity rate you set applies to a resource assignment to an activity in a project (not to that
     specific resource’s base compensation). The two values can be (and likely will be) different.
8. Save the file in the .csv format. Now, select **Configuration > Reference Data > Project Labor
   Activity Rates**.
9. Select ![](../../../resources/images/icons/icon-options_23x20.png) > Import. Drag and
   drop the file with the data onto the highlighted area of the Import File window **>
   Import**.
10. To publish the changes, select ![](../../../resources/images/icons/icon-options_23x20.png) > Publish > Publish

See [Manage Score Configuration](score-manage.htm "(Opens in a new tab or window)")
for more information on managing score which is applicable to projects.
