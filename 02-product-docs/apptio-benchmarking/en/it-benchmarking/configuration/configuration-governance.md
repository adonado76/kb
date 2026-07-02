---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "it-benchmarking"
title: "Configuration governance"
breadcrumb:
  - "Benchmarking"
  - "Configuration Guide"
source_path: "it-benchmarking/configuration/configuration-governance.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Configuration governance

Configuration decisions impact trust. Treat them like real changes, not casual preferences.

Recommended practices:

- Keep a short configuration summary for each environment:
  - Costing project used.
  - TBM version.
  - Peer group(s) selected.
- Maintain a simple change log for Benchmarking settings:
  - Date, change, reason, approver.
- Define approval rules:
  - TBM Lead must approve changes to version, main Costing project, or peer group.
  - TBMA can adjust mappings and minor settings with documentation and basic validation.

If a configuration choice can change an executive slide, it deserves a line in the log.
