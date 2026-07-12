---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Upgrading Costing Standard"
breadcrumb:
  - "Costing Standard"
  - "Administration"
  - "Upgrading Costing Standard"
source_path: "cost-transparency/admin/upgrade-cs.html"
images:
  - "resources/images/studio_images/ucs-1.png"
  - "resources/images/studio_images/ucs-2.png"
  - "resources/images/studio_images/ucs-3.png"
  - "resources/images/studio_images/ucs-4.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Upgrading Costing Standard

The upgrade process for Costing Standard involves updates to the following
layers.

![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/ucs-1.png)

## Platform layer

The platform (or Apptio code base), called TBM Studio, is a set of features and capabilities
that allow you to perform tasks that drive the Apptio applications, such as creating models,
uploading data sets, allocating costs, and creating reports. TBM Studio also includes the
Apptio calculation engine.

The goal is to upgrade all Server 12.x customers to the latest release each quarter. In an
effort to keep our applications updated with the latest features and performance enhancements,
we schedule mandatory maintenance during a specific date range. For dates, contact your
Customer Success Manager or refer to this [schedule](https://community.ibm.com/community/user/viewdocument/tbm-studio-and-applications-r12-rel "(Opens in a new tab or window)")

**Versioning**. R12 is a shortcut referring to the current version of TBM Studio base
product. Incremental releases of TBM Studio are represented as 12.11.x . To upgrade to a new
version of TBM Studio, contact your Customer Success Manager.

To see the version of Server Version you are running, select ![](_-1365910950.) > About.

The following window displays the Server Version:

![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/ucs-2.png)

## Applications layer (Content)

Applications are pre-defined components that use platform capabilities to achieve a use
case. Application components may contain the following content elements:

- Master data sets
- Model objects
- Taxonomy
- Metrics
- Perspectives
- Reports

**Versioning**. The versioning for Apptio applications is reflected as template
versions. Template v120, for example, is the latest template version number. It's possible
to use earlier template versions (for example, Template v107, or Template v109) on the
latest server version.

To see the version of template you are running, open TBM Studio and select *Project >
Project Settings*.

The Edit Project Settings dialog opens, displaying the component version.

![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/ucs-3.png)

## Upgrade guidance

Application updates are at your discretion:

- Move to a new application template if you want to use the latest features and
  enhancements introduced by that template.
- You can choose to remain on your current application template version, even after
  getting upgraded to the latest server version. For example, you can choose to remain on
  Template v109, even if the latest server version has Template v120
- You can skip template versions. For example, you can upgrade from application Template
  v107 to v110, skipping Template v109.
- You can choose to upgrade only few components whose latest features are interested to
  you. Be careful, on the dependencies of the components available on the component
  installation screen or configuration guide.

Note: To access a current application template, you must upgrade to the minimum platform
release that supports that template. For example, you can't access Template v106 unless you
are on TBM Studio 12.6 and later.

![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/ucs-4.png)

You must upgrade TBM Studio before you upgrade the application template.

For step by step instructions to upgrade template, go [here](con-ver-lay.html).

## TBM Taxonomy layer

The TBM Taxonomy is a framework for allocating IT costs in a standard approach that allows
technology leaders to run and optimize IT as a business. Upgrading from one version to
another is a customer-driven decision and is not directly related to the platform or content
upgrades. Reference files for each ATUM version are available in the product. Moving from
one ATUM version to another requires changes to data and allocation strategies to map costs
to the new categories.
