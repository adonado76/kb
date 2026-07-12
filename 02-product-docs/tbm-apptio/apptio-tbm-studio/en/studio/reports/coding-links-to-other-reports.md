---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Code links to other reports"
breadcrumb: []
source_path: "studio/reports/coding-links-to-other-reports.html"
images:
  - "resources/images/studio_images/studioimages/reports/studio_code_links_to_other_reports_700x534.png"
  - "resources/images/studio_images/studioimages/reports/studio_report_show_api_url_600x155.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Code links to other reports

**Applies to**: TBM Studio 12.0 and later

If you are creating many reports, you can provide the user with links to quickly move from one
report to another report using Wiki-style syntax. The links must be entered in an HTML text box or a button.

- For information on creating HTML text boxes, see [HTML text box](html.html "Applies to: TBM Studio 12.0 and later").
- For information on creating buttons, see [Button](button.html "Applies to: TBM Studio R.12.0 and later.").

Wiki-style links can also be used in the **Actions** tab for buttons.

## Syntax

The syntax for a Wiki-style link is shown below:

> `[[report|display-text|ToolTip-text]]`

The parameters for the links are described in the following table:

*report*

The name of a child report. The options are as follows:

| **Apptio version** | **Option** | **Description** |
| --- | --- | --- |
| All | *%metric* | Creates a link to the specified metric report and displays the value of the metric as the link text. |
| All | .. | Moves up one level in the report hierarchy. |
| All | @ | Inserts that portion of the link verbatim. For example, use for object reports. |
| All | / | Moves to the default report for the project. |
| All | *//projectname/* | Indicates a project different from the current project. |
| All | dialog:report: | Opens the report as a modal (that is, pop-up) dialog. |
| All | tab:*tab name/report name* | Indicates a report on a tab. |
| v.11 | /@*Object*/!FILTER[*Table.Column="value"*] | Can be used to qualify an object report. |
| v.11 | /@.*TableTransform:Table*/!FILTER[*Table.Column="value"*] | Can be used to qualify a TableTransform report. |
| v.12.1, v.12.2+ | dataTable:*table name* | Creates a link to a specified table. |
| v.12.1, v.12.2+ | costModel:*model name* | Creates a link to a specified model overview report. |

*display-text*

The text displayed in the link. If not specified, the name of the report is used as the link
text.

*tooltip-text*

The text that appears when the user pauses the mouse pointer over the link.

## Special characters

If a URL includes special characters, you must *encode* the characters using the standard
URL character encoding.

## Example

- Enter %2FA for a forward slash ( / )
- Enter %22 for a quotation mark (")

For more information on URL character encoding, search for *URL encoding* on the
internet.

**SEE ALSO**: Refer to the following from *w3schools.com*: [HTML URL
Encoding Reference](https://www.w3schools.com/tags/ref_urlencode.asp "(Opens in a new tab or window)").

## Encode URLs

URLs can be sent over the Internet only by using the ASCII character set.

- Because URLs often contain characters outside the ASCII set, the URL must be converted. URL
  encoding converts the URL into a valid ASCII format.
- URL encoding replaces unsafe ASCII characters with "%" followed by two hexadecimal digits
  corresponding to the character values in the [HTML
  ISO-8859-1](https://www.w3schools.com/charsets/ref_html_8859.asp "(Opens in a new tab or window)") character set.
- URLs cannot contain spaces. URL encoding replaces a space with a **+** sign.

## Examples

The following example creates a link to the child report Applications, with link text of **Click
here** and a tool tip that states **This Applications report is preliminary**:

> ```
> [[Applications|Click here|This Applications report is
>       preliminary.]]
> ```

The following example creates a link to a top-level report named Server Group Analysis (note the
leading slash).

> ```
> [[dialog:report:/Server Group Analysis/Server Detail|Server Detail|Examine server
>           details.]]
> ```

The following example creates a modal dialog (pop-up dialog) to a report called Server
Detail:

> ```
> [[dialog:report:/Server Group Analysis/Server Detail|Server Detail|Examine server
>           details.]]
> ```

The following example creates a filtered report based on the Cost Source object, which filters to
the Software cost pool:

> ```
> [[/Software
>           Report/@Cost Source/!FILTER[Cost Source Master Data.Cost Pool="Software"]|Software
>           Report|Examine the Software Cost Pool.]]
> ```

The following example creates a filtered report based on the Cost Source Master Data transform
(v.11 only):

> ```
> [[/Software
>           Report/@.TableTransform:Cost Source Master Data/!FILTER[Cost Source Master Data.Cost
>           Pool="Software"]|Software Report|Examine the Software Cost
>       Pool.]]
> ```

The following example creates a link to a metric report named Cost. If the value of Cost for this
object is $1,500, the link text will be **$1500**:

> `[[%Cost]]`

The following example links to the same Cost report as the above example, but the link text is
Open cost report:

> ```
> [[%Cost|Open cost
>           report]]
> ```

The following example links to the 2013 Budget report on the Budgeting tab in the Budget1
project:

> `[[//Budget1/tab:Budgeting/2013 Budget]]`

Assuming the following report hierarchy: Home > Business Units > Services Report

- [[/|Go Home]] - Produces a link Go Home that links to the default report.
- [[..|Back to BU]] entered on the Services Report - Produces a link Back to BU that links back to
  the parent report. In this case, Home > Business Units.

Assume you have a parent report called Test. It has two child reports: Child 1 and Child 2. To
create a button that goes from Child 1 to Child 2, enter the following in the **Navigate**
field:

> ```
> ../Child
>         2
> ```

The following example creates a link to the table Cost Source (v.12.1, v.12.2+):

> ```
> dataTable:Cost
>           Source
> ```

The following example creates a link to a model overview report named Summary (v.12.1,
v.12.2+):

> `costModel:Summary`

## Troubleshooting

Sometimes the path to a report isn't obvious from the name or where it appears in the Project
Explorer. Also, renaming reports can complicate matters because the system uses the original report
name for the path. In these cases, look at the URL for the report. This section presents an example
scenario to show how to do this.

Let's say you wanted to create a button or an HTML link that navigates to the Financial Review
report.

The following graphic below shows the Financial Review report in TBM Studio.

1. Right-click on a reporting element, such as a table, to produce a context menu that includes the
   Show API URL selection.

   ![image](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/studio_code_links_to_other_reports_700x534.png)
2. Select **Show API URL**. A dialog appears that shows the report path:

   ![image](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/studio_report_show_api_url_600x155.png)

## Format of the path string

Following is the relevant information from the path above:

> /.View:tab:Service Costing/.View:Financial Review

In the context of a button's navigation field or an HTML link, you would use this:

> [[/tab:Service Costing/Financial Review]]

Note: Indicates an important situation which, if not avoided, may seriously impair
operations.

If you try to use [[/IT Finance - Summary]], it fails because it isn't the full path, including
the tab specification.
