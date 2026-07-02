---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Configure Drivers for Allocations"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Build Cost Models"
  - "Create Allocations"
source_path: "studio/new-uc/howtoguides/build-cost-model/config-drivers.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configure Drivers for Allocations

**Objective:** Create allocation drivers that precisely control how costs flow from
source to target tables using matching conditions and weighting columns.

**When to use:** You need granular control over allocation behavior, including matching
costs to specific target rows based on shared attributes (like Vendor ID or Account) and
applying custom weighting logic.

**Time estimate:** 20-30 minutes

## Understanding Drivers

Drivers determine the mechanics of cost distribution. There are two types:

**Unit Drivers:** Define how value enters a model object from its underlying data. Unit
drivers reference columns in the source table.

**Allocation Drivers:** Define how value flows from one model object to another.
Allocation drivers specify matching logic and weighting behavior.

## Step-by-Step: Configure an Allocation Driver with Matching

**Scenario:** Allocate vendor costs to technology services, matching on Vendor ID and
Account, weighted by an "Allocation Weighting" column.

1. **Open the source table's Model step**
   - Navigate to the source table (e.g., "Vendors") in Project Explorer.
   - Click the Model step in the transform pipeline.
2. **Create or edit the allocation**
   - Click Add Allocation or select an existing allocation to edit.
   - Set: Allocate = Cost, Using = Weighted Value, To = Technology Services.
3. **Configure matching conditions (Data Relationship)**
   - Under Data Relationship, click to add matching columns.
   - Add pairs: Vendor ID → Vendor ID, Account → Account, Expense Type → Expense Type.

   Note: Both columns must exist in their respective tables. Values must match exactly for
   costs to allocate.
4. **Set the weighting column**
   - Under Weight By, select Table.
   - Choose the weighting column (e.g., "Allocation Weighting").
   - Ensure this column contains numeric values with no nulls or negatives.
5. **Preview and verify**
   - Click Preview to examine the allocation results.
   - Review for any unallocated rows (rows without matching targets).
6. **Save the driver configuration**
   - Click Save to confirm the allocation.
   - Check in the table when all allocations are complete.

## Driver Configuration Best Practices

**Keep driver tables small and clean**

- Include only columns needed for matching and weighting.
- Remove unused columns to improve performance.
- Document the driver's purpose for future maintainers.

**Use explicit matching over automatic**

- Automatic matching (legacy feature) can produce unexpected results.
- Always specify explicit source and target column pairs.
- If you see "Automatic relationship" checkbox, clear it and configure explicit keys.

**Verify data types match**

- Matching columns should have the same data type (text to text, number to number).
- Text matching is case-sensitive.
- Trim whitespace from text columns in Data Studio if matching fails unexpectedly.

## Driver Types Reference

|  |  |  |
| --- | --- | --- |
| **Driver Type** | **Definition** | **Example Use Case** |
| **Column** | Value taken from a column in the table | Server count, square footage, user count |
| **Metric** | Value taken from another model metric | Use Cost metric to weight Budget allocation |
| **Formula** | Calculated value using a custom formula | Complex weighting logic, conditional distribution |

**Parent topic:** [Create Allocations](../../../../studio/new-uc/howtoguides/build-cost-model/create-allocation.html)
