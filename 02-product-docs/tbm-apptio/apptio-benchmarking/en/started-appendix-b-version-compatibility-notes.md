---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "apptio-benchmarking"
title: "Appendix B: Version & Compatibility Notes"
breadcrumb:
  - "Getting Started"
  - "Appendix B: Version & Compatibility Notes"
source_path: "SSIU957/it-benchmarking/version-notes.html"
images: []
capability_ids: []
last_updated: "2026-07-12"
summary: ""
---
# Appendix B: Version & Compatibility Notes

This appendix explains how IBM Apptio Benchmarking lines up with TBM versions and how it interacts with Costing.

Use this when someone asks:

- "What version are we on?"
- "Why did things change after the last upgrade?"
- "Can we reuse our old Benchmarking setup?"

## TBM Taxonomy alignment

IBM Apptio Benchmarking uses the TBM taxonomy and structures to interpret your data and match it to external benchmarks.

TBM version selection

In Interactive Benchmarking’s Configuration you select an ATUM version (corresponding to the TBM Taxonomy version your details are aligned to). That choice controls:

- Which Cost Pools, Resource Towers, and Resource Sub-Towers exist
- How Infrastructure metrics are grouped and labeled
- Which benchmark definitions and mappings are available

Guidelines:

- Match the ATUM version to the TBM version your Costing project is using.
- If you are migrating to a new version… Confirm Interactive Benchmarking supports the new TBM version. If supported, complete the migration on the Costing side before changing Interactive Benchmarking’s configuration.Changing versions without coordination will break comparisons and confuse trends.

Impact on metrics and structure

Version changes can:

- Add, remove, or rename Resource Towers and Resource Sub-Towers
- Move cost elements between Resource Towers or Cost Pools
- Change which metrics are available for each area

From a user perspective:

- Before the change, metrics are based on the old structure
- After the change, metrics are based on the new structure
- In some cases, there is no 1 to 1 translation between the two

Practical implication:

- Mark the version change year as a new baseline.
- Do not pretend that pre-change and post-change values are directly comparable without restating.

## Relationship with Costing

Benchmarking and Costing are closely related but not the same thing.

With Costing integration

When Interactive Benchmarking is integrated with Costing:

- Interactive Benchmarking pulls annual IT cost from a chosen Costing project.
- That project must use TBM Cost Pools and Resource Towers that align with the selected TBM version.
- Infrastructure benchmarks depend on Resource Sub-Tower level mappings if you want unit cost metrics.

Benefits:

- You get consistent numbers between Costing and Benchmarking.
- You can drill from benchmark gaps down to accounts, vendors, applications, or services.
- You can keep one system of record for IT cost.

Risks if misaligned:

- Benchmarks will reflect a subset or distorted view of IT cost.
- Executive conversations will stall on reconciliation instead of decisions.

Without Costing integration

You can use Benchmarking without Costing by loading annual costs manually or via file.

You can still:

- Use Industry and IT OpEx benchmarks
- Use some Infra benchmarks if you supply cost and volume by Resource Sub-Tower

Limitations:

- No drill back to GL, vendors, or services inside Costing
- Data refresh is more manual and time consuming
- More room for scope and mapping inconsistencies

This approach can be fine for a pilot. For sustained use, integration with Costing is strongly preferred.

Keeping Benchmarking in sync with Costing

When Costing changes in ways that affect Benchmarking:

- New or restructured towers
- Major reclassifications
- Scope changes (for example adding cloud, telecom, or new business units)

You should:

- Review Benchmarking configuration and mappings.
- Revalidate a small standard set of benchmark views.
- Document that a modeling change occurred for that year.

If you skip this, you will see unexplained jumps in benchmark views that are really model changes, not operational changes.
