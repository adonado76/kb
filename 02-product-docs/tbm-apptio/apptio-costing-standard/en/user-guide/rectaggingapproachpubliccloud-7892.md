---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "user-guide"
title: "Apptio recommended tagging approach for Public Cloud IaaS/PaaS services"
breadcrumb: []
source_path: "user-guide/rectaggingapproachpubliccloud-7892.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Apptio recommended tagging approach for Public Cloud IaaS/PaaS services

Tagging in a public cloud environment is a vital way to apply more informative
information to your cloud resources. Without tagging information, cloud-provider bills will include
information about the provider services and potentially the accounts responsible for deploying the
resources only. By tagging information, you can get more descriptive information about the
resources, such as the application consuming that resource, the environment supported by the
resource, and the individual who owns the resource. All are examples of information that is
generally associated with resource tags.

- Applies to: Apptio Costing Standard or Apptio Cloud Cost Management running on TBM Studio
  v12.3.3 or later.

Apptio’s Costing Standard Cloud Service Provider object includes some pre-defined attributes that
are likely candidates to be populated with tags. The list of those attributes are as follows:

- Consumer

  Note: Depending on how enterprises are organized, Consumer, in many
  cases, can be populated by a non-tag attribute, such as a linked account for Amazon Web Services
  (AWS) or an account for Microsoft Azure.
- Application
- Environment
- Purpose
- Cost Center
- System Owner
- Project

Apptio recommends that enterprises configure tags to capture information associated with at least
some of the attributes listed above using the means appropriate for the provider. Please discuss
with your provider and cloud infrastructure owners for more information on configuring tags. The
following links are associated with popular providers:

- [AWS](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/billing-what-is.html "(Opens in a new tab or window)")
- [Azure](https://docs.microsoft.com/en-us/azure/azure-resource-manager/management/tag-resources?tabs=json "(Opens in a new tab or window)")
- [Google Cloud](https://cloud.google.com/compute/docs/labeling-resources "(Opens in a new tab or window)")

These attributes can then be used as dimensions within your analytics and/or as dimensions by
which costs are allocated. The following image shows using the Application attribute as a pivotable
value to examine your cloud costs by consuming application.![](../../resources/images/ct_images/7892_1.png)![Using Application attribute as a pivotal be value]()

Additionally, the Application attribute is often a means by which the costs should be allocated
up to the appropriate application to drive an application TCO inclusive of public IaaS/PaaS
spend.

**Parent topic:** [Costing Standard](../home.html)
