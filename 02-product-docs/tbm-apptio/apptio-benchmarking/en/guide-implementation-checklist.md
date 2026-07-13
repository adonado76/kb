---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "apptio-benchmarking"
title: "Implementation Checklist"
breadcrumb:
  - "How to Use This Guide"
  - "Implementation Checklist"
source_path: "SSIU957/it-benchmarking/how-to-use/implementation-checklist.html"
images: []
capability_ids: []
last_updated: "2026-07-12"
summary: ""
---
# Implementation Checklist

Before you start

Before you start

- Confirm products are visible in Frontdoor Benchmarking is visible. Costing is visible, if you plan to integrate with it (strongly recommended).
- If integrating with Costing, identify the system-of-record Costing project Select which Costing project will act as the source for IT actual spend. Ownership and change control for the Costing project are clear.
- Assign roles TBM / ITFM Program Lead identified. Primary TBMA / analyst designated as Benchmarking owner. Apptio platform admin identified. Key Resource Tower Owners (e.g.; Compute, Storage, Network, etc) identified.

Data readiness

- Organizational profile data available Latest full-year revenue for the scope of your IT org being benchmarked. Latest full-year FTE (full-time equivalent) for that same scope. Agreed industry classification associated with your IT org. Agreed region (global vs specific region) and size band logic.
- IT spend data ready for at least one full year Annual IT spend mapped into TBM Cost Pools . Annual IT spend mapped into TBM Resource Towers .
- Infrastructure volumes (if using infra benchmarks)* Device / capacity counts by Sub-Tower, for example: Servers (physical / virtual as required) Storage (TB of usable capacity) Network (ports, devices, or relevant units) FTE counts for major infra functions, if you plan to use FTE efficiency metrics.

* If you cannot tick all infra items, you can still start with Industry and OpEx benchmarks and add infra later.

Environment and configuration

- Access verified TBMA / admins can log into IBM Apptio Benchmarking . If Costing is integrated, TBMA / admins can log into the chosen Costing project. Key consumers can at least see Benchmarking reports they are expected to use.
- Taxonomy version set TBM version selected in Benchmarking to match the Costing project. Any non-standard Resource Towers / Cost Pools mapped to standard equivalents or documented exceptions.
- Organizational profile configured in Benchmarking Revenue and headcount entered and match the IT org scope. Industry and region set correctly. Any additional complexity drivers populated if available.
- Cost data connected or loaded If integrated with Costing: Benchmarking is pointing at the correct Costing project. Correct fiscal year / period selected for benchmarks. If not integrated: Annual IT spend by Cost Pool and Resource Tower loaded manually. Currency and fiscal year clearly defined.
- Infrastructure data configured (if applicable) Infrastructure cost mapped to Sub-Towers aligned with benchmark taxonomy. Volume / capacity data loaded for those Sub-Towers. Units of measure validated (GB vs TB, physical vs virtual, etc.)
- Peer group defaults defined Default peer group chosen (industry, size band, region). Any additional filter policies agreed (for example, when to narrow or broaden). Default peer group documented for reuse in exec reporting.

Validation and first use

- Smoke test core views Industry metrics: IT spend vs revenue and vs employees. IT OpEx: Cost Pool and Resource Tower distributions. Infrastructure: At least one unit cost metric (if infra data is configured).
- Sanity checks passed IT spend totals reconcile to Finance for the selected year. No obvious 10x outliers due to unit errors or bad mapping. All major Resource Towers and Cost Pools you expect are present and non-zero. Peer group and year shown match what you intend to discuss.
- Initial stakeholder package prepared 3-5 charts selected: 1 Industry view 1 IT OpEx distribution 1-2 Infrastructure views (if applicable) Short narrative drafted for each: Where we’re in line. Where we differ. Where we plan to investigate further.
- Intro session with sponsor held TBM Lead and TBMA walk sponsor (CIO / VP / Finance) through: What Benchmarking is. Who we are compared to. Key initial findings. Decisions documented: Metrics we will track. Resource Towers / areas we will focus on. How often we will revisit.

Governance and ongoing operations

- Cadence agreed Annual: Full refresh of data and benchmarks aligned to planning cycle. Peer group review and confirmation. Quarterly: Review of key benchmark metrics and Resource Tower gaps in QBR / steering. Ad hoc: Use benchmarks for major business cases and Resource Tower initiatives.
- Change policies defined Require approval (TBM Lead) for: Changing TBM version in Benchmarking. Changing the primary Costing project. Changing the default peer group selections. Adding or removing major cost categories from benchmark scope. Allow TBMA discretion (with documentation) for: Minor mapping corrections. Experimental views with clearly labeled alternate peer groups.
- Documentation in place One-pager saved that captures the following: Costing project used TBM version Default peer group Data refresh cadence Mapping notes for any non-obvious scope decisions, for example: “Telecom spend is included in Network tower.” “Shared service X is allocated entirely to IT Management.” Link to this Benchmarking Help guide shared with TBMAs, Resource Tower Owners, and key Finance partners.

If all of the above boxes are checked, Benchmarking is not just technically configured, it is actually usable, explainable, and governed.
