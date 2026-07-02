---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Data Display Options"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Tables"
source_path: "studio/new-uc/reference/report-studio-reference/data-display-options.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Data Display Options

**Number Formatting**

Number formatting controls how numeric values appear in the table. Formatting can be set at the
metric level (for model metrics), column level (for formula columns), or using the NumberFormat
function.

|  |  |  |  |
| --- | --- | --- | --- |
| **Format Type** | **Pattern Example** | **Output Example** | **Notes** |
| Standard Number | #,### | 5,000,000 | Includes grouping separator |
| Currency (USD) | $#,###.00 | $5,000.00 | Use ¤ for locale currency |
| Percentage | #,###% | 75% | Value multiplied by 100 |
| Decimal Precision | #,###.00 | 1,234.56 | Fixed decimal places |
| Millions | $#,###M | $5M | Abbreviation suffix |
| No Formatting | # | 5000000 | Raw number |

**NumberFormat function syntax:**

`=NumberFormat(Table.Column, "$#,###.00")`

**Tip:** To format as currency using the project's locale, use the universal currency symbol
(¤) instead of a specific currency sign.

**Negative Number Display**

Negative numbers can be displayed in several formats by specifying a negative pattern in the
NumberFormat function.

|  |  |  |
| --- | --- | --- |
| **Style** | **Pattern** | **Example Output** |
| Minus Sign (default) | #,###;-#,### | -1,000 |
| Parentheses | #,###;(#,###) | (1,000) |
| Currency with Parentheses | $#,###;($#,###) | ($1,000) |

**Null and Empty Value Display**

Empty or null values in tables display as blank by default. Use the IF function to provide
alternate display:

`=IF(IsNumeric(Value), Currency(Value), "$0")`

**Zeroes Filter**

You can remove rows with zero values from tables to focus on meaningful data.

**To apply the zeroes filter:**

1. Select the table and click the Data tab.
2. Click Zeroes.
3. Select the reports where zeroes should be removed.
4. Click OK. To revert, select reports and click Revert All.

**Parent topic:** [Report Components: Tables](../../../../studio/new-uc/reference/report-studio-reference/report-component-table.html)
