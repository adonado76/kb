---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "whats-new.html"
title: "Recent releases"
breadcrumb: []
source_path: "whats-new.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Recent releases

## Server 12.11.12 - February 28, 2025

Application template: 8191

New Application Features

Hybrid IT TCO Impact for IBM Apptio Costing Standard (v120)

The Hybrid IT TCO Impact solution is designed to help organizations measure and understand the
financial impact of their evolving hybrid IT environments. It empowers end users such as C-Suite
executives and Application Owners to make informed decisions and ensure migrations deliver the
intended financial value.

This solution provides several key benefits (as demonstrated by the
below reports), including the ability to compare current vs. target hybrid IT footprint, evaluate
migration financial benefit, and perform detailed pre-/post-migration analysis. These features
enable users to make informed decisions about application migration and optimize their hybrid IT
environments.

Level 100 Report: Hybrid IT TCO Impact Summary

![](../resources/images/ct_images/cg-sum.jpg)

Level 200 Report: Hybrid IT
TCO Impact Insights

![](../resources/images/ct_images/cg-200.jpg)

Level 300 Report: Hybrid IT TCO Impact Analysis

![](../resources/images/ct_images/cg-300.jpg)

To enable this new
solution, get started as follows:

For further configuration details, go [here](https://help.apptio.com/en-us/cost-transparency/configuration/hybrid-it-tco.htm "(Opens in a new tab or window)").

![](../resources/images/ct_images/3-steps.jpg)

Public Cloud TCO for Costing Standard (v120) and Costing Essentials (v200)

The Public Cloud TCO release for Costing Standard (v120) and Costing Essentials (v200) offers
multiple benefits for primary users, mainly IT finance teams. This version provides a simple and
transparent financial lens across monthly public cloud costs, helping to avoid unexpected bill
shock. It also enables teams to drive accountability and ensure optimal efficiency of public cloud
services, minimizing waste.

The new release includes the installation of new components, such
as Public Cloud TCO in v120 and Public Cloud TCO and Public Cloud TCO Reporting in v200. Users can
connect to cloud data and utilize features like Account Name, Business Unit, and Cloud Tower Mapping
Table to tailor reports and gain insights into their organization's cloud practices. With this
release, users can assess if their organization is applying "Best in Class" cloud practices,
including RI Coverage and Utilization Rates, to optimize their cloud services.

![](../resources/images/ct_images/release_notes/pct-1.jpg)

![](../resources/images/ct_images/release_notes/pct-2.jpg)

![](../resources/images/ct_images/release_notes/pct-3.jpg)

For more
information on configuration, see [here](https://help.apptio.com/en-us/cost-transparency/reports/public-cloud-config.htm "(Opens in a new tab or window)").

Costing Essentials (v200)

The Model Overview Reports are a new feature designed to provide users with a comprehensive view
of cost flows within the model. This release includes reports
for Labor, Vendor, Solutions, Consumers, and Cost Model, and is available to all users with report
access. The reports are designed to enhance transparency and clarity for users, providing a clear
and detailed view of cost flows within the model. The Labor Model View is included in the Cost-Labor
Reporting component, while the Cost Model View is found in the Model View collection.
The Vendor, Solutions, and Consumers Reports are located in their respective
collections.

Users can click on fields to select and see how cost is flowing between different
objects, providing a clear and intuitive way to navigate the reports. The reports are accessible to
anyone with report access, without requiring TBM Studio access. The primary users of the Model
Overview Reports are Admin and Power User, to refine cost allocations, make informed decisions, and
optimize their cost management processes.

![](../resources/images/acm_images/ce-model-view.jpg)

![](../resources/images/acm_images/ce-lcm.jpg)

![](../resources/images/acm_images/ce-vcm.jpg)

To view all
report cost models, see [here](https://help.apptio.com/en-us/apptio-cost-management/out_of_the_box_reports/model-views-ce.htm "(Opens in a new tab or window)").

Billing Essentials (v200)

The following enhancements have been made to Billing Essentials V200.

- Japanese language support has been added to improve accessibility for users.
- The Rate Management report now includes a new Rate Adjustment Impact metric, providing
  additional insights into rate changes.

  ![](../resources/images/be/rm-1.jpg)

  ![](../resources/images/be/sm-2.jpg)

  To
  know more, see the configuration [here](https://help.apptio.com/en-us/billing-essentials/configure-billing-essentials/configuration.htm "(Opens in a new tab or window)").
- A new Model Overview Report has been added to provide a summary of key billing
  information.

  ![](../resources/images/be/bcm.jpg)

  To know more,
  see [here](https://help.apptio.com/en-us/billing-essentials/reports/model-views-be.htm "(Opens in a new tab or window)").

Fixed in this release

- Resolved the issue of number parsing of strings containing ’e’.
- Unused Allocations is now GA.
- Fixed vulnerability issues.

## Client 2.12 - February 28, 2025

Dependency

\*Client v2.12 is compatible with Server 12.11.12 and 12.11.11.x

New Client Features

Email Subscription enhancements

The email subscription functionality
has been enhanced to improve usability, customization, and the overall user experience. The
administrators can now configure and customize email settings, while the end users will get clear
interactive emailed reports. and clarity in managing and receiving emailed
reports.

Dynamic PDF File Naming: The PDF file attached to email
subscriptions now includes the report name and reporting period in its file name. This change
ensures easier identification and organization of reports for recipients.

![](../resources/images/studio_images/r-notes/ess-1.jpg)

Customizable Email Subject and Email Body: Administrators can now
customize the email subject line using dynamic fields, like Report name, Reporting period, and
Report filters for more context-specific and relevant email subjects. The email body can also be
customized with dynamic fields, like Report name, Reporting period, and Report filters to provide
additional context or instructions directly in the email.

![](../resources/images/studio_images/r-notes/ess-2.jpg)

Updated Call-to-Action Button: The "View Report" button in the email
has been updated to "View Full Report in Apptio" so that recipients understand where the link will
take them.

![](../resources/images/studio_images/r-notes/ess-3.jpg)

Send Now: This feature provides the administrators a convenient way
to verify that the email subscription is working as intended, ensuring that subscribers receive the
expected content. By using Send Now, users can confidently test their email subscriptions, making it
easier to manage and maintain their subscriptions.

The Send Now feature is accessible from two
locations: under Manage Subscriptions for every email subscription, and on the edit screen of an
individual email subscription. To use Send Now on the edit screen, users must first save any changes
made to the subscription details. If changes are made but not saved, the Send Now feature will be
disabled until the changes are saved. Once saved, users can click Send Now to send a test email to
the subscribers, providing a quick and easy way to test and verify their email subscriptions..

![](../resources/images/studio_images/r-notes/send-nw.jpg)

![](../resources/images/studio_images/r-notes/send-nw1.jpg)

To
know more, see [Email Subscriptions](https://help.apptio.com/en-us/studio/reports/email-subscription.htm "(Opens in a new tab or window)").

Editable Tables

editCell function now works on a specific column only: In this release,
the cellEdit function has been updated to allow more precise email notifications. Administrators can
now configure the SendMail() function to trigger exclusively when the "Submission Status" column is
changed from “In Progress” to “Submitted,” ensuring Approvers are notified only when the status is
updated. Previously, edits to other columns would also trigger emails if the status remained
“Submitted.” This update introduces the cellEdit(“column\_name”) syntax, which ensures actions are
triggered only when the specified column is modified.

![](../resources/images/studio_images/r-notes/et-edit.jpg)

Show Changes enhancements: The Show Changes feature has been updated
with the following enhancements:

The primary key (PK) is now displayed in the Show
Changes view, allowing for easier identification of modified records.

![](../resources/images/studio_images/r-notes/sc-pk.jpg)

For enriched
editable tables, the Show Changes view only displays changes made to the underlying source table.
This is indicated by the presence of a value for modified fields and the absence of a value for
unmodified fields.

![](../resources/images/studio_images/r-notes/sc-pk1.jpg)

Fixed in this release

- 'Show Changes' views now align with Data Pipeline > Editable Table step.
- Fixed security vulnerabilities.

## Server 12.11.11.2 - February 27, 2025

- Fixed security vulnerabilities.

## Server 12.11.11.1 - February 5, 2025

- Quarterly Java update.
- Fixed the environment 'not found' issue in Apptio BI.

## Server 12.11.11 - January 17, 2025

Application template: v120-8191

New Application Features

Billing Essentials GA
(v200)

This release provides the following enhancements to improve the overall
user experience and provide more efficient management of billing and data upload processes.

- Enhanced Reporting: The Billing Process Admin Report has been integrated
  into the Billing collection, with role-based access control (RBAC) permissions configured to
  restrict access to authorized Billing Process Owner(s).
- Journal Entry Export and Archiving: The Billing Journal Archive tab now
  enables users to export journal entries to an Excel file (.xlsx) and create a flattened table for
  audit reporting purposes, utilizing a CopyTable script to ensure data integrity.
- Invoice Archiving: The Bill Invoice Archive tab features a Copy Invoice
  Details button script, which facilitates the archiving of bill invoices by creating a duplicate copy
  of the original invoice, ensuring a permanent record for auditing and compliance purposes.

  ![](../resources/images/be/be-rn-1.jpg)

  ![](../resources/images/be/be-rn-2.jpg)

Fixed in this release

- Deleted data permanently for a table in data pipeline.
- Fixed vulnerability issues.
- Precision calc optimizations

## Client 2.11 - January 17, 2025

Dependency

\*Client v2.11 is compatible with Server 12.11.11 and 12.11.10.x

\*Some Client
v2.11 features are dependent on new Server 12.11.11 features.

New Client Features

Table Upload feature is now
GA

The Table Upload Component was released two years ago and the visibility in the
Studio Ribbon was controlled via the Enable Features feature. With it moving to GA, no impact will
happen to any existing project.

Email Distribution Enhancements

- Filtered views subscriptions: This feature enables users to share
  filtered reports with specific recipients through a subscription system. The recipients will receive
  a hyperlink to access the report with pre-applied slicer selections, thereby allowing them to view
  the report with the desired filter settings. Additionally, recipients have the option to receive an
  attached PDF document, which can be configured to include or exclude the linked Simple View while
  maintaining the selected filter settings. This feature provides a flexible and secure way to share
  reports with others, ensuring that recipients receive the information they need in a format that is
  easy to consume.

  ![](../resources/images/studio_images/r-notes/fv.jpg)

  To know more, see [Email Subscriptions with Filtered View](https://help.apptio.com/en-us/studio/reports/email-subscription.htm#Email "(Opens in a new tab or window)").
- Duplicate Subscription: This feature enables users to create a copy of an
  existing email subscription and simplifies the subscription management process. To implement this
  feature, a new "Duplicate Subscription" icon has been added to the Manage Subscription dialog, which
  allows users to create a copy of an existing subscription. The duplicated subscription is
  automatically named with the prefix "Copy of" followed by the original subscription name, and users
  can edit the details of the duplicated subscription, including the name, frequency, and attached
  email template.

  ![](../resources/images/studio_images/r-notes/dupsub.jpg)

  To know more, see [Duplicate Email Subscriptions](https://help.apptio.com/en-us/studio/reports/email-subscription.htm#Duplicat "(Opens in a new tab or window)").

Horizontal scroll bar for open Studio document tabs​

To improve the
management of multiple bottom tabs opened in the studio, a horizontal scroll bar has been
introduced. It allows users to easily navigate through multiple open tabs. Additionally, the latest
tab opened will be highlighted, providing a clear visual indicator of the current tab in
focus.

![](../resources/images/studio_images/r-notes/scroll.jpg)

Previously the tabs would disappear if there was no space, and hence it was tedious to open
them again.

Editable Tables

- Create branch has option to auto-check out all editable tables: A new
  feature has been introduced to improve the management of editable tables in branches. This
  enhancement provides a more streamlined and efficient workflow for managing schema and data changes
  in branches and helps to prevent unintended changes to the trunk.

  When creating a branch, user can
  now select the option to automatically check out all editable tables, which will update them in the
  development workspace. The need for manual checkout of individual tables is not required, thereby
  reducing the risk of data inconsistencies and errors. The checkout process is now automated,
  ensuring that all editable tables are properly updated in the branch.

  Previously, when data
  was updated in a branch, it was automatically updated to the trunk. There was no control to validate
  or confirm the changes in a branch. To know more, see [Create Branch with Auto-Checkout Option](https://help.apptio.com/en-us/studio/admin/bp-branching-projects.htm#Create "(Opens in a new tab or window)").
- Expose Username and Edit Date from change history: The editable table
  solution configuration process is enhanced by exposing two new reporting columns -
  .Username and .Edit Date system columns. Administrators can now easily access these columns in
  Project Explorer when an Editable Table is opened and drag them into the ad hoc configuration panel
  for an editable table report component. Additionally, these columns are now visible in the report
  view mode, allowing users to order and resize them as needed. This update eliminates the need to
  create separate columns and use ApptioScript to populate the information, streamlining the
  configuration process and improving the overall user experience.

  ![](../resources/images/studio_images/r-notes/sh-1.jpg)

  ![](../resources/images/studio_images/r-notes/sh-2.jpg)

  ![](../resources/images/studio_images/r-notes/sh-3.jpg)

  Previously, both
  these columns were available only in Show Changes. To avoid confusion, the column names in Show
  Changes table have been renamed to Username and EditDate.

  To know more, see [Show/hide .Username and .EditDate](https://help.apptio.com/en-us/studio/reports/tables/component-config-panel.htm#Show/hid "(Opens in a new tab or window)").
- Save/Bulk Update Performance Improvement: A significant performance
  improvement has been made to the save and bulk upload functionality, resulting in faster and more
  efficient processing of large datasets.

  | Number of rows updated | Number of columns updated | Old time (in seconds) | New time (in seconds) |
  | --- | --- | --- | --- |
  | 10,000 | 3 | 179 | 2 |
  | 20,000 | 3 | 578 | 4 |
  | 30,000 | 3 | 1189 | 7 |
  | 1 lakh | 1 | timeout | 47 |
  | 2 lakhs | 5 | timeout | 110 |

Fixed in this release

- Fixed the issue of dropdown menus not respecting the Row Level Security for standard table.
- Fixed the issue of Table Auto Sizing not working properly with Tree option.
- Fixed the issue of Pseudo Translations of Missing Strings.
