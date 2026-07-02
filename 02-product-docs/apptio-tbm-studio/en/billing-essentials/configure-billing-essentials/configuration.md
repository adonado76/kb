---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "billing-essentials"
title: "Configuration"
breadcrumb: []
source_path: "billing-essentials/configure-billing-essentials/configuration.html"
images:
  - "resources/images/be/be-flowchrt.jpg"
  - "resources/images/be/be-s9.jpg"
  - "resources/images/be/billing-charge.jpg"
  - "resources/images/be/s7-sl.jpg"
  - "resources/images/studio_images/alloc-chrt.jpg"
  - "resources/images/studio_images/be-tu1.jpg"
  - "resources/images/studio_images/be-tu2.jpg"
  - "resources/images/studio_images/be-tu3.jpg"
  - "resources/images/studio_images/be-tu4.jpg"
  - "resources/images/studio_images/be-tu5.jpg"
  - "resources/images/studio_images/becomp-1.jpg"
  - "resources/images/studio_images/bes11.jpg"
  - "resources/images/studio_images/bes11chrg.jpg"
  - "resources/images/studio_images/bes11pc.jpg"
  - "resources/images/studio_images/bes11pu.jpg"
  - "resources/images/studio_images/bes9.jpg"
  - "resources/images/studio_images/besolution.jpg"
  - "resources/images/studio_images/cons-feed.jpg"
  - "resources/images/studio_images/df-chart.jpg"
  - "resources/images/studio_images/mc-be.jpg"
  - "resources/images/studio_images/s8.jpg"
  - "resources/images/studio_images/samp-ref.jpg"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configuration

1. (TBM Studio): Create a Project.
2. (TBM Studio): Billing Essentials supports Multi-currency. See [here](multi-currency.html)  for the configuration details.
3. (TBM Studio): Configure Time Settings and Check in the changes.
4. (TBM Studio): Install  **Billing- Charge**  component in the project. ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/be/billing-charge.jpg)
   ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/becomp-1.jpg)
5. (TBM Studio): Create two input tables to ensure relevant details are uploaded.
   - Table Name: Consumption Feed
   - Feed Table Name: Solution Library

     Sample for Reference:

     Name of the tables can be
     customer specific

     ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/samp-ref.jpg)
6. (TBM Studio): Save and Check in the changes.
7. (TBM Studio): These tables must be mapped to the Master/Feed tables as shown below

   Consumption Feed (Consumption Feed table)

   ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/cons-feed.jpg)

   Solution
   Library Feed (Solution Library table)

   ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/be/s7-sl.jpg)

   *\*\* If the source
   column to map is missing, ensure that the right data type for the column is specified in 'Type
   Override' section in 'Import' transform for the table*
8. (TBM Studio): Save and Check in the changes.

   Note:
   - If there are any changes, upload the input table on an adhoc/monthly basis to ensure the
     accuracy of the reports
   - Verify that ‘Billable’ formula highlighted below is present in the Solution Master to ensure
     that accurate data is populated in the reports

   ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/s8.jpg)

   Rate Management Report (‘Billing Charge- Reporting’ component should be installed)
9. (Report View): Navigate to Billing > Rate Management.

   Clear the filter from ‘Billable’ to
   reveal all Offerings. Use this table to edit the ‘Billable’ column to ‘Yes’ or ‘No’. Additionally,
   updates to the ‘Base Rate’ and ‘Rate Management’ column can be applied to set the Billable Rate if
   needed

   - **Base Rate**  - Initial rate established based on the unit cost from Costing Essentials
   - **Rate Adjustment**  - Enter a positive or negative number to calculate and adjust the Billable
     Rate (Billable Rate = Base Rate + Rate Adjustment), calculated via the ET script
   - **Rate Adj Impact**  - Used to clearly identify the charge vs cost recovery as a result of the
     Rate Adjustment

   Select  **Save**  and then  **Publish**  to propagate to all reports and models,
   “Solution Library ET Transform”

   ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/be/be-s9.jpg)

   ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/bes9.jpg)

   \*\* Once published, ensure that 'Billable' filter is set to 'Yes' to see the Charge value in
   the report.
10. (TBM Studio): Navigate to Tables > Solution Library ET Transform and
    review the data post Publish in Step 10. Additionally, a recurring publish can be set for
    this table. For more information, see  [Recurring publish of transform table](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=administration-recurring-publish-transform-table "(Opens in a new tab or window)")  .
11. (TBM Studio): Open Consumption Model and verify the allocations

    Billable Units

    ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/bes11.jpg)

    *\*\* This screenshot is for reference as the cost allocations will vary based on the data.*

    **Charge**

    ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/bes11chrg.jpg)

    *\*\* This screenshot is for reference as the cost allocations will vary based on the data.*

    Plan Charge

    ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/bes11pc.jpg)

    *\*\* This screenshot is for reference as the cost allocations will vary based on the data.*

    Plan Units

    ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/bes11pu.jpg)

    *\*\* This screenshot is for reference as the cost allocations will vary based on the data.*

    Also, verify the allocations in  **Solutions**  model for the above-mentioned metrics

    ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/besolution.jpg)

    *\*\* This screenshot is for reference as the cost allocations will vary based on the data.*

    Data Flow Chart

    ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/df-chart.jpg)

    Allocation Chart

    ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/alloc-chrt.jpg)

    ![img1](../../../../../03-media/apptio-tbm-studio/resources/images/be/be-flowchrt.jpg)

**Multi-Currency**

If customer uses Multi-currency this would be a good time to set that up. Multi-currency is the
same in Costing Essentials as in CT projects. You can reference the Multi-currency configuration in
Help Center.

However, if your customer uses a non-Gregorian calendar, the newer version of MCC doesn’t
support non-Gregorian. If your customer requires a non-Gregorian Calendar, follow the Legacy
Multi-currency configuration here.

Select the preferred  **Base Currency**  .

![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/mc-be.jpg)

**Table Upload**

The  **Table Upload**  component allows end users with appropriate permissions to directly
 **upload**  data from spreadsheets into tables without the need for TBM Studio access. Table
Uploads report consists of two tabs: Table Upload and Table Upload Access.

**Table Uploads tab**

Table Uploads tab will help the users directly upload data into the Consumption/General Ledger,
Budget and Labor without the need for TBM Studio access.

Navigate to Workbench > Table Uploads > Table Upload as shown:

![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/be-tu1.jpg)

The table upload component offers two configuration options -  [Simple configuration](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=reports-table-upload-component#TableUploadcomponent__Simpleconfiguration__title__1 "(Opens in a new tab or window)")  &  [Advanced configuration](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=reports-table-upload-component#TableUploadcomponent__Advancedconfiguration__title__1 "(Opens in a new tab or window)")  . In this example, it is
equipped with Advanced Configuration, allowing user matching in the Table Upload Access tab.

![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/be-tu2.jpg)

**Table Upload Access tab**

Table Uploads Access tab will help the admins manage access to who can directly upload data into
the Consumption/General Ledger, Budget and Labor without the need for TBM Studio access.

Navigate to Workbench > Table Uploads > Table Upload > Table Upload Access as shown:

![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/be-tu3.jpg)

Grant table upload access by specifying the table name and the corresponding user details to
allow them to upload data into the designated table as shown below.

![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/be-tu4.jpg)

![img1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/be-tu5.jpg)

*\*\* Tab visibility can be customized based on the customer's requirements to control which user
roles have access to the "Table Upload Access" tab in the Table Upload report.*

For more information, see  [Table Upload](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=reports-table-upload-component "(Opens in a new tab or window)")  .
