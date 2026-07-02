---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Set the default colors for metrics on charts"
breadcrumb: []
source_path: "studio/reports/set-default-colors-charts.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Set the default colors for metrics on charts

**Applies to**: TBM Studio 12.0 and later

Use the **Color Spec** property to change the default colors for metrics in all charts or in a
single chart.

- For all charts, use the **Color Spec** property for projects. Access the property by clicking
  **Project Settings** on the **Project** tab.
- For an individual chart, use the **Color Spec** property on the **Chart** tab of the
  **Properties** dialog.

You can specify alternate colors for metrics by entering a **Color Spec** string in the
following format:

> `metric=color-spec[;metric=color-spec]`

The elements of the string are described below.

**metric** - Any metric in the chart as its name appears in the chart legend. No asterisks are
supported.

**Color Spec** - A string describing the color. Valid color-spec strings are:

- **Flat colors**: black, gray, lightgray, darkgray, white. "Transparent" also is supported and
  will effectively make a bar or line invisible.
- **Gradient colors**: blue, red, green, yellow, violet, brown, skyblue, lightgreen, orange,
  darkblue, darkgreen, purple, aqua, pink, teal, crimson.
- You can also prefix any of the gradient colors with **flat** to get a non-gradient version,
  for example: **flatblue**.
- An exclamation point ( ! ) before a color-spec indicates that the following color-spec should
  not be used anywhere in the chart.

You can specify multiple Color Specs by separating them with semicolons ( ; ) as in the following
example:

> `Cost=blue;Budget=green;!purple`

This example specifies: Cost is blue, Budget is green and do not use purple.

Only one metric per color is supported. If you set two metrics to the same color, only the first
metric will use the selected color.

Hexadecimal color codes (e.g. #ff55ff) are valid, as are color keywords. For example, to specify
blue for the Cost metric:

> `Cost=#082f6d`

The colors available are shown below:

| Color | Swatch | Color | Swatch | Color | Swatch |
| --- | --- | --- | --- | --- | --- |
| blue | image | purple | image | black | Black |
| red | image | lightblue | image | gray | Grey |
| green | image | pink | image | lightgray |  |
| yellow | image | teal | image | darkgray | Dark Grey |
| violet | image | crimson | image | white | White |
| brown | image | orange | image |  |  |
| skyblue | image | darkblue | image |  |  |
| lightgreen | image | darkgreen | image |  |  |

## Custom Color Palette

**Applies to**: 12.10.10 and later

The value in the Color Spec field is the primary value and cannot be overridden by the custom
color palette that is chosen for the report.

To know more, refer [Custom Color Palette](../admin/color-enhancement.html).
