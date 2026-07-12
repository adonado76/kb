---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Production Environment Security"
breadcrumb:
  - "Concepts and Architecture"
  - "Security Model"
  - "Security Across the Lifecycle"
  - "Production Environment Security"
source_path: "SSWRJM/studio/new-uc/concepts-architecture/security-model/prod-env-security.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Production Environment Security

The production environment is where business users access reports and data.

- Access: Requires the AccessProd permission. Granted to all roles that need to view production reports (including Business Users).
- Read-only for most users: Business Users and most Power Users should only consume reports in production, not modify configurations.
- Change management: Security changes should follow the standard promotion workflow: modify in development, validate in staging, promote to production.
