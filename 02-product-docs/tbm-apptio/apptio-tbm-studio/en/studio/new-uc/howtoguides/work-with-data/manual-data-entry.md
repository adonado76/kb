---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Manual Data Entry"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Work with Data"
source_path: "studio/new-uc/howtoguides/work-with-data/manual-data-entry.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Manual Data Entry

|  |  |
| --- | --- |
| **Content Type** | How-To Guides |
| **Target Audience** | Business Analysts, IT Finance Teams, Administrators |
| **Prerequisites** | Data Studio access, understanding of TBM Studio tables and transform pipelines |

## Overview

Editable tables enable you to manually enter and maintain data directly within TBM Studio.
They serve as user-editable data-entry layers that feed into transform tables and ultimately
your cost model. Use editable tables for scenarios such as labor mappings, cost-center
attributes, vendor classifications, budget variance explanations, and any reference data
that requires human input or enrichment.

**Key distinction:** TBM Studio supports two types of editable tables with fundamentally
different purposes:

- [Blank editable tables](create-blank-et.html): You create all rows and
  columns from scratch. Best for small reference datasets where every piece of data
  originates from user input.
- [Enriched editable tables](create-eet.html): The system generates rows from
  an existing transform table, and users add annotations or classifications. Best for
  enriching system-generated data with human judgment.

Understanding when to use each type is critical for building maintainable data
pipelines.

- **[Create Blank Editable Tables](../../../../studio/new-uc/howtoguides/work-with-data/create-blank-et.html)**
- **[Create Enriched Editable Tables](../../../../studio/new-uc/howtoguides/work-with-data/create-eet.html)**
- **[Configure Dropdowns and Validation](../../../../studio/new-uc/howtoguides/work-with-data/config-dd-valid.html)**
- **[Set Up Editable Table Publishing](../../../../studio/new-uc/howtoguides/work-with-data/setup-et-publish.html)**
