---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Drivers"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Model Studio Reference"
source_path: "studio/new-uc/reference/model-studio-reference/drivers.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Drivers

Drivers bring value into a model object and determine how that value is distributed. They are the
primary mechanism for connecting source data to the cost model.

## Driver Types

TBM Studio supports three types of drivers, each serving different allocation needs.

**Unit Driver**

**Description:** A unit driver brings value into a model object from a column in the
underlying table. Unit drivers are typically used at the lowest tier of a model where financial data
enters the system.

**Unit Driver Configuration**

|  |  |  |  |
| --- | --- | --- | --- |
| **Parameter** | **Required** | **Values** | **Description** |
| Name | Yes | Text string | Display name for the driver |
| Add To | Yes | Metric selection | Which metrics this driver applies to |
| Using | Yes | Column, Metric, Formula | Source of the driver value |
| Notes | No | Text string | Documentation for the driver |

**Using Options**

|  |  |  |
| --- | --- | --- |
| **Option** | **Source** | **Use Case** |
| Column | Value from a column in the table | Most common. Direct mapping from cost/budget column |
| Metric | Value from another model metric | When driver depends on another calculated metric |
| Formula | Calculated value from formula | Complex calculations or cross-table references |

**Example: Creating a Unit Driver**

To create a unit driver for OpEx costs:

1. Check out the table and click the Model step
2. In the Model workspace, click Add Unit Driver under the Drivers column
3. Under Add To, select the Cost metric
4. Under Using, select Column and choose the OpEx column
5. Save changes

*→ See Section [Add
unit drivers for detailed procedure](../../howtoguides/build-cost-model/adv-model.html)*

**Allocation Driver**

**Description:** Allocation drivers appear on the left side of the model edit workspace and
represent incoming allocations from other model objects. They are created automatically when you set
up an allocation from a source object to a target object.

**Note:** Allocation drivers are displayed in parentheses when using default names. Custom
names remove the parentheses.

**Formula Driver**

**Description:** A formula driver uses a calculation to determine the value. Formulas can
reference table columns, other metrics, or values from other tables.

**Formula Syntax Examples**

|  |  |
| --- | --- |
| **Purpose** | **Formula** |
| Reference column in same table | table.column name |
| Sum all values in a column | table:column name |
| Conditional sum | table:column[column2="value"] |
| Reference current metric | $\_ (shorthand for metric name) |
| Cross-project reference | project!table:column name |

*→ See Section 5.4: Formulas & Functions for complete formula reference*

- **[Driver Configuration Options](../../../../studio/new-uc/reference/model-studio-reference/driver-config-option.html)**
- **[Driver Data Requirements](../../../../studio/new-uc/reference/model-studio-reference/driver-data-requirements.html)**
- **[Driver Validation Rules](../../../../studio/new-uc/reference/model-studio-reference/driver-validation-rules.html)**
- **[Deleting a Driver](../../../../studio/new-uc/reference/model-studio-reference/delete-driver.html)**
