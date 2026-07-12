---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Manual Data Entry"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "Work with Data"
  - "Manual Data Entry"
source_path: "SSWRJM/studio/new-uc/howtoguides/work-with-data/manual-data-entry.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Manual Data Entry

| Content Type | How-To Guides |
| --- | --- |
| Content Type | How-To Guides |
| Target Audience | Business Analysts, IT Finance Teams, Administrators |
| Prerequisites | Data Studio access, understanding of TBM Studio tables and transform pipelines |

## Overview

Editable tables enable you to manually enter and maintain data directly within TBM Studio. They serve as user-editable data-entry layers that feed into transform tables and ultimately your cost model. Use editable tables for scenarios such as labor mappings, cost-center attributes, vendor classifications, budget variance explanations, and any reference data that requires human input or enrichment.

Key distinction: TBM Studio supports two types of editable tables with fundamentally different purposes:

- Blank editable tables : You create all rows and columns from scratch. Best for small reference datasets where every piece of data originates from user input.
- Enriched editable tables : The system generates rows from an existing transform table, and users add annotations or classifications. Best for enriching system-generated data with human judgment.

Understanding when to use each type is critical for building maintainable data pipelines.
