---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Report overview - Tagging quality"
breadcrumb:
  - "Costing Standard"
  - "Report Walkthrough"
  - "Previous Version Layouts"
  - "Cloud Reports"
source_path: "cost-transparency/reports-v104/taggingquality.html"
images:
  - "resources/images/ct_images/8091_1.png"
  - "resources/images/ct_images/8091_10.png"
  - "resources/images/ct_images/8091_11.png"
  - "resources/images/ct_images/8091_12.png"
  - "resources/images/ct_images/8091_2.png"
  - "resources/images/ct_images/8091_3.png"
  - "resources/images/ct_images/8091_4.png"
  - "resources/images/ct_images/8091_5.png"
  - "resources/images/ct_images/8091_6.png"
  - "resources/images/ct_images/8091_7.png"
  - "resources/images/ct_images/8091_8.png"
  - "resources/images/ct_images/8091_9.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Report overview - Tagging quality

## Report overview - Tagging quality

Note: Applies to: Apptio Costing Standard or Apptio Cloud Cost Management running on TBM Studio
v12.3.3 or later.

The public cloud reporting in Apptio's Costing Standard includes a view into your cloud tagging
quality. Broadly, public cloud tagging quality helps you in these ways:

- Use the tagging quality reports to discover tag omissions and invalid values
- Locate the number of empty or invalid tags by consumers of cloud services
- Filter for specific consumers and export rows with blank or invalid values to send to those
  consumers

The tagging quality analytics are based on attributes in Apptio that are mapped from tags in the
cloud bill. Make sure to map the tags correctly in order to fully utilize this report.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8091_1.png)

## Completeness

- The **Completeness** tab allows the user to identify the number of records
  that have no values in specific fields.
- The chart at the top shows the count of blank records by the applicable field. This chart can
  also be manipulated to show any specific field and the number of blank records by month.
- The details table provides you with a more data-driven view and shows the specific column name
  and the number of fields in that column that are missing values.
- The last component of the tab is the actual data set itself. The user can use the
  **Show Blanks** slicers to manipulate the data and view the blank fields in
  relation to the data set.
- There are also pickers next to the **Show Additional Details** that allow the
  user to manipulate the data and view only specific columns if needed.![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8091_2.png)
- If you click **View** under the Tx column, you can see the **Tagging
  Quality Details** for the applicable line item.![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8091_3.png)

## Validity

- The **Validity** tab allows the user to identify the number of records that
  have invalid values in specific fields.
- The chart at the top shows the count of invalid records by the applicable field. This chart can
  also be manipulated to show any specific field and the number of invalid records by month.
- The details table gives you a more data-driven view and shows the specific column name and the
  number of fields in that column that are have invalid values.
- The last component of the tab is the actual data set itself. The user can use the
  **Show Invalid** slicers to manipulate the data and view the invalid fields in
  relation to the data set.
- There are also pickers next to the **Show Additional Details** that allow the
  user to manipulate the data and view only specific columns if needed.![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8091_4.png)
- If you click **View** under the Tx column, you can see the **Tagging
  Quality Details** for the applicable line item.![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8091_5.png)

## Configure Validity Report

While the **Completeness** tab will automatically indicate blank values in the
bill, the **Validity** tab needs to be configured with comparison data of the
expected values based on the tagging used. This is done by appending data into the **Cloud
Validity** table. This table is then used as a reference to determine which fields of the
cloud bill are valid values. You can configure this by doing the following:

- Go into **TBM Studio** and open the **Cloud Validity**
  table. Select the **Table** step and click **Export**, and
  then **Excel**.

  ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8091_6.png)
- Delete the **Valid** column from the spreadsheet. Use this spreadsheet as a
  template for your validity data. Populate the spreadsheet with the appropriate data, as it
  correlates to the fields in the bill (for example, put "Amazon Web Services, Inc.” in the Provider
  column, and fill in the remaining columns as they are mapped into Apptio from the cloud bill).

  ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8091_7.png)
- Once the data is filled in, save the spreadsheet.
- In Apptio, click **New**, and select **Table**. Type in
  the table name and category and click **OK**.![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8091_8.png)
- Select **File Upload**. Upload the spreadsheet that you created in Excel. This
  will be used as a reference for valid values. Once uploaded, if further configuration is needed, you
  can make changes on the **Import** step or add other steps (formula, filter,
  etc.) to configure as needed.

  ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8091_9.png)
- Select **Cloud Validity** again and click **Check Out**.
  Select the **Append** step. Append the table that you have just created and map
  the columns to **Cloud Validity** consistent with your bill’s tagging.

  ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8091_10.png)

  ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8091_11.png)
- Click **Check In** and check-in both documents.

  ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8091_12.png)

The **Cloud Validity** table will now be used to compare these fields with the
fields in the cloud bill. Any values that are inconsistent with this table will be noted as an
invalid value on the **Validity** tab of the **Tagging
Quality** report.
