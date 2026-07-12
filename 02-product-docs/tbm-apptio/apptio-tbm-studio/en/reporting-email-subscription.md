---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Email Subscription"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "Create Reports"
  - "Advanced Reporting"
  - "Email Subscription"
source_path: "SSWRJM/studio/reports/email-subscription.html"
images:
  - "03-media/apptio-tbm-studio/es-1.jpg"
  - "03-media/apptio-tbm-studio/em-sub-1.jpg"
  - "03-media/apptio-tbm-studio/ms-1.jpg"
  - "03-media/apptio-tbm-studio/ms-2.jpg"
  - "03-media/apptio-tbm-studio/ms-3.jpg"
  - "03-media/apptio-tbm-studio/endisES.png"
  - "03-media/apptio-tbm-studio/send-now.jpg"
  - "03-media/apptio-tbm-studio/send-now-1.jpg"
  - "03-media/apptio-tbm-studio/email-full.jpg"
  - "03-media/apptio-tbm-studio/pdf-name.jpg"
  - "03-media/apptio-tbm-studio/pdf-11.jpg"
  - "03-media/apptio-tbm-studio/pdf-10.jpg"
  - "03-media/apptio-tbm-studio/pdf-9.jpg"
  - "03-media/apptio-tbm-studio/pdf-8.jpg"
  - "03-media/apptio-tbm-studio/pf-7.jpg"
  - "03-media/apptio-tbm-studio/pdf-6.jpg"
  - "03-media/apptio-tbm-studio/pdf-5.jpg"
  - "03-media/apptio-tbm-studio/pdf-4.jpg"
  - "03-media/apptio-tbm-studio/pdf-3.jpg"
  - "03-media/apptio-tbm-studio/pdf-2.jpg"
  - "03-media/apptio-tbm-studio/pdf1.jpg"
  - "03-media/apptio-tbm-studio/filter-view.jpg"
  - "03-media/apptio-tbm-studio/ds2.jpg"
  - "03-media/apptio-tbm-studio/ds3.jpg"
  - "03-media/apptio-tbm-studio/ESsearch.png"
  - "03-media/apptio-tbm-studio/ds4.jpg"
  - "03-media/apptio-tbm-studio/ds-5.jpg"
  - "03-media/apptio-tbm-studio/ds5.jpg"
  - "03-media/apptio-tbm-studio/ds6.jpg"
  - "03-media/apptio-tbm-studio/ds7.jpg"
  - "03-media/apptio-tbm-studio/ds8.jpg"
  - "03-media/apptio-tbm-studio/ds-1.jpg"
  - "03-media/apptio-tbm-studio/ds-2.jpg"
  - "03-media/apptio-tbm-studio/dup-sub1.jpg"
  - "03-media/apptio-tbm-studio/ds-3.jpg"
  - "03-media/apptio-tbm-studio/bu_toggle.png"
  - "03-media/apptio-tbm-studio/bu-2.png"
  - "03-media/apptio-tbm-studio/bu-1.png"
  - "03-media/apptio-tbm-studio/bu-3.png"
  - "03-media/apptio-tbm-studio/navigate-enable-feature.png"
  - "03-media/apptio-tbm-studio/enabled-report.png"
  - "03-media/apptio-tbm-studio/email-report.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Email Subscription

This feature enables TBMAs to subscribe to email reports regularly. They can also include other users in these report subscriptions, who will be notified of the same.

- EmailSubscriptionsCreate
- EmailSubscriptionsFilteredCreate

- For security reasons, an email can be sent only to the authorized domains in the customer's environment. For example, to the customer acme, adding an email for jdoe@acme.com would work, but adding an email for jdoe@xyz.com will not work.
- RLS (Row Level Security) is not supported in the Email Subscriptions

## Create Email Subscription

Navigate to any report, expand the Export icon and then select Email Subscription . This option will appear only for TBMAs.

The Email Subscriptions popup appears.

Enter values in the following fields. The * indicates a mandatory field.

| Field | Description |
| --- | --- |
| Report Collection* | The value is auto-populated with the name of the report collection that the report you are viewing. You can change the value by selecting from the dropdown list. |
| Report Name* | The value is auto-populated with the name of the report you are viewing. You can change the value by selecting from the dropdown list. |
| Subscription Name* | The name is auto-populated as <Report Collection - Report Name>. You can edit this name or enter a new name. |
| Define email body | From 12.11.9, select this option to change the subject and description of the email that is sent to the subscriber. You can enter a maximum of 3000 characters in the email body. |
| Include PDF in attachment | From 12.11.9, select this option to see a PDF version of the report attached in the email. |
| Bulk Upload XLS | Select this toggle if you want to send bulk email subscriptions with filters. If this option is enabled, the Recipients field will be disabled. |
| Recipients* | Enter the email id of those who must receive the email subscriptions. From 12.11.8, it is possible to input a valid email address from one of the supported domains manually. |
| Reporting Period | The report will be generated based on this time period. Select one of the options: Current Period If the Enable Default Time Period is not selected, this will be the default selection. If this radio button is enabled then the user will get an email/pdf for the Current calendar month. Previous Period If this radio button is enabled then the user will get an email/pdf for the Previous month i.e, If Default Period is enabled in the "Project Time Settings" --> Previous Period = Default Period - 1 If Default Period is disabled in the "Project Time Settings" --> Previous Period = Current Period - 1 Default Period (default)- This option appears only if you select the Enable Default Time Period under Project tab >� Time Settings option. If this radio button is enabled then the user will get an email/pdf for the Default month that is set in the "Project Time Settings" |
| With Filters | From 12.11.11, select this toggle to subscribe to filtered email reports. |
| Frequency | Select one of the options: Daily (default) Weekly - Select the days Monthly - This is a default selection. Select the date Send Time *: Select a time from the dropdown. It is defaulted to your current time zone. Day *: Select the day of the month from the dropdown. |
| Subscription Ends | Select one of the options: Never (default) or On a Date - enter or select a future date, in <dd-mm-yyyy> format. |
| Manage Subscriptions | Select this link to view, edit, and delete the email subscriptions. |

After entering values in all the fields, select the Subscribe button. A confirmation message " Report subscribed successfully! " appears. The subscription added here will be available in the Manage Subscriptions popup.

## Manage Subscriptions

- View, search, or edit any of the subscriptions.
- The Delete Subscription(s) icon appears in version 12.11.11 and later.
- Use the pagination option to navigate to the subscriptions.

Select the View by user checkbox to view subscriptions by all the users who are part of subscriptions.

Select the User link to view the list of reports they have subscribed to.

## Enable/ Disable Email Subscriptions

- Immediate Subscription Triggering : Trigger (enable) subscriptions immediately after the Monthly End Process (MEP), ensuring timely updates and notifications.
- Subscription Pausing : Prevent email overload by pausing (disable) subscriptions during specific periods, allowing for better email management.

On selecting the Enable option, the subscription row is disabled and the message appears as “ Your email subscription has been paused. You will not receive further emails until it is resumed ”.

## Send Now

Applies to : 12.11.12 and later

The Send Now feature allows administrators a convenient way to verify that the email subscription is working as intended, ensuring that subscribers receive the expected content. By using this feature, they can confidently test their email subscriptions, making it easier to manage and maintain their subscriptions.

The Send Now feature is accessible from two locations:

Under the Manage Subscriptions popup, for every email subscription

On the edit screen of an individual email subscription.

Before you use Send Now on the edit screen, you must first save any changes made to the subscription details. If changes are made but not saved, the Send Now button will be disabled until the changes are saved. Once saved, you can select Send Now to send a test email to the subscribers, providing a quick and easy way to test and verify your email subscriptions.

## Define email body

Select this option to change the subject and description of the email that is sent to the subscriber.

Email subject and body are customizable. From 12.11.12, there is a provision to add dynamic variables like report name, reporting period and filters. These variables are then substituted with the actual values in the emails.

When you receive the email subscription, the

Email Subject appears as <Report Name> MMM_YYYY {filter1 condition = value}; {filter2 condition = value}; { ... }

Email Body appears as

Your subscribed TBM Apptio report is ready : <Report Name> report for the period of <MMM_YYYY>

- Project Name and ID = XXXX

The PDF file name or attachment as <Report_Name>_MMM_YYYY .pdf

The name of the button in the email will read as View full report in Apptio .

## PDF Option for Simple Reports

Administrators can create simple PDF reports for email subscriptions that have a clean print view. Follow the below screens for the process.

Note that:

If a simple view of a report exists, then the PDF attachment will include the simple view of the report in the email subscription.

If a simple view of a report does not exist, then the PDF attachment will include the "print layout view" of the report in the email subscription.

## Email Subscriptions with Filtered View

This feature allows users to share filtered reports with specific recipients through a subscription system. The recipient receives a hyperlink to access the report with pre-applied slicer selections, along with the option to receive an attached PDF document. The PDF can be configured to include or exclude the linked Simple View while maintaining the selected filter settings.

Navigate to the Email Subscription popup.

Swipe the Filtered Views toggle. The Filter By* drop down appears.

From 12.11.14, you can select a value from the drop down or do a partial search by entering the keyword.

Enter values in rest of the fields and select the Subscribe button. A confirmation message " Report subscribed successfully! " appears.

The recipient will receive an email with link to the report with the filtered views.

## Duplicate Email Subscriptions

This feature allows users to duplicate the existing subscriptions, and avoid creating them from scratch. You cannot duplicate multiple subscriptions at once.

Select Manage Subscriptions link in the Email Subscription popup.

Select any subscription - the Duplicate Subscription icon appears on the top right. This icon appears only on selecting a single subscription.

On selecting the Duplicate Subscription icon, a new popup will appear with all fields pre-populated to match the original subscription.

Make the appropriate changes and then select the Subscribe button.

## Table Upload

The table upload feature is designed for unique email report distribution to thousands of recipients. This feature allows a single report email subscription to include multiple unique, filtered report views for each recipient (or a group of recipients).

From the Email Subscription popup, swipe the Bulk Upload XLS toggle.

The option for uploading the table appears, and the Recipients and With Filters fields disappear.

- Drag and drop or attach file using Browse Computer link.
- Click the Blank Template link to download the template, fill it, and then upload using the Browse Computer link. The template table will be downloaded based on the available filtered columns.

If the file type is not valid, an appropriate error message will appear. The Subscribe button will be disabled until the file upload is successful.

Close the message and re upload the file in correct format. A successful upload message appears as shown.

After successful file upload, the Subscription Rules File link is enabled, indicating that a file/data is already available.

Once you enter all the other details, click the Subscribe button. The table is validated for data integrity and accurate report distribution. For example, the recipients column must contain valid email addresses and not left empty. Additionally, the column names and their respective data types must align correctly - an email address should not be entered into a column of string data, and similarly, string data should not be entered into a column expecting numerical or date values.

## LLM-Enabled Report Insights

This feature allows you to include report insights in email subscriptions to receive AI-generated summaries and month-over-month comparisons. By default, report insights are disabled. When enabled, the email includes:

- A summary of the selected reporting period.
- A comparison with the previous period.

![Enable Feature](../../resources/images/studio_images/navigate-enable-feature.png)

![Enabled Report Insights](../../resources/images/studio_images/enabled-report.png)

- Summary of report data
- Period-over-period comparison

![Email with report insights](../../resources/images/studio_images/email-report.png)
