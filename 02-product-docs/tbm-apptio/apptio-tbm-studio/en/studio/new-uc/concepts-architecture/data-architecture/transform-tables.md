---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Transform Tables"
breadcrumb:
  - "TBM Studio"
  - "Concepts and Architecture"
  - "Data Architecture"
  - "Tables and Table Types"
source_path: "studio/new-uc/concepts-architecture/data-architecture/transform-tables.html"
images:
  - "resources/images/studio_images/transform-pipeline.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Transform Tables

**Purpose:** Clean, combine, and reshape data within TBM Studio.

Every table in Data Studio has an associated transform pipeline. A transform table is the output
of that pipeline—the result of applying one or more transformation steps to your source data. You
can also create new transform tables derived from existing ones, building chains of transformations
that progressively refine your data.

Think of transform tables as an assembly line. Raw data enters at one end, passes through a
series of processing stations (transform steps), and emerges at the other end as clean, structured
data ready for the cost model.

![Transform Pipeline](../../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/transform-pipeline.png)

Key characteristics of transform tables:

- Steps execute top-to-bottom in the order they appear in the pipeline.
- You can add, remove, reorder, and edit steps at any time.
- The Table step at the end of the pipeline always shows the final result of all transformations.
- Transform outputs can be used as inputs for other transforms, creating reusable data processing
  chains.

**Parent topic:** [Tables and Table Types](../../../../studio/new-uc/concepts-architecture/data-architecture/table-types.html)
