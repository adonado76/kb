---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Asset Planning Overview"
breadcrumb:
  - "Planning"
  - "Asset Planning"
source_path: "it-planning/planning/manage-assets.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Asset Planning Overview

The Asset Planning module enables you to budget, forecast, and manage capital
investments in fixed assets. Fixed assets are long-term tangible resources—such as servers,
hardware, or equipment—that a business owns and uses over multiple years. These assets are
capitalized and depreciated over time rather than expensed immediately.

With Asset Planning, you can:

- Track **CapEx purchases** and the transition to **OpEx depreciation** once assets
  are placed in service.
- Model the **full asset lifecycle** — from acquisition through depreciation,
  maintenance, and retirement.
- Allocate **depreciation expense** by department or cost center for accurate financial
  reporting.
- Apply **depreciation rules and methods** to forecast long-term cost impacts across
  future periods.

## Configure Asset Planning

Note: Admin or Budget Process Owner roles are required.

**Enable Assets** 

- Ensure the **Assets** feature is enabled in: **Settings** (Gear icon) **→
  Company Profile**.

**Asset Class Reference Data**

Asset Class is a key dimension controlling how acquisitions and depreciation are handled.

- Go to **Configuration → Reference Data → Asset Class**.
- You may export a template: **Three-dot overflow menu****→ Export Template**.
- Populate or update columns in the .csv:
- **Asset Class** – Name of the asset category. Must be unique.
- **Depreciation Account** – OpEx account used for depreciation.
- **Purchase Account** – CapEx account used for asset acquisition.
- **Depreciation Method** – Select the method used to depreciate the asset. (e.g.,
  Straight Line, Double Declining, or Declining Balance). Refer to Depreciation
  Methods for more details.
- **Asset Life (months)** – Useful lifespan of the asset in months
- **Residual Value %** – The rate of the original asset cost that is expected to
  remain at the end of its useful life (also known as Salvage Value). Enter as a decimal —
  for example, 1 = 100%, 0.1 = 10%.
- **Balance Rate %** – The rate to depreciate the asset. Used for Declining Balance
  method. Enter as a decimal — for example, 1 = 100%, 0.1 = 10%.
- Import the updated file and **publish**.

## Entering & Managing Asset Line Items

- Open your plan and navigate to the **Assets** tab within the **Expenses** page.
- Add a new asset by either:
- Using the **empty row** at the bottom of the table, or
- **Right-clicking** and selecting **Insert Row**
- Enter the following details for each asset:
- **Asset Class -** Select the category that defines how the asset will be capitalized
  and depreciated. This determines default depreciation rules and accounts.
- **Cost Center -** Choose the cost center that will be financially responsible for the
  asset’s cost and depreciation.
- **Vendor** (optional) - Specify the supplier or vendor associated with the asset
  purchase. This is optional but helpful for reporting
- **Depreciation Method** – The depreciation rule that determines how the asset’s cost
  is expensed over time. This is automatically assigned based on the Asset Class but can be
  manually overridden if necessary.
- **Purchase Date -** The date the asset was acquired or capitalized.
- **In-Service Date -** The date the asset becomes operational. Depreciation begins
  from this date.
- **Purchase Price -** The capital cost of the asset being purchased. This value is
  used to calculate depreciation and total financial impact.
- **Quantity -** the number of asset units being purchased.

Once entered, Apptio Planning will automatically generate the depreciation schedule based
on the asset inputs and depreciation method. You’ll see the depreciation amounts distributed
across the time period columns.

In the **Summary** tab, Apptio Planning creates two financial entries automatically:

- A **purchase entry** using the configured *Purchase Account*
- A **depreciation entry** using the configured *Depreciation Account*

## Depreciation Charged to a Different Cost Center

If the depreciation expense should be assigned to a different cost center than the one that
owns the asset, you can use the **Depreciation Cost Center** field. This reroutes the
depreciation cost to an alternate cost center.

This is useful in scenarios such as when an asset is purchased by a Project cost center, but
ongoing maintenance is funded by a different cost center.

In this case, the asset remains owned by the original cost center, while depreciation is
charged elsewhere.
