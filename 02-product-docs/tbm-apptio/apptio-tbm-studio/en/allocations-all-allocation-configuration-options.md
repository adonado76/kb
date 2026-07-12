---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "All Allocation Configuration Options"
breadcrumb:
  - "Reference"
  - "Model Studio Reference"
  - "Allocations"
  - "All Allocation Configuration Options"
source_path: "SSWRJM/studio/new-uc/reference/model-studio-reference/allocation-config.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# All Allocation Configuration Options

This table consolidates all configuration options across allocation types.

Complete Parameter Reference

| Parameter | Applies To | Description |
| --- | --- | --- |
| Parameter | Applies To | Description |
| Allocate | All types | Select metrics to allocate (Cost, Budget, etc.) |
| Using | All types | Allocation type selection |
| To | All types | Target model object |
| Distribution | Weighted, Consumption, Standard, Recursion | Even, Weight By, or Data Relationship |
| Weight By | When Distribution = Weight By | Table column, Metric, or Other Driver |
| Data Relationship | When Distribution = Data Relationship | Source and target column pairs |
| Consumption Column | Consumption only | Target column showing units consumed |
| Capacity Column | Consumption only | Source column showing total capacity |
| Formula | Formula only | Custom allocation formula |
| Precision | Recursion only | Minimum value to continue iterating |
| Maximum Iterations | Recursion only | Maximum allocation cycles |
| Incremental Mode | Recursion only | Adds iteration value to source |
| From Filter | Formula | Filter rows in source table |
| To Filter | Formula | Filter rows in target table |
