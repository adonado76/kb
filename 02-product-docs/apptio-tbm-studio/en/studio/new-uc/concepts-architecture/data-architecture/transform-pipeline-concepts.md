---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Transform Pipeline Concepts"
breadcrumb:
  - "TBM Studio"
  - "Concepts and Architecture"
  - "Data Architecture"
source_path: "studio/new-uc/concepts-architecture/data-architecture/transform-pipeline-concepts.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Transform Pipeline Concepts

The transform pipeline is the processing engine at the heart of Data Studio. Every table has a
pipeline—a sequence of steps that process data from its raw ingested form into clean, structured
output ready for cost modeling.

## Transform Steps

A transform step is a single data processing operation within the pipeline. Steps execute in
sequence from top to bottom, and each step’s output becomes the next step’s input. You can add,
remove, and reorder steps to build the exact processing logic you need.

Every table pipeline starts with two automatic steps:

- **Source:** Defines where the data comes from (file upload, existing table, DataLink
  connector, or editable table).
- **Table:** Displays the final output of the entire pipeline. This step always appears at the
  end.

For file upload sources, two additional steps are automatically added:

- **Upload:** Allows you to select and manage the uploaded file.
- **Import:** Controls how the file is parsed—header row detection, data start row, column type
  detection, and delimiter settings.

## Available Transform Step Types

You can add the following steps to any table’s pipeline to transform data:

|  |  |  |
| --- | --- | --- |
| **Step Type** | **What It Does** | **Common Use Case** |
| Map Columns | Conforms table output to match a standard schema (such as the ATUM taxonomy) and maps columns from source to target | Mapping GL data to cost pool categories |
| Join | Combines data from two or more tables into single rows based on matching values in shared columns | Enriching cost data with vendor information from a separate table |
| Append | Stacks the rows from one table below the rows of another table | Combining monthly GL files into a single dataset |
| Filter | Removes rows based on conditions applied to one or more columns | Excluding non-IT cost centers from the analysis |
| Formula | Creates new calculated columns, changes column types, or overrides existing values | Computing a derived classification or converting a currency |
| Group | Groups rows by the values in one or more text columns, aggregating numeric values | Summarizing transactions by cost center |
| Date Partition | Uses date values in the file (in rows or columns) to distribute data across time periods | Slicing a multi-month GL export into individual monthly periods |
| Hide and Rename | Hides unnecessary columns or renames columns for clarity | Removing internal IDs before data enters the model |
| Assign Rows | Uses machine learning and user-created rules to map data to taxonomy concepts | Automating cost pool assignments using ML classification |
| Flatten Hierarchy | Adds one column for each level in a data hierarchy | Enabling slicer-based filtering on hierarchical organization structures |

## Step Execution Order

Transform steps execute strictly from top to bottom. The output of one step becomes the input for
the next. This sequential model means that the order of steps matters:

- A Filter step placed before a Join will reduce the number of rows before the join operation,
  potentially improving performance.
- A Formula step placed after a Join can reference columns from both joined tables.
- A Map Columns step typically appears late in the pipeline, after cleaning and enrichment are
  complete.

You can drag steps to reorder them in the pipeline, with the exception of certain fixed steps
(Source, Upload, Import, and Table) that must remain in their designated positions.

Note:

**Best Practice**

Structure your pipeline so that filtering and data reduction happen early, joins and enrichment
happen in the middle, and mapping and final formatting happen last. This pattern improves both
clarity and performance.

## Data Lineage

Data lineage refers to the ability to trace a piece of data from its origin (the uploaded source
file) through every transformation it undergoes, all the way to the final model output and report.

Understanding data lineage matters for several reasons:

- **Accuracy:** When a report shows an unexpected number, lineage helps you trace backward to
  find where the issue originated—whether in the source data, a transform step, or a model allocation
  rule.
- **Auditability:** Finance and compliance teams need to verify that cost allocations can be
  traced back to source transactions.
- **Impact analysis:** Before changing a transform, you can follow the lineage forward to
  understand which model objects and reports will be affected.

TBM Studio tracks lineage through the pipeline’s sequential step model. Because each step’s
output feeds the next step’s input, the chain of transformations is always explicit and inspectable.
The model diagram in Model Studio further extends this lineage by showing how data flows from
transform tables through allocation objects to final business units.

## Transform Design Best Practices

- **Keep master transforms central:** Create a single master dataset (such as a Cost Source
  Master) that unifies multiple source files. Downstream transforms and model objects should reference
  this master rather than individual source files.
- **Avoid duplicating logic:** If multiple tables need the same transformation, create a shared
  intermediate transform rather than repeating the logic in each pipeline.
- **Validate column types early:** Incorrect column typing (for example, a numeric field
  detected as Label) causes errors that propagate downstream. Confirm types during the import step.
- **Use descriptive naming:** Name tables and steps clearly so that other team members can
  understand the pipeline without inspecting each step’s configuration.
- **Monitor for unused tables:** TBM Studio can identify tables that are not referenced by any
  report or model object. Periodically review and clean up unused tables to reduce complexity.
