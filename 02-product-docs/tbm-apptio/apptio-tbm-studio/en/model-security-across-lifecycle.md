---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Security Across the Lifecycle"
breadcrumb:
  - "Concepts and Architecture"
  - "Security Model"
  - "Security Across the Lifecycle"
source_path: "SSWRJM/studio/new-uc/concepts-architecture/security-model/security-across-lifecycle.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Security Across the Lifecycle

TBM Studio’s build and deployment lifecycle (Development → Staging → Production) introduces additional security considerations. Security configurations themselves are subject to the check-in/check-out workflow and must be promoted through environments just like data and models.

## Development Environment Security

The development environment is where models, reports, and security configurations are created and modified.

- Access: Requires the AccessDev permission. Typically granted to Admin and Power User roles.
- Edit permissions: Users must check out objects before editing. The check-out locks the object so others cannot edit simultaneously.
- Security changes: RLS mapping tables, filter configurations, and role definitions can all be modified in the development environment.
- Testing: Use preview filters and impersonation in the dev environment to validate security configurations before promoting.
