---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Learning Paths for Administrators"
breadcrumb:
  - "TBM Studio"
  - "Learning Paths (Role-Based)"
source_path: "studio/new-uc/learning-path/lp-admin.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Learning Paths for Administrators

**Objective:** Configure, secure, optimize, and maintain TBM Studio for your
organization

**Who this is for:** TBM Studio administrators, platform managers, and anyone responsible
for system configuration, user management, and production support

## Foundation (1 hour)

**What you**'ll learn: Administrator responsibilities and core platform concepts

**Learning objectives:**

- Understand the administrator role and responsibilities
- Learn the user roles and permissions model
- Understand the development lifecycle (Dev → Stage → Prod)
- Navigate administrative interfaces
- Recognize key platform concepts

**Topics to complete:**

1. **Admin Responsibilities Overview** (15 min) *→ Section 6.1*
2. **User Roles and Permissions** (15 min) *→ Section 6.2*
3. **Development Lifecycle** (20 min) *→ Section 4.5*
4. **Platform Architecture** (10 min) *→ Section 4.2, 4.3*

**Prerequisites:** Basic understanding of TBM Studio (recommend completing Quick Start
tutorial)

## Essential Skills (4 hours)

**What you**'ll learn: Day-to-day administrative tasks including user management,
permissions, builds, and security

**Learning objectives:**

- Create and manage users and roles
- Configure project settings
- Execute check-in and build processes
- Manage the development-to-production workflow
- Implement row-level security (RLS)
- Monitor and troubleshoot builds

**Topics to complete:**

1. [Manage Users and
   Roles (45 min)](../howtoguides/manage-users-permission/manage-up-intro.html)
2. **Configure Projects** (30 min) *→ Section 6.1*
3. **Master Check-In Workflow** (45 min) *→ Section 4.5*
4. **Build and Promotion Process** (60 min) *→ Section 4.5*
5. [Implement Row-Level
   Security](../howtoguides/manage-users-permission/implement-rls.html) (45 min)
6. **Monitor System Health** (15 min) *→ Section 6.4*

**Prerequisites:** Foundation completed, admin access to a project

**Estimated practice time:** Add 2-3 hours practicing in dev environment

## Advanced (6 hours)

**What you**'ll learn: Performance tuning, complex security scenarios, disaster
recovery, and platform optimization

**Learning objectives:**

- Optimize build performance and calculation times
- Manage components and dependencies
- Troubleshoot complex build issues
- Handle disaster recovery and rollback
- Configure advanced data freshness and automation
- Implement branching strategies
- Tune platform for optimal performance

**Topics to complete:**

1. **Performance Optimization** (90 min) *→ Section 6.4*
2. **Component Management** (45 min) *→ Section 6.1*
3. **Advanced Build Troubleshooting** (60 min) *→ Section 7.1, 7.3*
4. **Disaster Recovery and Rollback** (45 min) *→ Section 4.5*
5. **Advanced Data Freshness** (30 min) *→ Section 6.4*
6. **Branching Strategies** (45 min) *→ Section 4.5*
7. **Security Hardening** (45 min) *→ Section 6.3*

**Prerequisites:** Essential Skills completed, hands-on experience with production
support

**Common challenges:**

- **Slow builds:** Use Calc Explorer, simplify models, review transform complexity
- **RLS not working:** Verify mapping table accuracy, check role assignments
- **Promotion failures:** Validate in Stage thoroughly, check for environment
  differences
- **User complaints about access:** Review permissions systematically, use
  impersonation to verify
