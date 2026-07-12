---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Migration Recommendations report collection - HBM"
breadcrumb: []
source_path: "cost-transparency/reports-v104/hbmmigrationscollection.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Migration Recommendations report collection - HBM

- Applies to: Hybrid Business Management on TBM Studio TBM Studio and later

Use the Migration Recommendations reports to refine your strategy for migrating from on-premises
servers to cloud servers. The reports allow you compare your current spend against potential cloud
infrastructure spend. Use this report collection to understand which areas of your current
infrastructure can benefit the most from migration, with actionable, insightful KPIs and high-level
analytics. This information is especially helpful in highlighting the continued value of cloud
migration.

Note:

The prices of cloud services are gathered from the price lists published by each public cloud
provider. Price lists are imported and updated once a month. Prices are blended with discounts,
sales tax, and support costs.

For an introduction to the concepts in HBM, see [About Hybrid Business Management](../home.htm "(Opens in a new tab or window)"). For a full list of reports, see [Hybrid Business Management Reports](../../..hbm-reports.htm "(Opens in a new tab or window)").

This report collection is designed for the following roles:

- Director of IT
- Applications group
- Cloud center of excellence

This report collection aligns to the following business goals:

- Make informed migration decisions supported by data
- Compare costs of on-premises infrastructure with potential cloud infrastructure
- Understand the value of migration

These reports enable you to determine the following:

- Which servers should we migrate first?
- How can we clearly demonstrate the value of migration?
- How should we prioritize migration over time?

## Display the report collection

1. Log in to Apptio.
2. On the **Home** page, click **Hybrid Business Management**.
3. In the Report collection menu, select **Migration Recommendations**. The **Migration
   Summary** report opens.

## Migration Summary report

Use this report to compare your current on-premises server costs with potential cloud service
costs.

This report has the following elements:

**(1) KPIs** - KPIs provide a high-level comparison of your current server spend versus
potential cloud server costs:

- **Current Annual Server Cost** - This KPI shows the overall spend on servers. Spending per
  hour is shown as **Cost per Hr**.
- **Annual AWS Cost** - This KPI shows the potential annual cost of Amazon Web Services (AWS).
  Spending per hour is shown as **AWS Cost per Hr**.
- **Annual Azure Cost** - This KPI shows the potential annual cost of Microsoft Azure. Spending
  per hour is shown as **Azure Cost per Hr**.
- **Annual Google Cost** - This KPI shows the potential annual cost of Google Cloud Provider
  (GCP). Spending per hour is shown as **Google Cost per Hr**.

**(2) Filters** - The following filters are available in this report. These filters are
cumulative, and affect all data on the page, including the KPIs:

- **Application** - Select an application to see the impact of your migration strategy on a
  specific application.
- **Environment** - Select an environment to see the impact of your migration strategy in a
  specific environment.
- **OS** - Select an operating system to see the impact of your migration strategy on a
  specific operating system.
- **Location** - Select a location to see the impact of your migration strategy on the servers
  in a specific location.
- **Virtualization Profile** - Select a virtualization profile to see the impact of your
  migration strategy on a specific type of server.

**(3) Potential Savings by Environment** - Use this chart to view your potential cloud
migration savings per environment. Use the options above the table to show or hide specific
environments.

**(4) Potential Savings by Data Center** - Use this chart to view your potential cloud
migration savings per data center. Use the options above the table to show or hide specific data
centers.

**(5) Potential Savings by Purpose** - Use this chart to view your potential cloud migration
savings per server type (application servers, web servers, database servers, directory servers, and
mail servers).

Questions answered:

- Which cloud service providers are the most cost effective?
- Is it better to move Dev and Test environment workloads first to cloud to allow for
  testing?
- Can we risk downtime in our Production environment, or does it contain sensitive data that we
  don’t want on public cloud?
- Are web servers better to move to cloud?
- Should we consolidate our data centers?

## Workload Migration report

Use this report to show a workload-based view of migration comparison.

This report has the following elements:

**(1) KPIs** - The KPIs in this report are the same as in the Migration Summary report. See
element 1 in the [Migration Summary report](hbmmigrationscollection.html).

**(2) Workloads, Rehost Workloads, and Utilization** - Use the following tabs to view the
costs and usage of migration workloads and rehosted workloads:

- **All Workloads** - Use this chart to compare the cost of your top ten workloads on your
  current on-premises servers versus the cost of running similar (CPU/RAM) compute services in AWS,
  Azure, and GCP. Use the selectors to the right of the chart to control which data is displayed.
  Below the chart, the **Workload Details** table displays detailed data for all of your
  workloads.
- **Rehost Workloads** - Use this chart to view your top ten workloads that are designated to
  be rehosted to the cloud, and to compare the costs of those workloads on on-premises servers versus
  the cost of running similar (CPU/RAM) compute services in AWS, Azure, and Google. Below the chart,
  the **Rehost Workload Details** table displays detailed data for your workloads that are
  designated to be rehosted to the cloud.
- **Utilization** - Use this table to view and compare the costs of all workloads. Click the
  check boxes above the table to add additional columns to the table. This table is similar to the one
  on the **All Workloads** tab, but with additional data displayed.

Questions answered:

- Which cloud service providers are the most cost effective?
- Is it better to move Dev and Test environment workloads first to cloud to allow for testing? Can
  we risk downtime in our Prod environment or does it contain sensitive data that we don’t want on
  public cloud?
- Are web servers better to move to cloud?
- Should we consolidate our data centers?

## AWS Migration report

Use this report to explore migration statistics with additional metadata that AWS provides.

This report has the following elements:

**(1) Filters** - Control which data is displayed in the table by selecting filters. The
filters are cumulative.

**NOTE**: The **Term Type** filter defines how compute services are consumed and paid for,
either On-demand or Reserved. If you select Reserved, the payment type can be All Upfront, Partial
Upfront, or No Upfront.

**(2) Table** - This table contrasts your current server infrastructure with AWS
recommendations.

Questions answered:

- How can we tailor AWS to best meet our needs?
- Which AWS options are available?

## Migration Recommendations - Additional Use Cases

Use this report to explore additional options to adopt as part of a migration strategy.
Currently, two cases are covered. Each case has a table in its own tab.

- The **Tech Refresh** tab focuses on aging servers, which are prime candidates for migration
  to public cloud.
- The **Dev/Test Environments** tab focuses on servers which run test environments. These
  servers can be selectively migrated first at low risk as you continue to evaluate your overall
  strategy.

This report has the following elements:

**(1) KPIs** - The KPIs in this report are the same as in the Migration Summary report. See
element 1 in the [Migration Summary report](hbmmigrationscollection.html).

**(2) Filters** - The first five filters in this report are the same as in the Migration
Summary report. See element 2 in the [Migration Summary report](hbmmigrationscollection.html).

- **Manufacturer** - Select a server manufacturer.

**(3) Recommendations** -Use this table to view on-premises servers which meet certain
criteria related to age. Note that in the image above, no such servers are displayed. Click the
**Dev/Test Environments** tab to view a table which displays development and test servers.

Questions answered:

- Which AWS options are available?
- How can we tailor AWS to best meet our needs?

## Migration Comparison

Use this report to analyze your server infrastructure based on a variety of requirement
combinations.

This report has the following elements:

**(1) KPIs** - The KPIs in this report are the same as in the Migration Summary report. See
element 1 in the [Migration Summary report](hbmmigrationscollection.html).

**(2) Filters** - The filters in this report are the same as in the Additional Use Cases
report. See element 2 in the [Additional Use Cases report](hbmmigrationscollection.html).

**(3) Server Configuration** - Use this table to compare costs of on-premises servers with
potential cloud alternatives, with additional data such as cloud server location. Select the options
above the table to add additional columns to the table.

Questions answered:

- How will the locations of my servers change with migration?
- What is the per hour cost of using a specific cloud server?

## Migration Recommendations - Utilization Comparison

Use this report to analyze your server infrastructure based on a variety of requirement
combinations.

This report has the following elements:

**(1) KPIs** - The KPIs in this report are the same as in the Migration Summary report. See
element 1 in the [Migration Summary report](hbmmigrationscollection.html).

**(2) Filters** - The filters in this report are the same as in the Additional Use Cases
report. See element 2 in the [Additional Use Cases report](hbmmigrationscollection.html).

**(3) Server Configuration** - Use this table to compare costs of on-premises servers with
potential cloud alternatives, with additional data such as cloud server location. Select the options
above the table to add additional columns to the table.

Questions answered:

- How will the locations of my servers change with migration?
- What is the per hour cost of using a specific cloud server?
