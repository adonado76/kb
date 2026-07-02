---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Production Environment Security"
breadcrumb:
  - "TBM Studio"
  - "Concepts and Architecture"
  - "Security Model"
  - "Security Across the Lifecycle"
source_path: "studio/new-uc/concepts-architecture/security-model/prod-env-security.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Production Environment Security

The production environment is where business users access reports and data.

- **Access:** Requires the AccessProd permission. Granted to all roles that need to view
  production reports (including Business Users).
- **Read-only for most users:** Business Users and most Power Users should only consume reports
  in production, not modify configurations.
- **Change management:** Security changes should follow the standard promotion workflow: modify
  in development, validate in staging, promote to production.

**Parent topic:** [Security Across the Lifecycle](../../../../studio/new-uc/concepts-architecture/security-model/security-across-lifecycle.html)
