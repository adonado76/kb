---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "Setting up Time Zone Preferences"
breadcrumb:
  - "Cloudability Premium"
  - "Setup"
source_path: "product/manage-profile.html"
images:
  - "images/Default_Cost_Metric_Config.png"
  - "images/share_and_subscribe_to_reports,_alerts,_and_emails_6.jpg"
  - "images/share_and_subscribe_to_reports,_alerts,_and_emails_7.jpg"
  - "images/share_and_subscribe_to_reports,_alerts,_and_emails_8.jpg"
  - "images/share_and_subscribe_to_reports,_alerts,_and_emails_9.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Setting up Time Zone Preferences

In Cloudability , time zone preference can be set or updated
using the following steps:

1. Click the  **User**  icon at the top right and select  **Manage Profile**  .
2. Click the  **PREFERENCES**  tab, and define the define default View and Time zone under the
    **View and Timezone**  section . The timezone will be used as your Cloudability timezone.

**Subscribe to Summary Emails**

Send your most important cloud data to your email at time intervals you define.

To configure your cloud spend summary emails:

1. To define how often you’d like to receive your emails, in the Cloud Spend Summary Emails
   section, select an option from the EMAIL FREQUENCY list: Daily, Weekly, Monthly, Quarterly or Off.
2. Select the  PREFERENCES  tab.
3. To define how often you’d like to receive your emails, in the  Cloud Spend Summary
   Emails  section, select an option from the  EMAIL FREQUENCY 
   list.   

   ![cloud spend summary email screenshot  ](../../../../03-media/cloudability-premium/images/share_and_subscribe_to_reports,_alerts,_and_emails_6.jpg)

   Selecting  Off  opts you out of summary emails.
4. To set your cost metric, click the list under  Cost Metric for Mail  and
   select an option.   
   ![cost centric screenshot  ](../../../../03-media/cloudability-premium/images/share_and_subscribe_to_reports,_alerts,_and_emails_7.jpg)
     
    When you have linked accounts within a Consolidated Billing account family, AWS
   includes a blended rate and unblended rate in your detailed billing reports. If you're using
   Reserved Instances, it may make sense for you to report based primarily on Unblended cost.   
     
    NOTE  : To use amortized costs, your default view cannot include a tag-based
   filter. Estimates will reflect  Cost(Total)  if  Cost(Amortized)
    is selected.
5. To set your budget, click the drop-down under  Budget for Mail  and
   select an option.   
   ![budget for email screenshot](../../../../03-media/cloudability-premium/images/share_and_subscribe_to_reports,_alerts,_and_emails_8.jpg) Your cloud spend summary email will look something like this:
   ![success screenshot  ](../../../../03-media/cloudability-premium/images/share_and_subscribe_to_reports,_alerts,_and_emails_9.jpg)

**Choice of delivery for delayed organizations**

*This is a custom setting for accounts using Cloudability Enterprise and must be enabled by the
Cloudability Success team.*

If your data is consistently delayed from AWS (due to data volume or parsing done before sending
it to Cloudabiilty), this could create a scenario where users consistently get the new Data Delayed
email. To prevent this, we've added an option that lets your users select when to receive their
mail. They can choose to get their mail with the  most up-to-date data 
(regardless of freshness) or opt to wait until we have the  The last complete day
 . The former is the default.

**Understanding the metrics** 

- Month-to-Date Spend  : See how much you've spent this month, then
  compare that to your spend on this date last month.
- Est. Monthly Spend  : See how much you're estimated to spend this month
  based on a rolling average over a user-defined number of days, then compare that to last month's
  total.
- Yesterday's Spend  : This number reflects your estimated spending for
  the day prior to your receipt of the email.
- Cost  : This section of Daily Mail will list the AWS accounts and the
  AWS Services (such as RDS, Elastic Compute Cloud, etc.) which have generated the most spending this
  month to date.
- Month-to-Date Usage Hours  : See how many hours of usage you've
  generated this month, then compare that to your usage hours on this date last month.
- Yesterday's Usage Hours  : This number reflects how many hours of usage
  you generated for the day prior to your receipt of the email, and compare that total to the day
  before.
- Yesterday's Running Instance Count  : See how many instances yesterday's
  usage hours spanned across, and compare that total to the day before.
- Usage  : See the five most recent instances that have been started on
  your account.
- Email Settings  : Drill into the data that matters to you with settings
  that allow you to filter by View, exclude certain spending types such as taxes or one-time costs,
  and choose whether your data is calculated using Blended or Unblended cost.

Note: If you have incomplete data from your cloud vendor due to data update schedules, the delivery
of your daily cloud spending email may be delayed. For example, if you do not have complete data
through the end of the previous day (UTC), then you can expect your email to be delivered around 10
am Pacific time to allow for complete data to be received and processed. This minimizes occurrences
of  Yesterday's Estimated Spend  being under reported due to incomplete data
from the cloud vendor for that time period.

Configuring the default cost metrics for your org

Each module in Cloudability (eg: True Cost Explorer, Rightsizing etc.) supports a specific set of cost metrics like Cost (Total), Cost (List),
Cost (Amortized) etc. While Cost (Total) is the default cost metric for these modules, an admin user can change this and set it to a different default
cost metric by navigating to  **Manage Profile > Organization Settings**  page.

![screenshot for default cost metric config](../../../../03-media/cloudability-premium/images/Default_Cost_Metric_Config.png)

This screen would display all Cloudability modules that support more than 1 cost metric, along with a drop down that
contains the list of metrics that are currently supported for that respective module. As an admin user, you can choose your
preferred cost metric for each of the modules and click  **Save Default Cost Metrics**  button at the bottom which will apply your
changes across users in your entire Cloudability org.
