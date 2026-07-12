---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Understanding the Three Environments"
breadcrumb:
  - "Concepts and Architecture"
  - "Build and Deployment Lifecycle"
  - "Understanding the Three Environments"
source_path: "SSWRJM/studio/new-uc/concepts-architecture/understand-environments.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Understanding the Three Environments

TBM Studio organizes work into three distinct environments, each serving a specific purpose in the development-to-production workflow. All three environments are accessible from a single URL through the Environment menu in the toolbar.

Development Environment

The Development environment is your personal workspace for making changes. When you check out a document and begin editing, you automatically enter the Development environment. Key characteristics include:

- Isolation: Your edits are local to your workspace. Other users cannot see your changes until you check them in.
- Real-time calculation: When you save changes, TBM Studio calculates transforms and metrics so you can validate your work immediately.
- Multiple workspaces: If other users have documents checked out, their development environments appear in the Environment menu. With appropriate permissions, you can view or even edit documents in another user's workspace.
- Automatic switching: When you have no documents checked out, TBM Studio automatically switches you to the Staging environment.

Staging Environment

The Staging environment aggregates all checked-in changes from all users. It serves as the integration and validation layer before production. Key characteristics include:

- Shared state: All edits from all users are combined here after check-in.
- Full calculation: After each check-in, Stage performs a complete calculation including drills and reports.
- Validation gateway: Administrators validate changes in Staging before promoting to Production.
- Lock capability: Staging can be locked to prevent new check-ins during the promotion process.

Stage calculation nodes are provisioned on demand, which can take up to 15 minutes. The calculation itself runs after provisioning is complete.

Production Environment

The Production environment contains the validated, approved version of your project that end users consume. Key characteristics include:

- Read-only for most users: View-only users always see Production. They cannot see Staging or Development environments.
- Controlled updates: Only administrators can promote content from Staging to Production.
- Near-instant promotion: In TBM Studio 12.x, promotion to Production is nearly instantaneous.
- Visibility depends on promotion: Production only appears in the Environment menu after Stage has been promoted at least once.

Environment Comparison

| Aspect | Development | Staging | Production |
| --- | --- | --- | --- |
| Aspect | Development | Staging | Production |
| Purpose | Individual editing | Integration & validation | End-user consumption |
| Visibility | User-specific | All editors | All users |
| Calculates | Transforms, Metrics | Transforms, Metrics, Drills, Reports | Receives promoted builds |
| Who can edit | Power Users, Admins | N/A (receives check-ins) | N/A (receives promotions) |
