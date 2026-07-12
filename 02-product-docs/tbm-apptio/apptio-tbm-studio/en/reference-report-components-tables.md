---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Report Components: Tables"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Tables"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/report-component-table.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Report Components: Tables

## Overview

Tables are the primary data display component in Report Studio. They present structured data in rows and columns, support interactive features like sorting and filtering, and offer extensive configuration options for formatting, calculations, and navigation. Tables can display data from model objects, transform tables, or editable tables.

This reference section provides comprehensive documentation for all table configuration options organized by functional area.

## Table Types

Report Studio supports several table types to address different data presentation needs.

| Table Type | Description | Use Case |
| --- | --- | --- |
| Table Type | Description | Use Case |
| Standard Data Table | Basic table with rows, columns, and values. Created by dragging fields from Project Explorer into Component Configuration areas. | Most common table type. Use for displaying cost data, inventories, allocations, and general reporting. |
| Grouped Table | Consolidates data by values in one or more columns. Automatically aggregates duplicate entries and displays subtotals. | Summarizing costs by business unit, service, or category. Comparing aggregate values. |
| Subtotal Tree Table | Hierarchical table with expandable rows. Users can drill down through multiple levels. | Hierarchical cost breakdowns. Business unit to application to service drill-downs. |
| Pivot Table | Displays pivoted data using Pivot Row Col, Pivot Col Col, and Pivot Val Col properties. | Cross-tabulation analysis. Time-based comparisons across categories. |
| Editable Table | Allows users to enter and modify data directly in the report. Supports validation and carry-forward. | Budget entry, forecast adjustments, manual cost allocations, and data collection. |
