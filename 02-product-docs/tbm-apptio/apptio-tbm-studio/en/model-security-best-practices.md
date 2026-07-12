---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Security Best Practices"
breadcrumb:
  - "Concepts and Architecture"
  - "Security Model"
  - "Security Best Practices"
source_path: "SSWRJM/studio/new-uc/concepts-architecture/security-model/security-best-practices.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Security Best Practices

Effective security in TBM Studio requires thoughtful planning and consistent application of security principles. This section provides conceptual guidance and common patterns to help you design a robust security configuration.

## Principle of Least Privilege

The principle of least privilege means granting each user the minimum access necessary to perform their job function. In TBM Studio, this principle applies at every layer:

- Roles: Assign the least-privileged role that meets the user’s needs. Start with Business User and elevate only when required.
- Custom Roles: When creating custom roles, include only the permissions the role actually needs. Avoid copying Admin permissions “just in case.”
- RLS: Restrict data visibility to the narrowest scope appropriate for each user’s responsibilities.
- API Accounts: Create dedicated service accounts with minimal permissions for each integration.
- Report Permissions: Make reports visible to the roles that need them rather than leaving all reports accessible to everyone.
