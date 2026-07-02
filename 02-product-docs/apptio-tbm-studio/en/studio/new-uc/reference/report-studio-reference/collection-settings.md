---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Collection Settings"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Collections"
source_path: "studio/new-uc/reference/report-studio-reference/collection-settings.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Collection Settings

**Color Palette Settings**

Beginning with R12.10.10, administrators can apply custom color palettes to report collections.
When a color palette is selected for a collection, all reports within that collection automatically
use the same color palette for charts, providing visual consistency across the collection.

**To apply a color palette to a collection:**

1. On the **Project** tab, select **Report Collections**.
2. Select the collection from the **Available Collections** list.
3. Choose a color palette from the available custom or preset palettes.
4. Click **Close** to save.

Note: If a different color palette is selected for an individual report within the collection, that
report's palette will override the collection-level palette for that report only. New reports added
to the collection do not automatically inherit the collection's color palette; administrators must
manually apply it at the report level if needed.

**Color Palette Scope**

Collection-level color palettes apply to:

- Bar charts, line charts, pie charts, and most other chart types
- Chart colors only (not tables, fonts, slicers, backgrounds, or KPIs)

Color palettes do not apply to Treemap and Waterfall chart types.

**Parent topic:** [Report Collections](../../../../studio/new-uc/reference/report-studio-reference/report-collection.html)
