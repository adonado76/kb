---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Transform Tables"
breadcrumb:
  - "Concepts and Architecture"
  - "Data Architecture"
  - "Tables and Table Types"
  - "Transform Tables"
source_path: "SSWRJM/studio/new-uc/concepts-architecture/data-architecture/transform-tables.html"
images:
  - "03-media/apptio-tbm-studio/transform-pipeline.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Transform Tables

Purpose: Clean, combine, and reshape data within TBM Studio.

Every table in Data Studio has an associated transform pipeline. A transform table is the output of that pipeline—the result of applying one or more transformation steps to your source data. You can also create new transform tables derived from existing ones, building chains of transformations that progressively refine your data.

![Transform Pipeline](../../../../resources/images/studio_images/transform-pipeline.png)

- Steps execute top-to-bottom in the order they appear in the pipeline.
- You can add, remove, reorder, and edit steps at any time.
- The Table step at the end of the pipeline always shows the final result of all transformations.
- Transform outputs can be used as inputs for other transforms, creating reusable data processing chains.
