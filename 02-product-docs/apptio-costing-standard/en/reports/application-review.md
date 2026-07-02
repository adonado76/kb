---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Application Portfolio"
breadcrumb: []
source_path: "reports/application-review.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Application Portfolio

This report provides an executive overview of the application spend, broken out by app
run (operating costs) and app dev (investments) for your top applications, application families, and
the underlying infrastructure costs based on the ATUM IT towers (Data Center, Compute, Storage, and
Network). A simplified snapshot of any application is available with a quick click in any bar
chart.

This report is designed for:

- Application portfolio owners
- Application owners
- CIO and IT leadership

This report allows quick, high-level, periodic (for example, monthly) reviews of the applications
used across your organization. Slicers in this report allow you to filter for a specific type of
application, application owner, or application family. For example, you might want to set the
Application Type slicer to filter only COTS (customer-off-the-shelf) and SaaS applications if you're
considering a move to SaaS applications in an effort to reduce overall IT costs. For more
information on slicers, see the explanation of element 2, below.

Some executive teams might use this report to look into efficiencies and how to reduce IT
spending. In this case, you might focus on your most expensive applications or look for comparable
applications that are redundant. Other executives might focus on innovation and the digital
transformation of their business. In this case, you might want to identify how to shift spend from
app run to app dev. For more examples, see the explanations for elements 2, 3, and 4, below.

The Application Review report contains the following elements:

![](../../resources/images/ct_images/ct%20report%20collections/application%20review.jpg)

| Key element | Description |
| --- | --- |
| (1) Report collection | Each of the reports in this collection provide the financial and operational details you need to review your application spend, business drivers, application consumption, and application cost composition:   - Application Review (described in this page) - [Application Portfolio   report](application%20portfolio.htm "(Opens in a new tab or window)") - [Application List   report](application520list.htm "(Opens in a new tab or window)") - [Infrastructure   Analysis by Application report](infrastructure%20analysis%20by.htm "(Opens in a new tab or window)") - [New & Retired Apps   report](new%20retired%20apps.htm "(Opens in a new tab or window)") |
| (2) Slicers | The following global filters are available in this report:  Application Type:   - COTS: Common off the shelf, packaged applications - Custom: Home-grown applications, created in-house - SaaS: On-demand, web-based applications - Application IT Owner: An application owner is the point-person responsible for understanding and   delivering an application. - Application Family: Families are groups of related applications, as defined by your   organization.   The following roles might use the slicers in this report for a more personalized view:   - Application Portfolio Manager or CIO: Without setting any slicers, you can see an overview of   application spend across the organization. Use the slicers to narrow what you see across all   Applications reports. You might select a name from the Application IT Owner slicer to see all of the   applications that person is responsible for. You might select a specific Application Family to the   related applications in that group. - Application Owner: Select your name to narrow the applications displayed to the ones you're   responsible for. |
| (3) KPIs | KPIs provide a high-level view of your application spend and other metrics.  Use the year-to-date and trending data to compare the previous year to the current year for a more aggregated understanding, rather than just a monthly view:   - YTD App Spend as a % of IT Spend: This KPI shows the percentage of your application spend that   is associated with applications versus your overall IT spending YTD. These figures can be useful for   viewing change over time or looking into specific areas. For example, you could focus on the years   with the biggest spend if you want to optimize the spend. Or, if you have a large application   portfolio with lots of applications and redundancies, your figures might be very high, giving you an   opportunity for improvement. - App Run YTD: Application run (App Run) includes the OpEx daily activity and the amortization of   software and application-related projects. - App Dev YTD: Application development (App Dev) is project investment---what is being done to   enhance your applications and enable business capabilities. - Application Count: This KPI shows the number of in-service applications in your application   portfolio and the number for the previous period. These figures give an overview of the size of your   application portfolio. |
| (4) Application Spend by Category | Use the tabs in the Top Applications section to quickly view the top applications with the highest spend YTD. You can configure the number of applications to be displayed in this report. Viewing 10-20 applications is suggested.  In any of the tabs in the Top Applications panel (listed below), you can click on any chart or the first column of any table to open an [Application Detail dialog (application-level)](application%20review.htm#Applicat) that contains information specific to the application you select.  Note: The Application Detail dialog contains information that is different from the Applications Detail tab, which is discussed below.  Top Applications: Use this tab to see the overall cost for the top applications in your portfolio and how they trend over time. For example, the following image shows that Oracle CRM is clearly the most expensive application.    The Trend chart shows spending over the past 13 periods. In our example, the Trend chart shows that the CRM Oracle costs are coming down, supporting the fact that the application is being retired. When used together, the charts can provide a more accurate view of your application consumption.  Questions answered:   - What are the most expensive applications to run? - How much are we investing to change or enhance our applications?   Details: Select this tab to see the supporting details for the applications displayed in the Top Applications tab. These details will help you evaluate the costs and investments in your top applications.     - Application Name: Select this column to see the supporting details as those listed above for Top   Applications. - Application Business Owner: Use this column to easily see the primary owner from a business   consumption perspective. It's possible to have multiple business owners, but this column lists only   the primary owner. - Application Investment Objective and App Run/App Dev: The Application Investment Objective   column uses the TIME acronym. - Tolerate: These are applications that you want to keep in the portfolio, but you don't   necessarily want to invest in them. Ideally, these applications won't have much continuing   development, as evidenced by low figures in the App Dev column. - Invest: These are applications that the business wants to improve or innovate. As a result,   expect to see higher figures in the App Dev column for these applications. If you see low figures   for applications marked as Invest, you want to validate whether your investments are aligned with   your business expectations. - Migrate: These are applications that are being migrated or modernized. Expect to see any   investments in the App Dev column to be related to tech debt and not new functionality for these   applications. - Eliminate: These are applications to be removed from the application portfolio. Ideally, you   wouldn't expect to see any App Run or App Dev costs for these applications. If you see high   figures in the App Dev column for applications that are being migrated or eliminated, you want to   question that, because the continued development of those applications would work against your goal   for your application portfolio. - Server Count and Storage Total Space: The server count and the amount of storage provides   quantitative information about the infrastructure that supports the applications.   Questions answered:   - What is driving the cost of each application? - How much are we investing to change and enhance our applications?   Business Driver: Select this tab to see the units of output delivered for this application. The metrics include the specific unit of measure for the application, the quantity trend, and the average annual unit cost.    Look at the run costs and number of units to help you understand your applications in terms of cost per transaction, which allows you to see efficiencies over time and to compare similar applications in your portfolio.  If you set a target unit cost, you can track how the Average Monthly Unit Cost compares to the target over time. For example, if the cost per order for an order management system continues to trend down over time and hits your target unit cost you can use that data to demonstrate the efficient delivery of the application.  Questions answered:   - How does output vary over time? - What is the average unit cost for the unit of output? - How does the average unit cost vary over time?   Users: Select to see user-level metrics for the top applications. You can see the number of users, the average spend per user, and the average monthly spend, and how they trend over time.    To view data about all of your applications, see the Application Portfolio report.  Questions answered:   - How many users are using the application? - What is the average cost per user per period? - Who is using the application? (filter by business unit) |
| (5) Application Consumption by Business Unit | Use the Application Spend by App Family tab to see an aggregated view of your application spend by application family.    The Application Detail tab shows the underlying detail and related information about the application family.    In either tab, click in the chart or table to open the Application Detail dialog (application family-level). The dialog shows the list of applications in the application family, associated projects, and the spend over time.  Questions answered:   - Which application families have the greatest number of applications? |
| (6) Application Composition | Use the Infrastructure Costs tab to see the overall Data Center, Compute, Storage, and Network costs associated with your applications and the spend over time.    The Infrastructure Detail tab provides the underlying details about the infrastructure cost broken out by cost pool. You can filter the report by application family to see the infrastructure profile, which may be different across application families.    Select any row in the IT Resources Tower Name column or in the bar chart to see the quantity and unit cost over time in the Tower Detail dialog.    Questions answered:   - How much am I spending on infrastructure to support my applications? |

**Application Detail dialog (application-level)**

The Application Review report allows you to click in charts and tables to open dialogs with
information about specific applications. This section describes the Application Detail
(application-level) dialog that is available from any of the tabs in the Top Applications panel of
the Application Review report.

A similar detail dialog is available from the Application Spend by App Family panel of the
Application Review report. For that dialog, see the [Application
Detail dialog (application family-level)](../reports-v104/applicationdetaildialogapp.html "(Opens in a new tab or window)").

Note: This dialog is a simplified version of the full-page Applications detail
report.

The Application Detail (application-level) dialog contains the following elements:

![](../../resources/images/ct_images/ct%20report%20collections/application%20review_4.jpg)

| Key element | Description |
| --- | --- |
| (1) KPIs | The Application Detail dialog shows KPIs that are specific to the application you clicked from the main page. Use the year-to-date and trending data to compare the previous year to the current year for a more aggregated understanding, rather than just a monthly view:   - App Run YTD: Same as for the Application Review report, but filtered for the specific   application. - App Dev YTD: Same as for the Application Review report, but filtered for the specific   application. - % of Infra App Run YTD : Same as for the Application Review report, but filtered for the   specific application. |
| (2) Summary | View the spending trend for application development and run (left chart) for the application, its related infrastructure, and the application itself (right chart). |
| (3) Business Driver | Select this tab to view the actual number of units, along with average annual unit cost and target annual cost. |
| (4) Users | Select this tab to view the trending number of users and the average monthly cost per user. In this example, you can see a dramatic drop in user count, which you'd expect for an application being migrated or deprecated. As expected, the average unit cost is burdened much higher due to the drop in users. |
| (5) Related Projects | Select this tab to view the projects associated with the application you selected. |
| (6) Business Unit Consumption | Select this tab to view which business units are consuming the application. |

**Application Detail dialog (application family-level)**

The main Application Review report allows you to click in charts and tables to open dialogs with
information about specific applications. This article describes the Application Detail dialog for an
application family, which is available from any of the tabs in the Application Spend by App Family
panel of the Application Review report. The dialog shows the list of applications in the application
family, associated projects, and the spend over time.

A similar detail dialog is available from the Top Applications panel of the Application Review
report. For that dialog, see the [Application Detail dialog (application-level)](application%20review.htm#Applicat).

Note: This dialog is a simplified version of the full-page Applications detail
report.

The Application Detail dialog for application family contains the following elements:

![](../../resources/images/ct_images/ct%20report%20collections/application%20review_5.jpg)

| Key element | Description |
| --- | --- |
| (1) KPIs | The Application Detail dialog for application family shows KPIs that are specific to the application you selected from the main page. Use the year-to-date and trending data to compare the previous year to the current year for a more aggregated understanding, rather than just a monthly view:   - App Run YTD: Same as for the Application Review report, but filtered for the specific   application. - App Dev YTD: Same as for the Application Review report, but filtered for the specific   application. - % of Infra App Run YTD: Same as for the Application Review report, but filtered for the specific   application. |
| (2) Summary | View the spending trend for application development and run (left chart) for the application, its related infrastructure, and the application itself (right chart). |
| (3) Application List | Select this tab to see a list of the applications related to the application family you selected. |
| (4) Related Projects | Select this tab to view the projects related to the application family you selected. |

**Parent topic:** [Costing Standard](../home.html)
