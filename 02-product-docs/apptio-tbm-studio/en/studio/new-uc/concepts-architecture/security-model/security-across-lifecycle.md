---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Security Across the Lifecycle"
breadcrumb:
  - "TBM Studio"
  - "Concepts and Architecture"
  - "Security Model"
source_path: "studio/new-uc/concepts-architecture/security-model/security-across-lifecycle.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Security Across the Lifecycle

TBM Studio’s build and deployment lifecycle (Development → Staging → Production) introduces
additional security considerations. Security configurations themselves are subject to the
check-in/check-out workflow and must be promoted through environments just like data and models.

## Development Environment Security

The development environment is where models, reports, and security configurations are created and
modified.

- **Access:** Requires the AccessDev permission. Typically granted to Admin and Power User
  roles.
- **Edit permissions:** Users must check out objects before editing. The check-out locks the
  object so others cannot edit simultaneously.
- **Security changes:** RLS mapping tables, filter configurations, and role definitions can all
  be modified in the development environment.
- **Testing:** Use preview filters and impersonation in the dev environment to validate
  security configurations before promoting.

- **[Staging Environment Security](../../../../studio/new-uc/concepts-architecture/security-model/staging-env-sagfety.html)**
- **[Production Environment Security](../../../../studio/new-uc/concepts-architecture/security-model/prod-env-security.html)**
- **[Security and the Check-In/Check-Out Workflow](../../../../studio/new-uc/concepts-architecture/security-model/security-checkin.html)**
