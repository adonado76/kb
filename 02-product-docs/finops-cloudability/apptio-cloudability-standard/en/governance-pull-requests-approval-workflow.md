---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Pull Requests - Approval Workflow"
breadcrumb:
  - "Governance"
  - "Pull Requests - Approval Workflow"
source_path: "SSVCLNQ/admin/governance-pull-requests-and-approval-workflow.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Pull Requests - Approval Workflow

Governance integrates with GitHub to manage PR approvals. As a reminder, PRs that don’t comply with the “Gated” enforcement level are blocked but they can be unblocked by users with the “Cloudability Governance PR Approver” role.

GitHub Configuration

GitHub repository owner needs to create a branch protection rule which requires Governance check runs to pass before merging.

1. Navigate to the "Pull Requests" tab in the Governance dashboard and review PRs that require approval. Only PRs that are “open” and that have a “failed” status can be approved.
1. Select the PR and click "Approve."
1. In GitHub, the PR check run status updates to "Pass," allowing the Cloud Engineer to merge that change.
