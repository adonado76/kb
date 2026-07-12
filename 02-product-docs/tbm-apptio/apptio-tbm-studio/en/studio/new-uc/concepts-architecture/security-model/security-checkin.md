---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Security and the Check-In/Check-Out Workflow"
breadcrumb:
  - "TBM Studio"
  - "Concepts and Architecture"
  - "Security Model"
  - "Security Across the Lifecycle"
source_path: "studio/new-uc/concepts-architecture/security-model/security-checkin.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Security and the Check-In/Check-Out Workflow

Security-related objects (such as RLS configurations, report permissions, and role-based
component visibility settings) follow the same check-in/check-out workflow as other TBM Studio
objects. This means:

- You must check out a table to add or modify its RLS step.
- Checking in the modified table triggers a recalculation that applies the new RLS rules.
- Other users see the updated security configuration only after the calculation completes.
- RLS mapping tables in the Row-Level Security project also follow the check-out/check-in pattern.

Note:

**Best Practice: Security Change Management**

Treat security changes with the same rigor as model changes. Document what was changed and why,
test thoroughly in development and staging before promoting to production, and verify the results
after promotion. A misconfigured RLS rule can either expose sensitive data or hide data that users
need to do their work.

**Related Concepts:** For a detailed explanation of the build and deployment lifecycle,
see[Build & Deployment Lifecycle](../build-deployment.html). For
step-by-step procedures for managing users and configuring security, see Section 3.4 Manage Users
& Permissions and [User
Management](../../admin/user-management.html) and [Security &
Compliance](../../admin/sec-comp.html).

**Parent topic:** [Security Across the Lifecycle](../../../../studio/new-uc/concepts-architecture/security-model/security-across-lifecycle.html)
