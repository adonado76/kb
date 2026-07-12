---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Application Portfolio"
breadcrumb:
  - "Costing Standard"
  - "Report Walkthrough"
  - "Applications Collection"
source_path: "cost-transparency/reports/application-portfolio.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Application Portfolio

This report expands the information in the Application Review report to the entire
application portfolio. This report allows you to see who's responsible for the overall suite of
applications in your IT organization, the spend per business unit, cost drivers broken out by IT
tower and vendor, and the impact of projects related to the applications.

The portfolio view looks across your entire application suite and helps you gain insights related
to who's consuming application spend, the cost drivers, the cost composition of vendors, and
projects related to your applications.

This report is designed for:

- Office of the CIO or IT leadership
- Enterprise architects
- Business analysts

This report allows you to quickly review the entire application portfolio across the
organization. Slicers let you to filter the data that is displayed. For example, you might want to
set the Application Type slicer to filter on COTS (customer-off-the-shelf) and SaaS applications if
you're considering a move from customer applications to SaaS applications in an effort to reduce
overall IT costs. For more information on slicers, see element 2, below.

Some executive teams might use this report to look into efficiencies and how to reduce IT
spending. In this case, you would expect to see more spent on application run (app run) than on
application development (app dev). Other executives might focus on innovation and the digital
transformation of their business. In this case, expect to see spending shift from application run to
application development. For more examples, see the explanations for elements 2, 3, and 4,
below.

The Application Portfolio report contains the following elements:

![](../../resources/images/ct_images/ct%20report%20collections/application%20portfolio.jpg)

| Key element | Description |
| --- | --- |
| (1) Report collection | This report collection provides the details you need to review your application spend, trends, and usage:  - [Application Review report](application%20review.htm "(Opens in a new tab or window)")   (open by default) - Application Portfolio (described in this page) - [Application List   report](application%20list.htm "(Opens in a new tab or window)") - [Infrastructure   Analysis by Application report](infrastructure%20analysis%20by.htm "(Opens in a new tab or window)") - [New & Retired Apps   report](new%20retired%20apps.htm "(Opens in a new tab or window)")   Apptio might truncate the report collection list, depending on the size of your screen. If you cannot see the entire collection listed, you can find the missing reports by selecting the More arrow. |
| (2) Slicers | The global slicers in the Applications report collection persist from report to report, so the filters you set in this report could affect what you see in other Applications reports. For more information, see the "Slicers" section in the Application Review report. |
| (3) KPIs | KPIs provide a high-level view of your application spend compared to budget:   - App Run YTD: Application run (app run) is the OpEx, day-to-day activity cost that is included in   the amortization of application-related projects. - App Dev YTD: Application development (app dev) is project investment---what is being done to   change the portfolio and develop the business. - # Retired Apps over 12 months: This KPI shows the number of applications retired and acquired in   the last 12 months. - Application Count: This KPI shows the current number of applications used in the organization,   with the percentage of change in applications YTD. |
| (4) Application Spend by Category | Use the Application Spend by Category panel to compare your running investments (App Run, on the left) to your development investments (App Dev, on the right). Being able to see side-by-side comparisons of the spending in certain categories can be dynamic and useful.    App Run Spend and App Dev Spend: Use this tab to compare bar charts side by side. From the Select Category field, select a category to compare the app run and app dev for that category:   - Application Type: Select this option to compare spending by type of application. For example,   compare the app run and app dev for Saas applications. - Application Family: If you have mapped applications into groups, select this option to compare   app run and app dev for a specific application family. - Application Function: This selection can be configured for a core service or function that is   important to your organization. - Application IT Owner: This selection lets you see which application owner is managing the   largest cost from a portfolio perspective. - Application User Category: This selection lets you see what type of user category (business   apps, customer apps, IT apps, etc.) has the largest cost from a portfolio perspective.   As industry moves toward digitalization, businesses are building more technology that directly supports end users, which drives value to the business. Often, the goal is to spend more on customer-facing applications than on internal IT applications, or even on internal business applications. Therefore, it's critical to know where that spending is occurring.  Details (for both sides): Select this tab to display see the underlying details used for the bar charts.    In either of the Details, click in the chart or table to open the [Application Detail dialog (application family-level)](../reports-v104/applicationdetaildialogappfamily.html "(Opens in a new tab or window)"). The dialog shows the list of applications in the application family, associated projects, and the spend over time.  Trend (for both sides). Select this tab to compare the category spend over time. |
| (5) Application Consumption by Business Unit | Use the Application Consumption by Business Unit panel to see who is using applications by business unit (BU). You can use this panel to rationalize specific applications and determine whether the portfolio can be simplified.    This panel contains a lot of data, so it might be helpful to focus on a specific application family by setting a filter. For example, you might want to filter by a specific application family to see how many applications are off-the-shelf or custom within a BU. This report can also help you see who's consuming those applications. The bar chart shows the BUs with the highest consumption YTD. Select OpEx and CapEx to toggle the bar charts with that data. |
| (6) Application Composition | Use this set of charts and tables to view your application spend YTD per IT tower and vendor to understand the costs related to each application. You can use them to see OpEx from a tower perspective and evaluate the composition of those costs. For example, if spending is particularly high in the Compute, Storage, and Data Center towers, you might consider moving to Saas applications to reduce those costs.    You can also use this data from a vendor perspective to see what is driving both the direct and indirect costs that are flowing into your application portfolio. For example, the costs shown in the Hardware tower for a specific vendor might be very high, but that might happen because that storage is being used by many applications, so you have to consider more of a holistic view of the vendor costs.  Application Composition by IT Tower: The chart shows the IT towers with the highest spend YTD. Click a bar in the chart to view details about the application spend per IT sub-tower.  Application YTD OpEx by Family and IT Tower: The table lists all applications by family, breaking out the spend YTD for each IT tower.  Select any item in the Application Name column to open the [Application Name detail report](../reports-v104/applicationnamedetail.html "(Opens in a new tab or window)"), filtered to show the full spend, trend, and details for the application you selected from the main report. |
| (7) Applications Impacted by Projects | Use the Applications Impacted by Projects chart and the Project Spend by Application Family table to see the applications impacted by various projects across the organization, organized by application family. Use this data to see the impact of projects by application family.  Select a bar in the chart or any item in the Project Name column of the table to open the [Project Financial Details dialog](../reports-v104/projectfinancialdetails.html "(Opens in a new tab or window)"). |
|  |  |
