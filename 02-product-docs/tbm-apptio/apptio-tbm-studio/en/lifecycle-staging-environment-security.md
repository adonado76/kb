---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Staging Environment Security"
breadcrumb:
  - "Concepts and Architecture"
  - "Security Model"
  - "Security Across the Lifecycle"
  - "Staging Environment Security"
source_path: "SSWRJM/studio/new-uc/concepts-architecture/security-model/staging-env-sagfety.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Staging Environment Security

The staging environment serves as a validation gate between development and production.

- Access: Requires the AccessStg permission. Typically granted to Admin and Power User roles.
- Purpose: Validate that security configurations work correctly with real data before deploying to production.
- Testing: Run staging calculations and verify that RLS filters produce the expected results. Use impersonation to test as specific users.
