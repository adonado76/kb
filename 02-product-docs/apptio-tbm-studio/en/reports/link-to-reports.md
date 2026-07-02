---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Link to reports"
breadcrumb: []
source_path: "reports/link-to-reports.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Link to reports

Applies to: TBM Studio 12.1 and later

You can give users viewing a report the option of selecting a value in a table or selecting an
entire chart and displaying a related report. Each column in a table can link to a different report.
A chart can only link to a single report. The navigation properties are shown in the following
image. In tables, links are displayed as blue text.

![](../../resources/images/studio_images/studioimages/studio/stu632.png)

You can link to reports anywhere within a project, including child reports. However, the best
practice is to create all the reports as top-level reports.

Note: Report links only apply to object-based tables. You cannot link to reports from transform
tables.

## Access the navigation properties

To edit navigation properties:

1. Select a column in a table or select an entire chart.
2. Select the Ad Hoc tab and click Drill in the Navigation section.

## Field descriptions

The navigation fields are described in the table below. You can select more than one of the
Context Includes options.

|  |  |
| --- | --- |
| Field | Description |
| Enable Navigation | Makes the unit names in a table or the bars or slices in a chart active as links for navigation. If the option is not selected, links will not be active for the column.NOTE: In charts, navigation must be keyed to the value column, not the label column. |
| Open as Modal | When selected, the drill-to report will be displayed as a pop-up. The user can view the report and then click the close button to return to the original report. The target report should be kept simple. Do not include complex filters or columns pickers. |
| Navigate To: | Select the name of a report that will be the destination for the links. The report can be any of the reports in the project. Also, you can create a new report by clicking New Report. The New Report dialog is displayed where you can define the new report. |
| Filter on selected row | Filters the target report by the value selected by the user. The options determine what combination of rows are used for the filter. Rows refers to the entries in the Rows section (or Legend section for charts) of the Ad Hoc Query Configuration dialog. For this option to work, the data in the two reports must be linked through the inference engine. If this option and the other options are not selected, the target report will display all rows.**Filter on all Rows columns.** Filters using the values in all the columns included in the Rows section of the Ad Hoc Query Configuration dialog.Filter only on Grouped columns. Filters using the values in all the grouped columns included in the Rows section of the **Ad Hoc Query Configuration** dialog.Filter only on currently selected column. Filters using only the column containing the value selected by the user. |
| Filter on applied slicer selections | Filter the target report by the values selected in the slicers. If this option and the other options are not selected, the target report will display all rows. |
| Include current report's filters | Includes the filters defined in the Filters section of the **Ad Hoc Query Configuration** dialog. If this option and the other options are not selected, the target report will display all rows. |
| Add currentlyselected column | If the selected column does not exist in the target report, the column will be added to the target report. |
| Include current report's added columns | Retains the context of the current report and applies it to the target report. If the current report includes added columns, the columns will be added to the target report. |

## Navigation examples

Assume you have the following three tables in three separate reports:

|  |  |  |
| --- | --- | --- |
| Report A | Report B | Report C |

**Example 1: Select a value in the Business Unit Costs table in Report A and link to Report B.
Display all values in Report B.**

The intended result is shown below:

|  |  |  |
| --- | --- | --- |
| Report A | ---> | Report B |

To get this result, select the Business Unit column in the Business Unit Costs
table in Report A and set the navigation options as shown below:

![](../../resources/images/studio_images/studioimages/reports/rep257.png)

**Example 2: Select a value in the Business Unit Costs table on Report A and display the
Business Unit FTEs table on Report B. Display only the row selected.**

The intended result is shown below:

|  |  |  |
| --- | --- | --- |
| Report A | ---> | Report B |

To get this result, select the Business Unit column in the Business Unit Costs
table in Report A and set the navigation options as shown below:

![](../../resources/images/studio_images/studioimages/studio_link%20to%20reports_example%201.png)

**Example 3: Select a value in the Cost column of the Business Unit Costs table in Report A and
display Report B with the Cost column added to Business Unit FTEs table.**

The intended result is shown below:

|  |  |  |
| --- | --- | --- |
| Report A | ---> | Report B |

To get this result, select the Cost column in the Business Unit Costs table in
Report A and set the navigation options as shown in the following image:

![](../../resources/images/studio_images/studioimages/reports/rep262.png)

**Example 4: Select a value in the Business Unit column of the Business Unit Costs table in
Report A and display Report B with only the selected business unit data displayed. Select the
business unit displayed in Report B and display the Business Unit Cost Centers table in Report C
with all the business units displayed.**

The intended result is shown in the following images:

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| Report A | ---> | Report B | ---> | Report C |

To get this result:

1. Select the Cost column in the Business Unit Costs table in Report A and set the
   navigation options as shown below:

   ![](../../resources/images/studio_images/studioimages/studio_reports_options.png)
2. Select the Business Unit column in the Business Unit FTEs table in Report B and
   set the navigation options as shown in the following image:

   ![](../../resources/images/studio_images/studioimages/studio_business%20unit%20costs%20table_result.png)
