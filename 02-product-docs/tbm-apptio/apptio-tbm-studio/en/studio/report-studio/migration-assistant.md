---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "IBM Apptio Report Migration Assistant Guide"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
  - "Configuration and Customization"
source_path: "studio/report-studio/migration-assistant.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# IBM Apptio Report Migration Assistant Guide

## Overview

This guide explains how the IBM Apptio Report Migration Assistant works, what is preserved, what
requires manual updates, and how to plan for a successful transition. Report migration creates a new
version of your report in the updated format while leaving your original report unchanged.

- Your existing report is not modified
- A new migrated report opens in a separate tab
- You can compare old vs. new side-by-side to validate results and make updates
- Reports are created with the same name as the original with “(Migrated)” appended.

This document applies to reports built in the classic Report Studio migrating to IBM Apptio
Report Studio. Report migration from the classic Report Studio to IBM Apptio Report Studio is a
customer-managed activity. Customers are responsible for executing the migration and should ensure
the individual performing the migration has administrative permissions in TBM Studio. As part of
this IBM Apptio modernization evolution, classic Report Studio will reach end of life (EOL) on
December 31, 2027. After this date, existing classic Report Studio reports will no longer be
accessible.

To support the transition, the IBM Apptio Report Migration Assistant helps customers move
existing reports from the classic Report Studio to the new experience. The migration process is
largely automated, with the ability to carry over >90% of report components, data configurations,
and layouts, enabling teams to transition efficiently while maintaining continuity. While most
structural elements are preserved, formatting (including colors, fonts, styling, and themes) will
not fully carry over and will require adjustment in the new Report Studio.

While migration is designed to be completed by customers, those who would like assistance or are
unable to complete the migration can reach out to their Customer Success Manager (CSM) to define a
scoped engagement under a Statement of Work (SOW). IBM Apptio Essentials customers may leverage
their TAS service that is available to them.

Customers may also choose to leverage the new/refreshed out-of-the-box (OOTB) reports instead of
migrating their existing report collections.

## Migration Playbook

This section describes the playbook to be applied

1. **Discovery**:
   - The customer reviews the list of recently used reports in the CT Report Studio experience to
     choose which ones should be migrated.
2. **Migration**:
   - For each report:
     - The user must “Check Out” the report
     - The user clicks the “Migrate Report” button in TBM Studio. This produces a new Report with the
       same name as the old report with “(Migrated)” appended, e.g., “Financial Review (Migrated)”. This
       new report is generated in a new tab.
     - The user switches to the new report in IBM Apptio Report Studio, verifies that the data
       configuration is the same, and applies the desired formatting options to make the report look like
       the old one.
   - What to Expect Post-Migration
     - A list of components/widgets that will be migrated is captured [here](#migasst__What_will_be). The table also includes a list of widgets/capabilities that will not be migrated to
       the new experience.
     - Unsupported widgets will be displayed as a placeholder. Placeholders can only be deleted.
     - Drill navigation will not be migrated.
     - Colors may be different.
     - The migration of a single report should not take more than a couple of minutes.
     - If you would like to apply personalized logos, you can use an HTML component with an image tag,
       e.g., <img src="https://logos.apptio.com/myLogo.jpg" >.
3. **Recommended Post Migration Workflow** 
   - Open both reports side-by-side
     - Original (checked out to allow viewing of configuration)
     - Migrated version (editable)
   - Validate data
     - Confirm metrics and outputs match
   - Validate components
     - Open the Layer panel to view all components and to see any that may be obscured.
   - Review placeholders
     - Identify unsupported components via the layer panel
     - Remove or rebuild as needed
   - Fix formatting
     - Adjust colors, fonts, and layout
     - Align components using layout tools
   - Rebuild interactions
     - Recreate drill navigation manually
4. **User Acceptance Testing**:
   1. Once all reports for a customer have been migrated, the customer reviews the updates.
      - The user adjusts the reports based on feedback
5. **Hand off**:
   - The user renames all accepted reports to remove the “(Migrated)” tag and checks in the new
     report(s).
   - Existing CT Report Studio based reports can continue to co-exist until the user feels
     comfortable with IBM Apptio Report Studio

## What will be migrated vs not

|  |  |  |  |
| --- | --- | --- | --- |
| Will be migrated | Will not be migrated | Migrated later (Timing TBD) | Under consideration |
| - Data configurations (metrics, dimensions, filters) - Component types (supported) - Layout structure - Positioning (approximate) - Component sizing (exact) - Data outputs (numbers remain consistent) - Report name (with “(Migrated)” appended) - Button - Charts   - Bar   - Column   - Line   - Overlay: Column + Line   - Overlay: Stacked column + Line   - Overlay: Line + Line   - Pie   - Stacked bar   - Stacked column - Column picker - Compact slicer - Editable table - Group - HTML - KPI - Quick pivot - Simplified upload - Slicer - Table - Tabs | - Table   - Demand   - Task list   - o Cell annotations - Symbol   - Gauge   - Symbol - Formatting (colors, fonts, styling, themes) - Drill configurations (Drill paths are not migrated due to differences in report identification   (legacy paths vs. new unique IDs) - Unsupported / deprecated components - Exact alignment (Minor layout shifts may occur) - GL mapper - Mapping grid - Model diagram - Note - Table upload - Report collections - Folder structure | - Chart   - Tree map - Icon - Text - Waterfall | - Chart   - Bubble   - Radar |

## Report Complexity Profiles

Use these profiles to set expectations for migration effort:

**Simple Reports**

- Basic charts and tables
- Minimal formatting
- Few or no custom components
- Expected Outcome:
- Quick cleanup
- Mostly formatting adjustments

**Medium Complexity Reports**

- Mix of charts, KPIs, and filters
- Some custom formatting
- Moderate layout complexity
- Expected Outcome:
- Requires formatting fixes and minor rebuilding
- Some placeholders to address

**Complex Reports**

- Advanced layouts and heavy customization
- HTML components, buttons, or legacy widgets
- Drill paths and interactivity
- Expected Outcome:
  - Significant manual refinement required
  - Multiple components may need rebuilding
  - Interaction logic must be recreated

Note:

- Migrate target reports before source reports. Since drill navigation must be re-added
  post-migration, it may be more efficient to migrate your classic reports from the bottom up. That
  way, when you’re fixing the source report drills, the targets are available for you to choose.
- The position of components may vary depending on whether the classic component header is
  visible. In classic reports, component titles or headers are outside the component borders, whereas
  in new reports, they are inside. When classic report components have hidden headers, report authors
  tend to adjust them upward to reduce whitespace. Thus, when migrating reports, we move them
  down.

## Known issues

The following are known issues with the Report Migration Assistant in release 12.11.21 (April
2026). Most or all will be addressed in 12.11.22 (May 2026)

- Compact slicers with multiple slicers in one component are migrated to a group of individual
  slicers. This grouping renders the slicers ineffective because it changes their scope. Simply
  ungroup the slicers to remedy this.
- Tree tables with cross-object configurations (rows, columns, values, or filters with two or more
  model objects) may not work. This will be addressed in 12.11.22.

**Parent topic:** [Configuration and Customization](../../studio/report-studio/config-custom.html)
