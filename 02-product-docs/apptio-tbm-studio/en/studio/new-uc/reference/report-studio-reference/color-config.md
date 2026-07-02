---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Color Configuration"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Charts"
source_path: "studio/new-uc/reference/report-studio-reference/color-config.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Color Configuration

**Custom Color Palettes**

**Applies to:** TBM Studio 12.10.10 and later

You can apply custom color palettes to most chart types. Access color palettes from the Report
tab > Color Palette option. Palettes can be applied at the report level or the report collection
level.

**Limitations:** Custom color palettes cannot be applied to Tree Map or Waterfall charts.
Color palettes also do not affect tables, font/label colors, slicers, backgrounds, or KPI
components.

**Color Spec Syntax**

For fine-grained control over individual metric colors, use the Color Spec property. Enter color
specifications in the following format:

`metric=color-spec[;metric=color-spec]`

**Example:** `Cost=blue;Budget=green;!purple`

This sets Cost to blue, Budget to green, and excludes purple from automatic color assignment.

**Available Color Keywords**

**Flat Colors:** black, gray, lightgray, darkgray, white, transparent

**Gradient Colors:** blue, red, green, yellow, violet, brown, skyblue, lightgreen, orange,
darkblue, darkgreen, purple, aqua, pink, teal, crimson

**Tip:** Prefix gradient colors with "flat" to get non-gradient versions (e.g., flatblue).
Hexadecimal codes are also supported (e.g., Cost=#082f6d).

**Parent topic:** [Report Components: Charts](../../../../studio/new-uc/reference/report-studio-reference/report-component-charts.html)
