---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "admin"
title: "Set the default colors for project metrics"
breadcrumb: []
source_path: "admin/set-default-colors.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Set the default colors for project metrics

Applies to: TBM Studio 12.0 and later

Use the Color Spec
property to change the default colors for metrics in a project.

- For all charts, use the Color Spec property in the Edit Project Settings dialog. Access the
  dialog by clicking Definition on the Project tab.
- For an individual chart, use the Color Spec property on the
  Chart tab of the Properties dialog for the chart.

To access the property, on the Project tab, in the
Page Setup group, click Project Settings. You can
specify alternate colors for metrics by entering a **Color Spec** string in the following
format:

`metric=color-spec[;metric=color-spec]`

The elements of the string are
described below.

- metric - Any metric in the chart as its name appears in the chart legend.
  No asterisks are supported.
- Color Spec - A string describing the color. Valid color-spec strings are:
  - Flat colors: black, gray, lightgray, darkgray, white. "Transparent" also
    is supported and will effectively make a bar or line invisible.
  - Gradient colors: blue, red, green, yellow, violet, brown, skyblue,
    lightgreen, orange, darkblue, darkgreen, purple, aqua, pink, teal, crimson.
  - You can also prefix any of the gradient colors with flat to get a
    non-gradient version, for example: flatblue.
  - An exclamation point ( ! ) before a color-spec indicates that the following color-spec should
    not be used anywhere in the chart.

You can specify multiple Color Specs by separating them with semicolons ( ; ) as in the
following example:

`Cost=blue;Budget=green;!purple`

This example specifies: Cost
is blue, Budget is green and do not use purple. Only one metric per color is supported. If you set
two metrics to the same color, only the first metric will use the selected color. You can use hex
codes to specify colors. For example, to specify blue:

`Cost=#082f6d`
