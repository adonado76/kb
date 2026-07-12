---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Infrastructure Analysis by Application"
breadcrumb: []
source_path: "reports/infrastructureanalysisby.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Infrastructure Analysis by Application

This report provides a detailed analysis of the percentage of application use per IT
tower (Compute, Storage, and Service Desk).

This report is designed for:

- Application owners
- Infrastructure owners
- Enterprise architects

The report provides a high-level view of infrastructure across your applications. You can find
details about infrastructure compute storage, as well as a view into cloud data, and service desk
and help desk tickets that are associated with your applications. You can use this report to drill
into data about the underlying servers and storage devices (logical storage units) that are
associated with each application. For example, you could use the data in this report to analyze a
cloud migration effort.

The Infrastructure Analysis by Application report contains the following elements:

![](../../resources/images/ct_images/ct%20report%20collections/infrastructure%20analysis%20by.jpg)

| Key element | Description |
| --- | --- |
| (1) Report collection | This report collection provides the IT financial details you need to review application usage and spend:   - [Application Review report](application-review.html "This report provides an executive overview of the application spend, broken out by app run (operating costs) and app dev (investments) for your top applications, application families, and the underlying infrastructure costs based on the ATUM IT towers (Data Center, Compute, Storage, and Network). A simplified snapshot of any application is available with a quick click in any bar chart.") (open by   default) - [Application Portfolio report](application-portfolio.html "This report expands the information in the Application Review report to the entire application portfolio. This report allows you to see who's responsible for the overall suite of applications in your IT organization, the spend per business unit, cost drivers broken out by IT tower and vendor, and the impact of projects related to the applications.") - [Application List report](#infrastructure_analysis_by "This report provides a detailed analysis of the percentage of application use per IT tower (Compute, Storage, and Service Desk).") - [Infrastructure Analysis by Application](infrastructureanalysisby.html "This report provides a detailed analysis of the percentage of application use per IT tower (Compute, Storage, and Service Desk).")   (described in this page) - [New & Retired Apps](new-retired-apps.html "This report provides data related to your application count, usage, and change YTD.") |
| (2) Slicers | The global slicers in the Applications report collection persist from report to report, so the filters you set in this report could affect what you see in other Applications reports. For more information, see the **Slicers** section in the [Application Review report](application-review.dita "(Opens in a new tab or window)"). |
| (3) Compute Analysis by Application | View the virtualization and environment usage percentages by application. The table provides a virtualization profile analysis with metrics for percentage of physical, virtual, private cloud, and public cloud hours used by each application. There is also an environment analysis showing the percentage of use in each environment (production, development, test, and DR).    Select any item in the Application Name column of the table to go to the [Application Name detail report](../reports-v104/applicationnamedetail.html) with details about that item. |
| (4) Storage Analysis by Application | View storage tier and environment usage percentages per application. The table provides the percentage of Tier 1, 2, and 3 usage, in addition to the percentage of use in each environment (production, development, test, or DR).    Select any item in the Application Name column of the table to go to the [Application Name detail report](https://tbmcouncil.jiveon.com/docs/DOC-9217 "(Opens in a new tab or window)") with details about that item. |
| (5) Service Desk Analysis by Application | View analytics by type of customer contact (incident, problem, change request, or service request) and severity level (critical, high, medium, or low) per application.    Select any item in the Application Name column of the table to go to the [Application Name detail report](../reports-v104/applicationnamedetail.html "(Opens in a new tab or window)") with details about that item. |
| (6) Server Hours, Total OpEx, OpEx per Hour, Environment Details | Use this set of charts and tables to view your overall application spend by server hours, total cost, and cost per server hour per environment or apply filters at the top of the report to see a specific view. |

You can use this report to answer the following questions:

|  |  |  |
| --- | --- | --- |
|  | • | What infrastructure is supporting each application? |

|  |  |  |
| --- | --- | --- |
|  | • | How much infrastructure are applications consuming? |

|  |  |  |
| --- | --- | --- |
|  | • | How much of my application portfolio is running on public cloud infrastructure? |

|  |  |  |
| --- | --- | --- |
|  | • | How has the TCO of an application changed as it has been migrated to public cloud infrastructure? |

|  |  |  |
| --- | --- | --- |
|  | • | What infrastructure costs are associated with my applications? |

|  |  |  |
| --- | --- | --- |
|  | • | What are the servers associated with my applications by environment? |

|  |  |  |
| --- | --- | --- |
|  | • | What storage tiers are associated to my apps by environment? |

|  |  |  |
| --- | --- | --- |
|  | • | Which applications are using non-standard infrastructure products? |

|  |  |  |
| --- | --- | --- |
|  | • | What percent of the application costs is attributed to the underlying infrastructure costs? |

**Parent topic:** [Costing Standard](../home.html)
