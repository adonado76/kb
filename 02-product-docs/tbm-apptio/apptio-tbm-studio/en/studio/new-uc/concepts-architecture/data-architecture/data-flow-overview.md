---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Data Flow Overview"
breadcrumb:
  - "TBM Studio"
  - "Concepts and Architecture"
  - "Data Architecture"
source_path: "studio/new-uc/concepts-architecture/data-architecture/data-flow-overview.html"
images:
  - "resources/images/studio_images/3stage-pipeline.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Data Flow Overview

TBM Studio processes data through a three-stage pipeline. Each stage corresponds to one of the
platform’s main components, and data moves through them in a well-defined sequence.

## The Three-Stage Pipeline

At the highest level, the data flow follows this path:

![Three Stage Pipeline](../../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/3stage-pipeline.png)

- **Data Studio** is where data enters the platform. You upload files, connect to external
  databases, or enter data manually. Data Studio also cleans, transforms, and prepares your data for
  modeling.
- **Model Studio** is where cost allocation happens. It references the prepared tables from
  Data Studio and applies business rules to allocate costs from sources (like general ledger entries)
  to business-meaningful targets (like applications or business units).
- **Report Studio** is where you visualize and analyze the results. Reports pull from model
  outputs and present insights through tables, charts, and dashboards. Data can also exit the platform
  via Published Tables and APIs.

## Key Transformation Points

Data is transformed at several critical points as it moves through the pipeline:

|  |  |  |
| --- | --- | --- |
| **Transformation Point** | **What Happens** | **Where It Occurs** |
| Data Ingestion | External files are parsed, column types are detected, and data is imported into TBM Studio | Data Studio |
| Transform Pipeline | Data is cleaned, joined, filtered, mapped, and enriched through a series of configurable steps | Data Studio |
| Date Partitioning | Multi-month data is sliced into individual time periods for month-centric analysis | Data Studio |
| Master Dataset Mapping | Heterogeneous sources (GL, Budget, Forecast) are mapped to a unified canonical schema | Data Studio |
| Cost Allocation | Prepared data is allocated from cost sources to targets using driver-based rules | Model Studio |
| Report Calculation | Model outputs are aggregated, filtered, and formatted for presentation | Report Studio |

## Stored Data vs. Calculated Data

An important architectural distinction in TBM Studio is between data that is stored persistently
and data that is calculated on demand.

- **Stored data**: The raw and transformed tables in Data Studio contain stored data. Once you
  upload a file or save a transform, that data persists in the project database. Editable table
  entries are also stored data.
- **Calculated data**: Model allocations and report outputs are calculated during build
  operations (staging or production calculations). These results reflect the current state of your
  transforms, model rules, and time period settings.

Note:

**Practical Implication**

Because model outputs are calculated rather than stored statically, changing upstream data (such
as uploading a new GL file) does not immediately change your reports. You must run a build to
recalculate the model with the updated data.
