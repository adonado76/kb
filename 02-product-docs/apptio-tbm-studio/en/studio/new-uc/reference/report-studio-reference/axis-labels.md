---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Axis Labels and Formatting"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Charts"
source_path: "studio/new-uc/reference/report-studio-reference/axis-labels.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Axis Labels and Formatting

**Label Truncation**

Labels displayed on the X and Y axes have a maximum length of 20 characters. If a label exceeds
this length, characters are removed from the middle of the label with an ellipsis. This ensures
labels remain readable while fitting within the available space.

**Example:** "aaaa bbbb cccc dddd eeee ffff 0001" would be truncated to display as "aaaa
bb...fff 0001"

**Number Formatting**

Use the Chart Number Format property to control how numbers appear on chart axes. The format uses
standard number format patterns:

|  |  |  |
| --- | --- | --- |
| **Pattern** | **Example Input** | **Example Output** |
| #,### | 5000000 | 5,000,000 |
| # | 5000000 | 5000000 (no formatting) |
| ¤#,### | 5000000 | $5,000,000 (locale currency) |

Tip: Use the universal currency symbol (¤) in the prefix or format field to display the
locale-appropriate currency symbol. To enter this symbol, copy it from the documentation or the
properties dialog.

**Parent topic:** [Report Components: Charts](../../../../studio/new-uc/reference/report-studio-reference/report-component-charts.html)
