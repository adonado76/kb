---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "RLS Scope: Where RLS Applies"
breadcrumb:
  - "TBM Studio"
  - "Concepts and Architecture"
  - "Security Model"
  - "Row-Level Security (RLS)"
source_path: "studio/new-uc/concepts-architecture/security-model/rls-scope.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# RLS Scope: Where RLS Applies

RLS can be applied across multiple areas of TBM Studio. Understanding where it applies—and where
it does not—is essential for complete security coverage.

|  |  |  |
| --- | --- | --- |
| **Area** | **RLS Behavior** | **Notes** |
| Transform Tables (Data Studio) | Applied via RLS pipeline step added to each table individually | Adding an RLS step automatically adds a modeling step. Only modeled tables and editable tables can have RLS. |
| Model Objects (Model Studio) | RLS filters flow through from the underlying transform tables | Each model step requires its own RLS configuration. RLS is not automatically inherited between model steps. |
| Reports (Report Studio) | Reports display data filtered by RLS. Aggregations reflect the filtered view. | All tables built with Ad Hoc Query are redacted. Certain legacy tables may not be. |
| Editable Tables | Users can only see and edit rows permitted by their RLS configuration | Hidden rows are preserved during publish—they are not deleted or overwritten. |
| Model Overview Reports | Each tier reflects RLS applied to that specific tier’s table | Values in a tier may not sum to the total shown in parent tiers if RLS is applied only to child tiers. |
| Drill-Through Reports | RLS applies to the drilled-to table based on that table’s own RLS config | The drill-to table uses its own RLS rules, not the parent table’s rules. |

Important:

**Critical: RLS Does Not Inherit Automatically**

Tables do not automatically inherit RLS settings. You must add an RLS step for each model step
that requires data security. If you configure RLS on Cost Source but not on IT Resource Towers,
users may see unfiltered data when viewing reports based on IT Resource Towers.

**Parent topic:** [Row-Level Security (RLS)](../../../../studio/new-uc/concepts-architecture/security-model/row-level-security.html)
