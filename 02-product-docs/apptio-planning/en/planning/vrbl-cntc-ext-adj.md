---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Variable Contract Extension Adjustment"
breadcrumb: []
source_path: "planning/vrbl-cntc-ext-adj.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Variable Contract Extension Adjustment

Note: This feature is available only in Expenses > New View. To learn more about Expenses >
New View please visit <link>

## Variable Contract Extension Adjustment

NOTICE: This feature is available only in Expenses > New View. To learn more about
Expenses > New View please visit <link>

![](../../resources/images/it_planning_images/3.84-newfeature.jpg)

1. Navigate to Expenses > Contract in the Expenses New View
2. Enter a contract line with all the details. To learn more about Adding a contract line please
   visit < link to Manage Contracts page>
3. To extend the contract select the Extend checkbox. The Extend button in the
   Extension Setting column is be enabled.
4. Select the Extend button.
5. The Configure Extension dialog is displayed with metadata of the contract.
6. The Extend Until field indicates the date up to which the contract will be extended. By
   default, it is set to plan end date.
7. The Disable Compounding field indicates whether extension adjustment is compounded or
   not. By default, it is set to non-compounding adjustment. Enable the toggle to apply compounding
   extension adjustment.
8. Enter the percentage adjustment value in Extension Adjustment
9. Select Apply to calculate all the extensions up to extend until date and apply the
   adjustments.
10. Contract Extensions generates the table with Start Date, End Date, Adjustment Percentage
    and Comments for each extension.
11. Edit adjustment percentages for each extension in the Adjustments field.
    - If Compounding extension is disabled, the Extension Adjustment is applied only for the first
      extension adjustment.
    - If Compounding extension is enabled, Extension Adjustment is applied to all the extensions.
12. In the Comments field, enter the comments, if any to describe or justify the adjustment
    percentage.
13. Select Submit to save the changes.
14. Select Cancel to discard the changes.

## Expenses Legacy View

Expenses Legacy view will highlight the editable cells of any contract lines created with
compounding extension adjustments. Mouse hovering on the editable cells will show a message
indicating the contract line is created with compounding contract extensions so user should switch
to the Expenses > New View to make any changes.

Note: If user makes any edits to the lines having compounding contract extensions (i.e. the lines
highlighted in yellow) the line will be updated to non-compounding extension adjustment, this is
because the feature is supported only in the Expenses > New View.

![](../../resources/images/it_planning_images/exp-leg-voew.jpg)

## Contract Data Import and Export from Expenses > Legacy View

- Import and Export of Contract data with variable extension adjustments is supported only from
  the Expenses > New View.
- Exporting Contract data from the Expenses > Legacy view will export the Adjustment Percentage
  only for the first extension adjustment.
- Importing the contract data in the Expenses > Legacy View will result in updating the
  compounding extensions to non-compounding extension adjustment with first extension adjustment
  percentage. Users will be warned about it after the data upload analysis.

  ![](../../resources/images/it_planning_images/imp-exp.jpg)
- Select Export Help File for more details.
- Lines with compounding extensions will be tagged in the exported help file, as shown in the
  reference screenshot below.

  ![](../../resources/images/it_planning_images/imp-exp-1.jpg)

## Contract Data Import and Export from Expenses > New View

Export Contracts

1. Navigate to Expenses > New View and Contracts tab. Open menu, select
   Export contracts... and then select Export All option
2. Two .csv files are exported.
3. File with \_Contact.csv suffix contains contract data.
4. File with \_Contract-Extensions.csv suffix contains extension data.

Import Contracts

1. Contract Details and Extension Details should be imported separately from Expenses >
   New View.
2. Navigate to Expenses > New View and Contracts tab. Open menu > Import contracts... , and
   then select Contract Details from the sub menu.
3. From the Import File dialog, select Replace All or Update Data option.
4. Select Import.
5. Selecting the Replace All import option will delete all existing contracts and the
   corresponding extensions. User must upload extension data separately.
6. Selecting the Update Data import option will update existing contract details for
   matching Line Item Code or External Code (if applicable) from imported file. User must upload
   extension data separately to make any updates.
7. The above steps still update only the contract details. The extension details must be updated
   separately using the mentioned steps.
8. Navigate to Expenses > New View and Contracts tab. Open menu > Import contracts... , and
   then select Extension Details from the submenu.
9. From the Import File dialog, select Replace All or Update Data option.
10. Select Import

## Extension Details File Format

- Provide Contract line details including line item code and other metadata as shown in the
  screenshot below.
- Each extension line is uniquely identified by Line Item Code that refers to the
  corresponding Contract and Extension Number that corresponds to the extension in sequence
  from contract start date to extend until date.
- Extension Number should be in sequence starting with 1 representing the first extension,
  2 representing the second extension and so on.
- Providing Extension Start Date is not mandatory, it will be calculated automatically
  during upload.
- Set Enable Compounding = TRUE if you want to make a compounding extension
  adjustment.
- Adjustment value for each extension will be accepted only if Compounding = TRUE
  otherwise only one adjustment value is applicable for non-compounding extensions.
- Provide Contract Extend Until date, it should be same for all extensions for the same
  contract.
- Provide Adjustment Percentage in decimal for each extension.
- Extension Comment column is used to enter any comments for each extension.

![](../../resources/images/it_planning_images/extfformat-1.jpg)

![](../../resources/images/it_planning_images/extfformat-2.jpg)

## Variable Contract Extensions for External Contracts

We have expanded the Variable Contract Extension Adjustments feature to support External
Contracts. With this enhancement you can set up compounding contract extension adjustments for
External Contracts as well as define unique adjustment percentages for each contract extension.

External Contracts, are those that are planned in external systems and shouldn’t be modified in
the Apptio Planning, but are required to be captured for the budgeting process. Only administrator
can import these contracts via a .csv file upload as read only data in Planning.

To upload the external contracts use Import External Contract option in the Expenses Table. Same
as non-external contracts, you need to upload a .csv file for contract details and extension
details.

![](../../resources/images/it_planning_images/3.86-pln.jpg)
