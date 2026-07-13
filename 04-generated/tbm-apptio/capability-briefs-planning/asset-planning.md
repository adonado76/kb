---
concept: "Asset Planning (CapEx acquisition, depreciation methods, CapEx-to-OpEx transition)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-planning
status: draft
generated_from:
  - 02-product-docs/apptio-planning/en/it-planning/planning/manage-assets.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/depreciation-method.md
last_updated: "2026-07-05"
---
# Asset Planning — How IBM Apptio Planning Addresses This TBM Capability

## The capability

Fixed assets — servers, hardware, equipment — are acquired as a capital expense but consumed as
an operating expense over their useful life. TBM's cost model depends on this transition being
modeled explicitly: a service's period cost should reflect the depreciation hitting this month,
not the full purchase price landing all at once in the month of acquisition. This is the same
principle already established elsewhere in this knowledge base for Costing Standard — service
costing uses the amortized/depreciated portion of capex, not the lump-sum capital amount, so that
period-over-period service cost comparisons stay meaningful. Asset Planning is where that
transition is modeled on the forward-looking (budget/forecast) side, rather than the
actuals/reporting side.

## How Apptio Planning solves it

**Asset Class drives default behavior.** Each Asset Class in reference data pre-defines the
Depreciation Method, the CapEx Purchase Account, the OpEx Depreciation Account, the Asset Life (in
months), Residual Value % (salvage value), and — for declining-balance methods — a Balance Rate
%. A new asset line inherits all of this from its class, keeping depreciation assumptions
consistent across every asset of the same type without per-line reconfiguration.

**Six depreciation methods cover both linear and accelerated patterns.** Straight Line (even
monthly spread based on Purchase Price × (1 − Residual Value) ÷ Asset Life) and its Calendar-Days
variant (day-prorated for partial periods) handle the common linear case. Double Declining and
the more flexible Declining Balance (with a configurable Balance Rate — 200% Balance Rate
reproduces Double Declining, and is the recommended way to model it, since Double Declining
recalculates book value at the start of every period rather than annually) model accelerated
depreciation, where expense is front-loaded into the asset's early life — relevant for hardware
categories where real economic value erodes faster upfront. Declining Balance Using Calendar Days
combines the accelerated pattern with day-level period accuracy. Manual Depreciation exists as an
escape hatch for assets whose depreciation schedule doesn't fit any system-calculated pattern.

**Two automatic financial entries per asset.** Once an asset line is entered (Asset Class, Cost
Center, Purchase Date, In-Service Date — which is when depreciation actually starts, not the
purchase date — and Purchase Price), the Summary tab automatically generates both a **purchase
entry** (CapEx, hitting the Purchase Account) and a **depreciation entry** (OpEx, hitting the
Depreciation Account, spread per the selected method). This dual-entry structure is what keeps
the investment/portfolio view (full capex visible) and the service-run view (only the periodic
depreciation flows) both available from a single planning action.

**Depreciation cost center delegation** mirrors the same pattern seen in Contract Planning: an
asset can be owned by one cost center (e.g., a Project that funded the purchase) while its ongoing
depreciation is charged to a different, operational cost center — separating capital ownership
from the recurring cost accountability.

## Why this matters in a client conversation

This capability is the natural place to