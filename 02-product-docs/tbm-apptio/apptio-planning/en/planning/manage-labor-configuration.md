---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Labor Configuration reference data"
breadcrumb: []
source_path: "planning/manage-labor-configuration.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Labor Configuration reference data

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
Data: Labor Dimensions](https://community.apptio.com/videos/1993 "(Opens in a new tab or window)").

Or see all [Apptio planning video and training resources](https://community.apptio.com/viewdocument/apptio-products-video-catalog?CommunityKey=1bdb1f0b-9524-43d4-b987-5d2b8595eebf "(Opens in a new tab or window)").

## Manage External or Internal Labor Pools in reference data

◆ Applies to: Apptio planning applications with Project Financial Planning (see [Get started with the Project
Financial Planning module](pfp/gs-project-financial.dita "(Opens in a new tab or window)")) or Service Demand Planning (see [Get started with the Service Demand
Planning module](sdp/gs-service-demand.dita "(Opens in a new tab or window)"))

Tasks in this section require you to license Project Financial Planning or Service Demand
Planning, then edit the Company Profile to enable Project Financial Planning or Service Demand
Planning. See [Edit the Company
Profile](edit-company-profile.dita "(Opens in a new tab or window)").

Define external labor pools to capture the direct external labor cost for your project or
service. Note that before you configure external labor pools, first update your department's
dimensions.

1. In the Company Profile, enable labor planning and, if licensed, Project Financial Planning or
   Service Demand Planning (see [Edit the Company Profile](edit-company-profile.dita "(Opens in a new tab or window)")).
2. In the left navigation menu, select Configuration > Reference Data > External Labor Pool
   or Internal Labor Pool.
3. Select ![](../../resources/images/icons/3-dots.png) in the top right corner of the
   table, select Export > Export All.
4. Open the downloaded .csv file and update the data values as required:
   - Code (required) - The abbreviated unique identifier of the labor pool.
   - Name (required) - The labor pool name.
   - Department Code (Internal Labor Pool only) - The department associated with the Internal
     Labor Pool.
   - Category - Use this column to expand on the type of labor pool. Examples of categories
     include Development, Quality Assurance, and Project Management.
   - Rate - The hourly rate of an individual in the labor pool.
   - Vendor (External Labor Pool only) - The vendor associated with the labor pool.
   - Default Pool (Internal Labor Pool only) - The labor pool to use for direct allocations by
     department. You can only select one labor pool per department.
   - Currency Code - The common currency for the labor pool. Required when the support for
     multiple currencies is enabled in the Company Profile. The department's common currency value should
     be the three-letter ISO code for the currency. If no currency code is entered, the default common
     currency is used.
5. Now, Configuration > External Labor Pool or Internal Labor Pool and then import the
   updated .csv file.

## Manage Labor Rates reference data

A Budget Process Owner or Admin can set up labor rates for both internal and external labor
resources. These labor rates can be tied to Role, Location, and Vendor dimensions.

Labor rates provide the default labor card values, such as annual compensation per labor role.
These default values are applied to specific workers and can be directly customized per worker. See
[Create a labor plan](create-labor-plan.dita "(Opens in a new tab or window)"). Labor
rates for internal labor resources will likely come from your human resources system. For external
labor resources, such as vendors, the vendor should provide their role-based labor card data in a
format you can use.

1. Enable labor planning features (see [Edit the Company Profile](edit-company-profile.dita "(Opens in a new tab or window)")).
2. In the left navigation menu, select Configuration > Reference Data > Labor Rates.
3. Select ![](../../resources/images/icons/3-dots.png) in the top right corner of the
   table, select Export > Export All.
4. Open the downloaded .csv file and update the data values as required:
   - Employee Type - Determines whether this rule applies to internal or external (such as
     vendors or contractors) labor resources.
   - Role - Available options for this dimension are provided by Roles reference
     data.
   - Location - Available options for this dimension are provided by Location reference
     data.
   - Vendor - Available options for this dimension are provided by Vendor reference
     data.
   - Currency Code - The common currency for the labor allocation. Required when support for
     multiple currencies is enabled. The department's common currency value should be the three-letter
     ISO code for the currency. If no currency code is entered, the default common currency is used.
   - Base Rate - The default labor compensation rate.
5. Now, Configuration > Reference Data > Labor Rates, and then select ![](../../resources/images/icons/3-dots.png) in the top right corner of the table. Now select
   Import and import the updated .csv file.
6. Select ![](../../resources/images/icons/3-dots.png) and select Publish to make
   the labor rates available in planning and spend management. After publishing labor rates, you can
   account for planned adjustments to these rates for specific labor resources (see [Manage custom
   dimensions](manage-custom-reference.dita "(Opens in a new tab or window)")).

## Manage Roles reference data

Roles are descriptive titles to apply to labor resources. The Role values you assign to labor
resources are the key look-up values in labor rate tables.

1. Enable labor planning features (see [Edit the Company Profile](edit-company-profile.dita "(Opens in a new tab or window)")).
2. In the left navigation menu, select Configuration > Reference Data > Role.
3. The Role reference data table includes the name for the resource role. You cannot directly edit
   values in the Roles table. Instead, select ![](../../resources/images/icons/3-dots.png)
   in the top right corner of the table, select Export > Export All. Open the downloaded .csv
   file and update the roles data, and upload and publish the .csv file as needed.
