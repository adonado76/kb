---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Azure Tags"
breadcrumb:
  - "Getting data into Cloudability"
  - "Connect Microsoft Azure"
  - "Azure Tags"
source_path: "SSVCLNQ/admin/azure-resource-group-tags.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Azure Tags

Cloudability supports the below mentioned types of tags for Azure

- Resource level tags These are part of the Azure Export files and no extra permissions are required within Cloudability for enabling these Tags format - cldy:Azure:ResourceTag:<resource tag key>
- Resource group tags To get Resource group tags from Azure, Cloudability needs an additional permissions either management:Reader or Microsoft.Resources/subscriptions/resourceGroups/read on the subscriptions Tags format - cldy:Azure:ResourceGroupTag:<resource group tag key>
- Subscription level tags To get subscription level tags from Azure, Cloudability needs an additional permission subscription:ReadSubscription Tags format - cldy:Azure:SubscriptionLevelTag:<subscription tag key>

Task : Enable access to resource group tag information to support cost allocation activities.

Using Azure resource group tags has become a popular primary allocation mechanism with large number of Azure users. It overcomes the duel problems of low tag coverage and the fact that Azure doesn't report back tag information for all resource types. Resource group tags don't natively appear in the detailed billing information and therefore, it's necessary to grant additional access as specified on this page.

Cloudability has a tag inheritance model for Azure: if an individual resource has a particular tag in the detailed billing data, we'll use that first to populate our analytics platform. If that tag doesn't appear in the billing data for that resource, Cloudability will then query the resource group it belongs to and pull the tag information from there. If the tag doesn't exist in the resource group, we'll consider it as "(not set)."

To enable the collection and processing of resource group tags, follow the steps here to credential your subscriptions.
