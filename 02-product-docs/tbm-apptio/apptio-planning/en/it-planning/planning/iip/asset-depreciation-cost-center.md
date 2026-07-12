---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Delegate Asset Costs"
breadcrumb:
  - "Planning"
  - "Project Planning"
source_path: "it-planning/planning/iip/asset-depreciation-cost-center.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Delegate Asset Costs

Important: Available with the ***Apptio Planning Standard****subscription*

Remember: *Integrated Investment Planning (IIP) feature must be enabled*

The **Delegate Asset Costs** feature allows you to allocate the depreciation portion of
an asset’s cost to a different cost center than the one that owns the asset purchase. This
is useful in project planning scenarios where a project cost center funds the initial
**capital purchase** (e.g., Build phase), while the ongoing **depreciation expense**
is owned by an operational or maintenance cost center (e.g., Run phase).

This delegation ensures that fixed asset costs are accurately attributed to the departments
responsible for maintaining, consuming, or depreciating the asset over time.

## How Asset Cost Delegation Works

Delegating asset expenses has two primary components:

- **Asset Purchase Amount** – Allocated to the **Cost Center** selected on the
  asset line.
- **Depreciation Amount** – Allocated to the **Depreciation Cost Center** selected
  on the asset line.

By choosing a different Depreciation Cost Center, you can delegate ongoing depreciation
costs to another team while keeping the capital purchase in the originating project or cost
center.

## Steps to Delegate Asset Depreciation Costs

1. Go to **Plan** → **Expenses** → **Assets**.
2. Create a new asset or edit an existing one.
3. In the asset line, select the **Depreciation Cost Center**. This cost center will
   receive all system-generated depreciation expenses for the asset.

**Important Notes**

- Depreciation delegation is available only when the **Integrated Investment Planning
  (IIP)** feature is enabled.
- Depreciation is always allocated **entirely** to the selected Depreciation Cost
  Center.
- Unlike contract delegation (which splits expenses by date), asset delegation applies
  **to all depreciation**, starting from the asset’s depreciation schedule.
- You cannot partially delegate depreciation—each asset supports only one Depreciation
  Cost Center.
