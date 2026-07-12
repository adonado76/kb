---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Quick Reference"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Integrate and Extend"
  - "API Integration"
source_path: "studio/new-uc/howtoguides/integrate-extend/quick-ref.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Quick Reference

## Required Headers for All API Calls (v12.9+)

|  |  |  |
| --- | --- | --- |
| **Header** | **Value** | **Purpose** |
| apptio-opentoken | Your authentication token | Authentication |
| apptio-current-environment | Environment ID | Target environment |
| app-type | Flagship | Required for v12.9+ |
| app-version | NA | Required for v12.9+ |
| Content-Type | Varies by operation | Request body format |

## Supported File Formats

|  |  |  |
| --- | --- | --- |
| **Format** | **Extension** | **Notes** |
| CSV | .csv | Comma-separated values |
| TSV | .tsv | Tab-separated values |
| Compressed CSV | .csv.gz | Gzip-compressed CSV |
| Compressed TSV | .tsv.gz | Gzip-compressed TSV |
| Excel | .xlsx | Download only |

## Related Documentation

- Section 5.5 API Reference: Complete endpoint documentation, parameter details, and response
  schemas
- [Data Import & Management](../work-with-data/data-import-mgmt.html): Manual data upload procedures and
  DataLink configuration
- [User Management](../manage-users-permission/manage-up-intro.html): Setting up API user accounts
  and permission assignments
- [Security
  Model](../../concepts-architecture/studio-model/security-architecture.html): Authentication architecture and security best practices

**Parent topic:** [API Integration](../../../../studio/new-uc/howtoguides/integrate-extend/api-integration.html)
