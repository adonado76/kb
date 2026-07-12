---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Account Structure by Vendor"
breadcrumb:
  - "Optimize"
  - "Understanding Commitment Management Basics in Cloudability"
  - "Account Structure by Vendor"
source_path: "SSVCLNQ/product/commitments_vendor_account_structure.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Account Structure by Vendor

## Purpose

The purpose of this document is to bring cloud account hierarchy to the practical level. It is crucial to understand how account structure impacts commitment sharing, visibility, and reporting across Cloudability Commitments. If you have not already, review the formal account definitions in How Commitment Management Differs Across Cloud Service Providers .

## Why Account Structure Matters to Commitments

Commitment benefits flow according to provider specific scopes (org, billing profile, project, region/AZ). Cloudability maps these hierarchies to:

- Compute KPIs correctly at the different levels of relevance.
- Recommend purchases at the correct sharing boundary based on preferences.
- Provide our users the ability to properly credential their accounts to systematically pull the appropriate data necessary.

Failure to properly credential and set up preferences may result in incorrect assumptions and recommendations that could lead to a incorrect reporting or worse, an erroneous purchase. Further, public APIs rarely provide sharing preferences systematically. This requires manual input to ensure both the portfolio and recommendations align with how discounts are actually applied.

## How Cloudability Maps Your Account Hierarchies

Cloudability ingests provider metadata and normalizes it to a few core ideas used across the app.

Payer Account - The invoice owner and common place where commitments are often formally billed. Note that often the commitment can be purchased at either the payer or linked account level. If sharing is turned on, the commitment will typically be shared across linked accounts on the payer.

Linked Account - Where resources run and usage occurs.

In product, our goal is to deliver a hierarchical and multi-select account selection across all pages. While at the time of writing this, we haven't fully supported this functionality, our plans are to make do on this commitment. For now, the pages address as follows:

Commitment Manager - Aggregates data across vendor accounts. Allows for multi-select. For, both the actual (historical) and forecasted (future) data, the account selection acts as a usage picker.

Commitment Portfolio - Shows per type summaries and details by account/subscription/project.

Commitment Recommendations - Respects your sharing intent (org wide vs. scoped) and account filters.

## AWS

Account Structure

Management (payer) account - Receives the consolidated bill; often the purchasing account for RIs/Savings Plans.

Member accounts (linked) - Where resources run and costs are generated.

Organizational Units (OUs) - Hierarchical “folders” for policy and governance (not billing containers). Not of particular interest for commitments.

Sharing behavior

Commitment sharing is an organization level setting. When enabled, discounts can automatically apply across member accounts, regardless of OU placement.

Region sharing is relevant to commitments where workloads and be deployed and commitment purchased at the region or availability zone.

## Azure

Account Structure

Billing Account (EA/MCA) - Top-level contract construct.

Billing Profile (MCA) - Invoice owner; often your primary sharing boundary.

Invoice Section (MCA) - Sub invoice buckets used for allocations/show back.

Subscription - Resource container and unit of billing.

Sharing behavior

Shared scope applies benefits across a billing context (e.g., EA Enrollment or MCA Billing Profile / Invoice Section)

Single Subscription or Single Resource Group limits benefits to that scope

## GCP

Account Structure

Billing Account - Where commitments and credits are managed; invoice owner.

Project - Resource container where workloads run and costs are generated.

Sharing behavior

Sharing must be turned on in the GCP console. It is managed at the Billing Account level.

Region is relevant to GCE Resource CUDs and some Spend CUDs such as Cloud SQL CUDs.

## Tips

1. Credential the right payer accounts first; confirm linked accounts and review any special permissions per service.
1. Set your account sharing settings per payer in commitment preferences to ensure correct sharing settings are defaulted to in recommendations.
1. Verify sharing is enabled at the payer level before trusting org wide coverage in Portfolio.
1. Confirm sharing settings and set them in the commitment preferences.
1. Periodically verify these settings.

## Takeaways

Account structure is crucial for proper function on Cloudability Commitments. Ensure accounts are correctly credentialed and sharing preferences set such that commitment functionality works properly.
