---
concept: "Contract Planning (vendor obligation modeling, amortization, extensions, VAT)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-planning
status: draft
generated_from:
  - 02-product-docs/apptio-planning/en/it-planning/planning/manage-contracts.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/ammortization-method.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/vrbl-cntc-ext-adj.md
  - 02-product-docs/apptio-planning/en/it-planning/planning/value-added-tax.md
last_updated: "2026-07-05"
---
# Contract Planning — How IBM Apptio Planning Addresses This TBM Capability

## The capability

Vendor and supplier contracts are frequently a large, fixed-obligation slice of IT operating
expense, but they behave differently from labor or discretionary spend: the commitment is often
made once, up front, and needs to be recognized as expense over the contract term rather than as
a single point-in-time cost. Without modeling this explicitly, planning either omits long-term
commitments entirely or shows them as a lump-sum spike at signing rather than a smooth expense
over the period the service is actually being consumed. TBM addresses this through **Contract
Planning**: capturing the commitment, choosing how it accrues over time, and handling renewals,
extensions, and tax treatment consistently.

## How Apptio Planning solves it

**Contract Type drives default behavior.** A Contract Type reference table maps each type to a
default **Amortization Method** and target **Account**, so a new contract line item inherits
sensible defaults (which can still be overridden per line) based on classification alone.

**Five amortization methods cover the realistic range of contract cost patterns.** Straight Line
Even Periods (flat monthly, even for a single-day period at the edges), Straight Line Using
Calendar Days (weighted by days per month), Straight Line Prorate First and Last (only the
boundary months are day-prorated, middle months split evenly), Straight Line By Duration (checks
whether start/end dates cover whole periods; assigns zero to a trailing partial period rather than
prorating it), and Manual Amortization (fully user-defined period-by-period entry, with an
optional Auto-Update Contract Total that keeps the header amount in sync with what's been entered
manually). Having five distinct methods — rather than one generic "spread evenly" rule — matters
because contract terms genuinely vary: a mid-month SaaS renewal amortizes differently than an
annual maintenance contract with a clean fiscal-year boundary.

**Contract Extensions model renewals without re-entering the whole contract.** In the modern
("New View") experience, a contract can carry multiple staged extensions, each with its own
percentage adjustment, and extensions can optionally **compound** — each renewal building on the
prior adjusted value, which is how a realistic multi-year vendor escalation (e.g., a 5% annual
uplift compounding over a 3-year renewal cycle) gets modeled instead of manually recalculating
new dollar amounts each year. Extension data imports/exports as a separate file from the base
contract, which is a detail worth flagging operationally since importing contract details alone
does not bring extensions with it.

**Cost center delegation** lets the amortization expense land on a different cost center than the
one that formally owns the contract (e.g., a project cost center that purchased a multi-year
license, but the ongoing run cost should charge an operational cost center from a specified date)
— separating contractual ownership from cost accountability.

**VAT handling** is automatic once enabled: a contract line's Location drives a lookup into a VAT
Rates reference table, producing an "Amount with VAT" alongside the pre-tax amount, while
amortization always operates on the pre-tax figure — keeping tax treatment correctly separated
from expense recognition.

## Why this matters in a client conversation

Contract Planning is a strong entry point for clients whose biggest pain isn't labor but vendor
spend visibility — especially in banking/insurance, where multi-year outsourcing, software
licensing, and managed-service contracts are large and often renewed with escalation clauses that
are hard to track centrally in a spreadsheet. The compounding extension model directly answers
"can this show me what our contract costs will look like three renewal cycles from now, with the
5% uplift clause factored in?" — a concrete, numbers-backed answer beats a manual multi-tab
what-if spreadsheet almost every time.

The five amortization methods are also a useful maturity/scoping lever: a client can start with
the simplest (Even Periods) for a first rollout, then move to Calendar Days or By Duration once
they need more precision — without needing a different tool or a re-platform to get there.

VAT support is worth surfacing early and specifically for any Latin American client with
multi-country operations (Colombia, Mexico, Brazil, etc.), since regional consumption-tax
treatment is a real procurement and reporting requirement, not a nice-to-have — and the
location-driven automatic lookup removes a manual step that's otherwise error-prone across
multiple jurisdictions.

## Source documents

- Contract Planning Overview — `02-product-docs/apptio-planning/en/it-planning/planning/manage-contracts.md`
- Amortization Methods — `02-product-docs/apptio-planning/en/it-planning/planning/ammortization-method.md`
- Contract Extensions — `02-product-docs/apptio-planning/en/it-planning/planning/vrbl-cntc-ext-adj.md`
- Value Added Tax — `02-product-docs/apptio-planning/en/it-planning/planning/value-added-tax.md`

*Nota: versión en español/portugués se genera en una siguiente pasada, una vez confirmes que este formato sirve para tu caso de uso de RFP.*