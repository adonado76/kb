---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Report Components - Input Components"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Report Components - Input Components"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/report-component-input-components.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Report Components - Input Components

## Overview

Input components in TBM Studio enable users to enter or modify data directly within reports. Unlike filter components that simply narrow displayed data, input components write data back to editable tables, which then flow through the data pipeline and ultimately affect cost model calculations.

Input components are primarily configured through editable table column properties and exposed to end users via report components. Understanding the distinction between filtering data (slicers) and modifying data (input components) is critical for building effective, data-entry-enabled reports.

Key Principle: Input components work with editable tables. To enable data entry in reports, you must first create an editable table and configure its columns with appropriate input types, validation rules, and constraints.
