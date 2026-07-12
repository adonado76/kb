---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Apply formulas to transform data"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Work with Data"
  - "Transform & Enrich Data"
source_path: "studio/new-uc/howtoguides/work-with-data/apply-formula.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Apply formulas to transform data

## Objective

Create calculated columns, transform data types, and apply business logic to your data
before it enters the modeling layer.

## When to use this

Use Formulas when you need to:

- Create derived columns (e.g., Total Cost = Unit Cost × Quantity)
- Convert column types (numeric to label, label to numeric)
- Apply conditional logic (IF statements, categorization)
- Enrich data with lookups to other tables
- Standardize values or format text

## Prerequisites

- Source table with data imported
- Understanding of TBM Studio formula syntax
- Column names and types identified

## Time estimate

10-15 minutes per formula column

## Steps

1. Check out the table in **Project Explorer**.
2. Add a **Formulas** step to the transform pipeline.
3. Click **Add a new column**.
4. Configure the new column:
   - **Type**: Select the column type (Key, Label, Numeric, Date)
   - **Name**: Enter a descriptive column name
   - **Formula**: Enter your formula beginning with =
5. Build your formula using TBM Studio syntax:
   - Reference existing columns using curly brackets: *{Column Name}*
   - Use operators: + - \* / for math, & for text concatenation
   - Apply functions: IF(), Lookup(), Value(), NumberFormat(), etc.
6. Click **Save** to add the column.
7. Review the preview to verify the formula produces expected results.
8. (Optional) To edit an existing formula column, select it from the **Select column to
   edit** dropdown, make changes, and click **Save**.

## Common formula examples

|  |  |
| --- | --- |
| **Use Case** | **Formula Example** |
| Calculate total cost | `={Unit Cost} * {Quantity}` |
| Categorize expenses | ``` =IF({Cost Pool} IN ("FTE                 Labor&","Depreciation&"),"Fixed&","Variable&") ``` |
| Convert numeric to text | `=NumberFormat({Account},"#,###&")` |
| Lookup from another table | ``` =Lookup({Account}, Chart of Accounts,                 Account,   Cost Pool) ``` |
| Add prefix to ID | `="pm-&"&{Asset Tag}` |

## Expected results

New formula columns appear at the top of the column list in the Edit pane. Original table
columns remain at the bottom. The preview shows calculated values based on your formula
logic.

## Common pitfalls

- **"Cannot find column&" error:** Verify column names are exact matches
  (case-sensitive when in curly brackets). If the column name contains special characters,
  it must be enclosed in curly brackets.
- **Type mismatch in lookups:** When using Lookup(), ensure the lookup key columns have
  matching types. Convert if necessary using Value() or NumberFormat().
- **Formula references columns from current Formulas step:** Most formulas can only
  reference columns from prior pipeline steps, not columns created in the same Formulas
  step. Create multiple Formulas steps if you need to build on calculated columns.

**Related tasks**

- Formulas and Functions reference (Section 5.4)
- [Join data from multiple sources](join-data.html)
- [Clean and map data](clean-map.html)

**Parent topic:** [Transform & Enrich Data](../../../../studio/new-uc/howtoguides/work-with-data/transform-enrich-data.html)
