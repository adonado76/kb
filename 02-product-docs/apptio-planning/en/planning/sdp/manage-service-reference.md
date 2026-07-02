---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Service reference data"
breadcrumb: []
source_path: "planning/sdp/manage-service-reference.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Service reference data

◆ Applies to: Planning with [Service Demand Planning](gs-service-demand.htm "(Opens in a new tab or window)"). The tasks below require you to license Service Demand Planning then
[edit the Company
Profile](../edit-company-profile.htm "(Opens in a new tab or window)") to enable Service Demand Planning features. The tasks below can only be performed by
users assigned to the Admin or Budget Process Owner roles. For additional information on roles, see
Frontdoor permissions and roles.

NOTE: The Service Demand Planning module is no longer available from Apptio. The
information below is provided for the benefit of current users of Service Demand Planning.

Dimensions are the essential data categories in budget line items. Many built-in dimensions have
dependencies on other dimensions (see [Reference data attribute and dimensions dependencies](../manage-reference-data.html#dimensiondepend) for more information). You
can import dimensions reference data from a .csv file or from Costing Standard and export dimensions
reference data templates and table data (see [Manage dimensions](../manage-reference-data.html "(Opens in a new tab or window)")).

![](../../../resources/images/it%20planning_images/icon_video.png): Watch this video
from Apptio Education Services: [Configuring Reference Data: Service Demand Planning Dimensions](https://community.apptio.com/videos/1996 "(Opens in a new tab or window)"). Or see all
[Apptio planning video and training resources](https://community.apptio.com/viewdocument/apptio-products-video-catalog?CommunityKey=1bdb1f0b-9524-43d4-b987-5d2b8595eebf "(Opens in a new tab or window)").

## Manage Business Unit reference data

Service Owners can use Business Units to help forecast service demand to additional areas within
their organization. Before configuring Business Units reference data, ensure that you publish the
Unit of Measure, Service categories, and Services dimensions (directions
follow).

1. In the navigation menu, select Configuration > Reference Data.
2. Select the Service tab on the Reference Data page.
3. Select > Business Unit.
4. Select ![](../../../resources/images/icons/3-dots.png) > Export.
5. In the Export file window, under Format options, you can change the format of the
   exported data.
6. Select Export. The reference data is exported as a .csv file.
7. Open the downloaded .csv file. Do not change the column headings or data structure of the file.
   Update the data table values as required:
   - Code (required) - The abbreviated unique identifier for the Business Unit.
   - Name (required) - The Business Unit name.
   - Parent Code - Represents your Business Unit hierarchy. A Parent Code value is the code
     value of its immediate higher-level or parent Business Unit (if any).
   - Cost Center Code - The identifier for corresponding Cost Centers. When importing actuals,
     they are allocated per Cost Center, then mapped to a Cost Object. A Business Unit can be associated
     with multiple Cost Centers and can include line items (volumes, labor, or expenses) recorded for
     more than one Cost Center. Add multiple Cost Centers to the table cell using a comma to separate
     them.
   - Currency Code - The common currency for the Business Unit. Required when support for
     multiple currencies is enabled. The Business Unit's common currency value should be the three letter
     ISO code for the currency. If no currency code is entered, the default common currency is used.
   - Price Group - Determines the price group for the Business Unit for Region-based or
     Tiered-pricing models.
   - Unit Price - Defines the amount to charge when a unit of a Business Unit is used.
8. Save the file in the .csv format. Now, select **Configuration > Reference Data > Service tab >
   Business Unit**.
9. Select ![](../../../resources/images/icons/3-dots.png)> Import. Drag and drop
   the file with the data onto the highlighted area of the Import File window >
   Import.
10. To publish the changes, select ![](../../../resources/images/icons/3-dots.png)**>
    Publish > Publish**.
11. To cancel the changes, select ![](../../../resources/images/icons/3-dots.png)**>
    Revert > Revert**.

## Manage Price Group reference data

The Price Group dimension allows the Admin to set up Regional- or Tiered-pricing models for their
Service Owners. The Price Group maps to the provider and consumers, which helps categorize custom
service prices for regions or consumers. Before configuring Price Group reference data, ensure that
you update the pricing strategy.

1. In the navigation menu, select Configuration > Reference Data.
2. Select the Service tab on the Reference Data page.
3. Select > Price Group. The Price Group reference data table includes the name of the
   consumer or provider region or group to which you want to apply a specific price. Regional pricing
   model names are abbreviated as AU, EU, and US. Tiered-pricing model names are External and Internal.
   You can omit the value used for the Base Price label in the Company Profile
4. Select ![](../../../resources/images/icons/3-dots.png) > Export.
5. In the Export file window, under Format options, you can change the format of the
   exported data.
6. Select Export. The reference data is exported as a .csv file.
7. Open the downloaded .csv file. Do not change the column headings or data structure of the file.
   Update relevant Departments, Projects, Business Units, or Services with the Price Group.
8. Save the file in the .csv format. Now, select **Configuration > Reference Data > Service tab >
   Price Group**.
9. Select ![](../../../resources/images/icons/3-dots.png)> Import. Drag and drop
   the file with the data onto the highlighted area of the Import File window >
   Import.
10. To publish the changes, select ![](../../../resources/images/icons/3-dots.png)**>
    Publish > Publish**.
11. To cancel the changes, select ![](../../../resources/images/icons/3-dots.png)**>
    Revert > Revert**.

## Manage Unit of Measure in reference data

Unit of Measure reference data determines how volumes of Services are measured. Before you define
Services, first define their Unit of Measure.

1. In the navigation menu, select Configuration > Reference Data.
2. Select the Service tab on the Reference Data page.
3. Select > Unit of Measure.
4. Select ![](../../../resources/images/icons/3-dots.png) > Export.
5. In the Export file window, under Format options, you can change the format of the
   exported data.
6. Select Export. The reference data is exported as a .csv file.
7. Open the downloaded .csv file. Do not change the column headings or data structure of the file.
   Update the data table values as required:
   - Code (required) - The abbreviated unique identifier for the Business Unit.
   - Name (required) - The Business Unit name.
8. Save the file in the .csv format. Now, select **Configuration > Reference Data > Service tab >
   Unit of Measure**.
9. Select ![](../../../resources/images/icons/3-dots.png)> Import. Drag and drop
   the file with the data onto the highlighted area of the Import File window >
   Import.
10. To publish the changes, select ![](../../../resources/images/icons/3-dots.png)**>
    Publish > Publish**.
11. To cancel the changes, select ![](../../../resources/images/icons/3-dots.png)**>
    Revert > Revert**.

## Manage Service reference data

Services, Departments, and Projects are types of Cost Objects.

1. Update the Unit of Measure reference data to include the Code for the Service reference data
   table. See the previous section: "Manage Unit of Measure reference data."
2. In the navigation menu, select Configuration > Reference Data.
3. Select the Service tab on the Reference Data page.
4. Select > Service.
5. Select ![](../../../resources/images/icons/3-dots.png) > Export.
6. In the Export file window, under Format options, you can change the format of the
   exported data.
7. Select Export. The reference data is exported as a .csv file.
8. Open the downloaded .csv file. Do not change the column headings or data structure of the file.
   Update the data table values as required:
   - Code (required) - The unique value for the Service.
   - Name (required) - The service's name.
   - Parent Code - Represents your services' hierarchy. A Parent Code value is the code value
     of its immediate higher-level or parent account (if any). Services listed with a Parent Code value
     of SC CNC, SC LOB, or SC CC are subordinate to the Client Computing, Line of Business, and
     Communication & Collaboration services.
   - Currency Code - The common currency for the service. Required when support for multiple
     currencies is enabled. The common currency value should be the three-letter ISO code for the
     currency. If no currency code is entered, the default common currency is used.
   - Price Group - Determines the price group for the service for Region-based or
     Tiered-pricing models. Leave blank to use the original price.
   - Pricing Strategy - The method used to price your service. Options include:
     - Fixed - An amount to charge (defined using the Unit Price column). This option is
       required if you selected Fixed as the pricing model in the Company Profile.
     - Dynamic - Dynamically calculate the Unit Price based on service cost composition and
       demand. Only use this option if you selected Dynamic as the pricing model in the Company Profile.
   - Unit Code - The unique identifier of the item to quantify for this service.
   - Unit Price - The amount to charge for a unit of service.
   - Cost Center Code - The identifier for corresponding Cost Centers. When importing actuals,
     they are allocated per Cost Center, then mapped to a Cost Object. A project can be associated with
     multiple Cost Centers and can include line items (volumes, labor, or expenses) recorded for more
     than one Cost Center. Add multiple Cost Centers to the table cell using a comma to separate
     them.
9. Save the file in the .csv format. Now, select **Configuration > Reference Data > Service tab >
   Service**.
10. Select ![](../../../resources/images/icons/3-dots.png)> Import. Drag and drop
    the file with the data onto the highlighted area of the Import File window >
    Import.
11. To publish the changes, select ![](../../../resources/images/icons/3-dots.png)**>
    Publish > Publish**.
12. To cancel the changes, select ![](../../../resources/images/icons/3-dots.png)**>
    Revert > Revert**.

## Manage Service Categories reference data

Service Categories reference data represents the hierarchical service structure of your
organization. Service Categories are visible in the Plan Sub-Section menu and on the
Services, Summary page.

1. In the navigation menu, select Configuration > Reference Data.
2. Select the Service tab on the Reference Data page.
3. Select > Service Categories.
4. Select ![](../../../resources/images/icons/3-dots.png) > Export.
5. In the Export file window, under Format options, you can change the format of the
   exported data.
6. Select Export. The reference data is exported as a .csv file.
7. Open the downloaded .csv file. Do not change the column headings or data structure of the file.
   Update the data table values as required:
   - Code (required) - The unique value for the Service Category.
   - Name (required) - The service category's name.
   - Parent Code - Represents your Service Categories hierarchy. A Parent Code value is the
     code value of its immediate higher-level or parent account (if any). Services Categories with a
     Parent Code value of SCPS and SCEUCS are subordinate to those service categories.
   - Currency Code - The common currency for the service. Required when support for multiple
     currencies is enabled. The common currency value should be the three-letter ISO code for the
     currency. If no currency code is entered, the default common currency is used.
   - Price Group - Determines the price group for the service for Region-based or
     Tiered-pricing models. Leave blank to use the original price.
   - Cost Center Code - The identifier for corresponding Cost Centers. When importing actuals,
     they are allocated per Cost Center, then mapped to a Cost Object. A project can be associated with
     multiple Cost Centers and can include line items (volumes, labor, or expenses) recorded for more
     than one Cost Center. Add multiple Cost Centers to the table cell using a comma to separate
     them.
8. Save the file in the .csv format. Now, select **Configuration > Reference Data > Service tab >
   Service Categories**.
9. Select ![](../../../resources/images/icons/3-dots.png)> Import. Drag and drop
   the file with the data onto the highlighted area of the Import File window >
   Import.
10. To publish the changes, select ![](../../../resources/images/icons/3-dots.png)**>
    Publish > Publish**.
11. To cancel the changes, select ![](../../../resources/images/icons/3-dots.png)**>
    Revert > Revert**.

## Manage Service Price Adjustments reference data

Service Price Adjustments reference data allows you to set pricing rules for Regional- or
Tiered-pricing models.

1. In the navigation menu, select Configuration > Reference Data.
2. Select the Service tab on the Reference Data page.
3. Select > Service Price Adjustments.
4. Select ![](../../../resources/images/icons/3-dots.png) > Export.
5. In the Export file window, under Format options, you can change the format of the
   exported data.
6. Select Export. The reference data is exported as a .csv file.
7. Open the downloaded .csv file. Do not change the column headings or data structure of the file.
   Update the data table values as required:
   - Consumer Price Group - Appears for tiered categories of a service, such as Internal or
     External.
   - Currency - The common currency for the service. Required when support for multiple
     currencies is enabled. The common currency value should be the three-letter ISO code for the
     currency. If no currency code is entered, the default common currency is used.
   - Provider Price Group - Determines the price group for the Service Provider.
   - Adjustment Amount - The price or percentage amount to adjust the base amount. To provide
     discounts, enter a negative number. For example, a value of -20 is equal to a $20 or 20% discount
     (depending on the Adjustment Type selected) on the unit of service.
   - Adjustment Type - Determines how adjustments are applied. The following options are
     available:
     - Absolute - A flat monetary rate to apply to the base unit price.
     - Percentage - A percent change to the unit price rate.
     - Amount - Used for Tiered pricing only. This is a flat monetary rate to apply to the base
       unit price.
8. Save the file in the .csv format. Now, select **Configuration > Reference Data > Service tab >
   Service Price Adjustments**.
9. Select ![](../../../resources/images/icons/3-dots.png)> Import. Drag and drop
   the file with the data onto the highlighted area of the Import File window >
   Import.
10. To publish the changes, select ![](../../../resources/images/icons/3-dots.png)**>
    Publish > Publish**.
11. To cancel the changes, select ![](../../../resources/images/icons/3-dots.png)**>
    Revert > Revert**.

TIP: Cost Object Permissions reference data determines who can edit each service, and who
can approve budget plan submissions. See [Manage Cost Object Permissions reference data](../manage-cost-object.htm "(Opens in a new tab or window)").
