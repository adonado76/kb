---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Published Tables"
breadcrumb:
  - "Reference"
  - "Data Studio Reference"
  - "Published Tables"
source_path: "SSWRJM/studio/new-uc/reference/published-tables.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Published Tables

## Overview

Published Tables provide a dedicated mechanism for exporting data from TBM Studio without using reports.

Advantages:

- No report permission management required
- Export available immediately after dev calc finishes
- Discoverable and maintainable export definitions
- Independent of TBM Studio reporting surface

## Creating Published Tables

Method 1: Create New

1. Navigate to Home tab > New
1. Select Published Table
1. Enter name and category
1. Click OK

Method 2: From Existing Report Table

1. Open report with source table
1. Right-click on report table
1. Select Create Published Table
1. Enter name and category

## Pre-calculation Settings

| Setting | Description |
| --- | --- |
| Setting | Description |
| Active (checked) | System pre-calculates table; ready on API call (default) |
| Inactive (unchecked) | System calculates on first API request |
