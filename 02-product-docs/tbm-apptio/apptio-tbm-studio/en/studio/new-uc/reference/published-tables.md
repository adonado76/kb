---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Published Tables"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Data Studio Reference"
source_path: "studio/new-uc/reference/published-tables.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Published Tables

## Overview

Published Tables provide a dedicated mechanism for exporting data from TBM Studio without using
reports.

**Advantages:**

- No report permission management required
- Export available immediately after dev calc finishes
- Discoverable and maintainable export definitions
- Independent of TBM Studio reporting surface

## Creating Published Tables

**Method 1: Create New**

1. Navigate to Home tab > New
2. Select Published Table
3. Enter name and category
4. Click OK

**Method 2: From Existing Report Table**

1. Open report with source table
2. Right-click on report table
3. Select Create Published Table
4. Enter name and category

## Pre-calculation Settings

|  |  |
| --- | --- |
| **Setting** | **Description** |
| Active (checked) | System pre-calculates table; ready on API call (default) |
| Inactive (unchecked) | System calculates on first API request |

**Parent topic:** [Data Studio Reference](../../../studio/new-uc/reference/data-studio-reference.html)
