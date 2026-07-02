---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Navigation Component Types"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Navigation"
source_path: "studio/new-uc/reference/report-studio-reference/navigation-component-types.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Navigation Component Types

**Button Component**

The Button component provides explicit navigation controls within reports. Use buttons to
navigate to specific reports, change the displayed time period, trigger scripts, or provide back
navigation. Buttons offer the most visible and user-friendly navigation option.

**Adding a Button**

1. From the Report tab, click the Button icon
2. The button component is added to the report inside a standard component panel
3. Position and resize the button as needed
4. Configure appearance and actions through the Properties dialog

**Button Appearance Properties**

|  |  |
| --- | --- |
| **Property** | **Description** |
| Button Text | Text displayed on the button. Supports static labels and dynamic text using the <%=...%> syntax. Can include HTML code to reference images from the Apptio image library. |
|  |  |
| Button Tooltip | Text displayed when users hover over the button. Use tooltips to provide additional context about the button's action. |
| Enabled | Controls button state: leave blank for active, enter "disabled" for grayed out, or "hidden" to hide. Use formulas for conditional states, e.g., <%=IF(Cost>5000,"enabled","disabled")%> |
| Button Color | Sets the background color of the button |
| Button Text Color | Sets the color of the button text |
| Text Size | Controls the size of the button and its text. Can also resize by dragging the panel border. |
| Button Growth | Auto: default size. Horizontal: lengthens button to fit the surrounding panel. |
| Panel Background Color | Sets the color of the panel surrounding the button |

**Button Action Properties**

Configure button actions through the Actions tab in the Properties dialog:

|  |  |
| --- | --- |
| **Property** | **Description** |
| Server Action | ApptioScript code executed when the button is clicked. Runs before Change Date and Navigate actions. This is an advanced feature. |
| Change Date | Changes the displayed time period. Select from the dropdown or enter a custom date in period:year format (e.g., January:FY2012, P3:FY2012). |
| Navigate | Enter a link using Wiki-style syntax to navigate to another report. See the Coded Links section for syntax details. |
| Back Button | When selected, clicking the button returns the user to the previous report. This provides an alternative to breadcrumb navigation. Overrides Server Action, Change Date, and Navigate settings. |
| Submit Form | If the button is placed in a form component, clicking it submits the form. |

**Performance Note:** Be careful when creating buttons that navigate to reports requiring
significant calculation. Navigation to complex reports can impact system performance.

**Report Links (Drill-Through)**

Report links enable users to navigate from a selected value in a table or an element in a chart
to a related report. This drill-through functionality is fundamental to creating interactive,
explorable reports. Links in tables appear as blue text.

**Important:** Report links only apply to object-based tables created with the Ad Hoc
Component Configuration dialog. You cannot add report links to transform tables or legacy tables and
charts.

**Configuring Report Links**

1. Select a column in a table or select an entire chart
2. Select the Ad Hoc tab and click Drill in the Navigation section
3. Configure the navigation properties in the dialog

**Navigation Properties Reference**

|  |  |
| --- | --- |
| **Property** | **Description** |
| Enable Navigation | Activates links for the selected column or chart. For charts, navigation must be keyed to the value column, not the label column. |
| Open as Modal | Displays the target report as a pop-up dialog. Users can view the report and click close to return. Best for simple target reports without complex filters or column pickers. |
| Navigate To | Select the destination report from any report in the project. Click New Report to create a new target report directly from this dialog. |
| Filter on selected row | Filters the target report by the value the user clicked. Options: Filter on all Rows columns, Filter only on Grouped columns, Filter only on currently selected column. |
| Filter on applied slicer selections | Passes the current slicer selections to the target report, maintaining the filter context. |
| Include current report's filters | Includes filters defined in the Filters section of the Ad Hoc Query Configuration dialog. |
| Add currently selected column | If the clicked column doesn't exist in the target report, adds it automatically. |
| Include current report's added columns | Retains and applies any added columns from the current report to the target report. |

**Coded Links (Wiki-Style Syntax)**

For maximum flexibility in report navigation, use Wiki-style coded links. These links can be
placed in HTML text boxes or in the Navigate field of button properties. Coded links support
navigation to any report, including filtered views and reports in other projects.

**Basic Syntax**

`[[report|display-text|tooltip-text]]`

Where report is the target, display-text is the visible link text (optional), and tooltip-text
appears on hover (optional).

**Link Syntax Options**

|  |  |
| --- | --- |
| **Syntax** | **Description** |
| /ReportName | Navigate to a top-level report (leading slash indicates root) |
| ChildReport | Navigate to a child report (relative to current) |
| .. | Move up one level in the report hierarchy |
| ../SiblingReport | Navigate to a sibling report (up one level, then to report) |
| / | Navigate to the default (home) report for the project |
| //projectname/report | Navigate to a report in a different project |
| tab:TabName/ReportName | Navigate to a report on a specific tab |
| dialog:report:/ReportName | Open the report as a modal (pop-up) dialog |
| %MetricName | Link to a metric report; displays the metric value as link text |
| dataTable:TableName | Navigate to a specified data table (v12.1+) |
| costModel:ModelName | Navigate to a model overview report (v12.1+) |
| /@Object/!FILTER[...] | Navigate to a filtered object report |

**Coded Link Examples**

**Navigate to a child report with custom text and tooltip:**

`[[Applications|Click here|This report is preliminary.]]`

**Navigate to a top-level report as a modal dialog:**

`[[dialog:report:/Server Group Analysis/Server Detail|Server Detail|Examine details.]]`

**Navigate to a filtered report:**

`[[/Software Report/@Cost Source/!FILTER[Cost Source Master Data.Cost
Pool=Software]|Software Report]]`

**Navigate to a report on a tab in another project:**

`[[//Budget1/tab:Budgeting/2013 Budget]]`

**URL Encoding for Special Characters**

If your report names or filter values contain special characters, encode them using standard URL
encoding:

|  |  |  |
| --- | --- | --- |
| **Character** | **Encoded Value** | **Example Usage** |
| / (forward slash) | %2F | Report names containing slashes |
| " (quotation mark) | %22 | Filter values with quotes |
| (space) | + or %20 | Multi-word report names |

**Report Collection Navigator**

Report collections group related reports together, and the report collection navigator component
provides a visual way for users to switch between reports in the same collection. When you add a
report to a collection, the navigator component is automatically added to the report, appearing as a
tab bar or menu at the top of the report.

Report collection navigators are managed through the Project tab > Report Collections dialog.
Administrators can create custom collections, assign reports to collections, set display order, and
configure which roles have access to each collection.

**HTML Text Boxes with Links**

HTML text boxes can contain navigation links using Wiki-style syntax, providing flexibility for
creating custom navigation interfaces. Add images, formatted text, and multiple links within a
single component.

**Adding an HTML Text Box**

1. From the Report tab, click the HTML icon
2. The Edit Content dialog opens where you enter HTML code and Wiki-style links
3. Click Apply to preview or OK to save and close

Note: HTML text boxes do not support JavaScript. HTML links cannot include JavaScript event
handlers.

**Parent topic:** [Report Components: Navigation](../../../../studio/new-uc/reference/report-studio-reference/report-component-navigation.html)
