---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Create a custom table identifier"
breadcrumb: []
source_path: "studio/model_studio/create-custom-table-identifier.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu607.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Create a custom table identifier

**Applies to**: TBM Studio 12.0 and later. The Apptio modeling environment provides a
flexible framework to manipulate data into groupings that form the basis for allocations and
reporting. Below, the best practices for choosing the right identifier for a given model table will
be explained.

Table identifiers are used to link model tables to an underlying column within a table. The
identifier is similar to a Primary Key in a relational database, and the best practice is to have
the identifier consist of unique values. Unique values support granular reporting and the ability to
drill down to the individual line item.

In choosing an identifier, you should consider the following:

- What is the most granular level of grouping I want to use in this table?
- Can I find a single column that has unique values for each row?
- Do I need to concatenate multiple columns together to achieve uniqueness?
- How does the data backing this table relate to the data in the table(s) that it allocates
  to?

By default, the application creates an identifier that uniquely identifies each row. However, you
can create a custom identifier that provides the level of detail you want to use when allocating
value in the model and when creating reports. For example, you might want to group values by
department, account, or some other value to reduce calculation times and provide higher level
reporting.

To create a custom table identifier:

1. Click the **Model** step in the table transform pipeline.
2. Click the table in the **Single-Table** view of the model.
3. In the **Rows** panel shown in the following image, check the columns you
   want to use to create the identifier. The columns are added to the table at the right. The table
   shows the cost for each row and the amount allocated:![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu607.png)
4. To return the Sankey diagram, click **Close** at the bottom of the pane.
