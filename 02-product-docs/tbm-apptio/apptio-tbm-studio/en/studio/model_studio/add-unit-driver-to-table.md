---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Add a unit driver to a table in a model"
breadcrumb: []
source_path: "studio/model_studio/add-unit-driver-to-table.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu605.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Add a unit driver to a table in a model

**Applies to**: TBM Studio 12.0 and later

There are two ways to add value to a table in a model:

- Use a value column in the table. This is known as a unit driver. Unit drivers most often are
  used at the lowest tier in a model.
- Allocate value to the table from another table. This is known as an allocation. Allocations most
  often are used to flow value from one tier in a model to another.

In the following image, the **Cost Source Actuals** table has two-unit drivers: **OpEx
Variable** and **OpEx Fixed**.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu605.png)

The information below describes how to add a unit driver. For information on allocations, see
**[Create an
allocation](allocate-value-in-model.htm "(Opens in a new tab or window)")**.

To add a unit driver to a table:

1. Click the table in **Project Explorer** and check out the table.
2. Add a **Model** step.
3. Click the **Model** step.
4. In the **Model** workspace, click **Add Unit Driver** under the **Drivers**
   column.
5. Under **Add To**, click the metrics to which the driver will apply.
6. Under **Using**, click the driver type (see below for an explanation of the driver
   types).
7. Complete the driver's definition based on the driver's type you selected:
   - **Column**: select a column
   - **Metric**: select a metric
   - **Formula**: enter a formula

Optionally, under **Notes**, enter information about the driver.

The **Source** and **Destination** tabs in the table on the right side of the dialog show
row by row how the value is being distributed.

## Driver types

There are three types of drivers.

- **Column** - The value is taken from a column in the table. This is the most common type of
  driver.
- **Metric** - The value is taken from another model metric.
- **Formula** - An equation generates the value. The equation can include values from the table
  or other tables.

## Delete a driver

1. Click the driver in the Sankey diagram.
2. Click **Delete** at the bottom of the panel.
