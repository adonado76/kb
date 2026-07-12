---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Application list"
breadcrumb: []
source_path: "reports/application-list.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Application list

This report is designed for application owners. It is an analytical report that provides
quick access to the complete details about any of the applications in the organization.

This report is designed for:

- IT leadership
- Application owners
- Business analysts
- Enterprise architects
- Portfolio managers

This report allows application owners to dive into the details of the applications they are
responsible for. You can set a global slicer for a specific application owner or application family.
For example, you might want to set the Application Owner global slicer to filter your own name so
you can see your applications every time you log on.

You can dynamically add and remove columns using the Select Additional Columns panel to get a
better view of the details of the applications you're responsible for. For example, after setting
the Application Owner filter to your own name, you might choose to remove the Application Business
Owner column from the table since you don't need to see your name listed as the owner in every
row.

Another use case is to quickly analyze the data about the applications that are being eliminated.
For example, you can set the Slice by Objective to Eliminate, then look for high App Dev figures.
This might lead you to question why development is continuing for an application that is being
deprecated. In addition, you'd expect to see zero costs associated with the applications that are
being eliminated. You can use this data to confirm and clean up your application usage.

Another use case might be to filter for historical data in an effort to find new ways of storing
unused applications offline without consuming infrastructure. For more information on slicers, see
the explanation of element 2, below.

The Application List report contains the following elements:

![](../../resources/images/ct_images/ct%20report%20collections/application%20list.jpg)

| Key element | Description |
| --- | --- |
| (1) Report Collection | This report collection provides the details you need to review your application spend, trends, and usage:  - [Application Review report](application%20review.htm "(Opens in a new tab or window)")   (open by default) - [Application Portfolio   report](application%20portfolio.htm "(Opens in a new tab or window)") - Application List (described in this page - [Infrastructure   Analysis by Application report](infrastructure%20analysis%20by.htm "(Opens in a new tab or window)") - [New & Retired Apps   report](new%20retired%20apps.htm "(Opens in a new tab or window)") |
| (2) Slicers | The following global filters are available in this report:   - Application Type: - COTS: Consumer off the shelf, packaged applications - Custom: Home-grown applications, created in-house - SaaS: On-demand, web-based applications - Application IT Owner: Similar to a cost pool owner, an application owner is the point-person   responsible for understanding and delivering an application. - Application Family: Families are groups of related applications, as defined by your   organization.  The following roles might use the slicers in this report for a more personalized view:  - Application Portfolio Manager or CIO: Without setting any slicers, you can see an overview of   the application spend across the organization. Use the slicers to narrow what you see across all   Applications reports. You might select a name from the Application IT Owner slicer to understand   that person's responsibilities related to applications. You might select a group of applications   from the Application Family to understand that group's overall performance. - Application Owner: Select your name to narrow the applications to the ones that you're   responsible for, and to see the performance of those applications at a high level. - Financial Analyst: Set the slicers for the areas you support to enable a detailed,   cross-organizational spend analysis.   Note: Remember that the filters you set in other Application reports can affect what you see in the Application Review report. For example, it's possible to set a filter in the Application List report that accidentally prevents or limits the applications you can see in the Application Review report. |
| (3) Application Details | Use this table to see specific details about all of your applications. The table lists the business and IT owners of each application, the app run and dev spend, server count, storage space, spend per user, and much more. Select any item in the Application Name column to open the full-page [Applications detail report](https://tbmcouncil.jiveon.com/docs/DOC-9217 "(Opens in a new tab or window)"), which provides all of the standard data in the system for the specific application you clicked.  The Application Details table includes the following additional slicers, which are specific to this report. These slicers do not persist to other reports in the Application report collection:   - Slice by Objective: This slicer allows you to filter according to the investment objectives that   you can assign to individual applications. You can also see these objectives for the applications   with the highest spend in the Application Spend tab in the Application Review report. - Tolerate: These are applications that you want to keep in the portfolio for a long time. You   need them, but you don't necessarily want to invest in them. Ideally, these applications won't have   much continuing development, as evidenced by low figures in the App Dev column. - Invest: These are applications that the business wants to improve or change. As a result, expect   to see higher figures in the App Dev column for these applications.   If you see low figures for applications marked as Invest, you want to question whether development has started.   - Migrate: These are applications that are being migrated. Expect to see little or no continuing   development (evidenced in the App Dev column) for these applications. - Eliminate: These are applications need to be eliminated. Expect to see low figures in the App   Dev column for these applications. If you see high figures in the App Dev column for applications   that are being migrated or eliminated, you want to question that, because the continued development   of those applications would work against your goal for your application portfolio. - Slice by Criticality: This slicer allows you to filter according to the level of business   need. - Business Essential: Without these applications, the company would suffer loss or penalties   either financially, legally, or some other way. Loss of these applications would have a serious   impact on the business. - Historical: These applications are no longer used. - Mission Critical: Without these applications, the company would suffer grave loss or penalties   either financially, legally, or some other way. Loss of these applications would completely disrupt   the business. - User Productivity: These applications help the organization achieve its desired end results,   reduce failures, enhance job performance, and simplify data management. Loss of these applications   would have a low to moderate effect on the business. - Slice by Category: This slicer allows you to filter according to type of application. |
| (4) Select Additional Columns | Control the visibility of the columns in the Applications Details table by selecting and deselecting the column names listed in the Select Additional Columns panel. |

Questions answered

- You can use this report to answer the following questions:
- Who are our SaaS providers and how much do we spend with each?
- What is our total spend per user per application?
- What is our total app run and app dev per application?

**Parent topic:** [Costing Standard](../home.html)
