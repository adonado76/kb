---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Quick Reference"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "Integrate and Extend"
  - "API Integration"
  - "Quick Reference"
source_path: "SSWRJM/studio/new-uc/howtoguides/integrate-extend/quick-ref.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Quick Reference

## Required Headers for All API Calls (v12.9+)

| Header | Value | Purpose |
| --- | --- | --- |
| Header | Value | Purpose |
| apptio-opentoken | Your authentication token | Authentication |
| apptio-current-environment | Environment ID | Target environment |
| app-type | Flagship | Required for v12.9+ |
| app-version | NA | Required for v12.9+ |
| Content-Type | Varies by operation | Request body format |

## Supported File Formats

| Format | Extension | Notes |
| --- | --- | --- |
| Format | Extension | Notes |
| CSV | .csv | Comma-separated values |
| TSV | .tsv | Tab-separated values |
| Compressed CSV | .csv.gz | Gzip-compressed CSV |
| Compressed TSV | .tsv.gz | Gzip-compressed TSV |
| Excel | .xlsx | Download only |

## Related Documentation

- Section 5.5 API Reference: Complete endpoint documentation, parameter details, and response schemas
- Data Import & Management : Manual data upload procedures and DataLink configuration
- User Management : Setting up API user accounts and permission assignments
- Security Model : Authentication architecture and security best practices
