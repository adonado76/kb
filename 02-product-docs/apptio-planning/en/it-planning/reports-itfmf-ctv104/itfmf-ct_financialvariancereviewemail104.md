---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Financial Variance Review email report (v104)"
breadcrumb: []
source_path: "it-planning/reports-itfmf-ctv104/itfmf-ct_financialvariancereviewemail104.html"
images:
  - "resources/images/it_planning_images/itfmf-ct_images/itfmf-ct_financialvariancereview_email.jpg"
  - "resources/images/it_planning_images/itfmf-ct_images/itfmf-ct_financialvariancereview_emailbutton.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Financial Variance Review email report (v104)

◆ Applies to: Planning and Costing
Standard on TBM Studio 12.3 and later, with Template v104 and
later

The Finance Variance Review email report helps you understand budget variance and focus
your efforts to ensure that you meet your financial plan for the fiscal year. The email function is
limited to financial analysts with admin permissions, allowing them to send the variance report with
comments to department owners and other stakeholders.

## Display the report

1. Log in to Apptio and navigate to Planning > Costing
   Standard.
2. On the Home page, click IT Financials.

   The Financial Review report opens.
3. In the Financial Review report, click the Send Financial Budget Variance Email
   icon.

   NOTE: This email icon is only displayed for users with admin permissions.

   ![image](../../../../../03-media/apptio-planning/resources/images/it_planning_images/itfmf-ct_images/itfmf-ct_financialvariancereview_emailbutton.jpg)

   The Financial Variance Review email report opens.

1. Log in to Apptio and navigate to Costing Standard.
2. On the Home page, click IT Financials.

   The Financial Review report opens.
3. In the Financial Review report, click the Send Financial Budget Variance Email
   icon.

   NOTE: This email icon is only displayed for users with admin permissions.

   ![image](../../../../../03-media/apptio-planning/resources/images/it_planning_images/itfmf-ct_images/itfmf-ct_financialvariancereview_emailbutton.jpg)

   The Financial Variance Review email report opens.

TIP: If you are having trouble getting this report to open, do the following:

- Ensure that you are in the Production environment, by checking it is displayed in the
  toolbar. The email feature is not available in the Development or Staging
  environments.
- Check your browser settings. For example, you might have trouble in Chrome if your **Block 3rd
  Party Cookies** option is enabled. Alternately, consider adding "[https://[\*.]apptio.com](https://apptio.com/ "(Opens in a new tab or window)")" to your allowed sites in Chrome, or a
  similar setting in other browsers.

## Key elements

The report contains the following elements.

alt![image](../../../../../03-media/apptio-planning/resources/images/it_planning_images/itfmf-ct_images/itfmf-ct_financialvariancereview_email.jpg)

(1) Configure Email

- Filter Outliers Table - (Optional) Use the following settings to configure the
  Outliers table:
  - % Variance - Set a minimum variance percentage. As you adjust this value, the report will
    show outliers that exceed the percentage threshold.

    For example, a setting of "0%" returns all results, regardless of variance percentage. A setting
    of "50%" returns everything with an absolute variance greater than 50%.
  - $ Variance - Set a minimum variance dollar amount. The report will show outliers that
    exceed the dollar threshold.

    For example, a setting of "0" returns all results, regardless of dollar amount. A setting of
    "3000" returns items with an absolute variance over $3000.
  - Top Results - Set the number of outliers that you want to include in the report.

    For example, a setting of "10" will return the top 10 variances.

    The results displayed in the Outliers table are the accumulation of these settings. For
    example, settings of "50%," "5000," and "10," respectively, will return the top 10 results that have
    an absolute variance greater than $5,000 and over 50%.
- Recipients - (Optional) Click in the Add Recipients field to enter an email address
  for the person you want to receive this report, then press Enter. Repeat as many times as
  needed.

  After you have finished entering all comments, click Send to distribute the email to the
  list of recipients. The Add Comment and Save buttons are now disabled and the filters
  are inactive. To send another email, click Reset, which allows you to again edit the filters,
  make comments and send the report to a new recipient. Click Save to save your changes without
  sending the email.

  NOTE: You will normally only send one financial variance review email per month. The
  outlier filter and email recipients you set will persist to the following time periods until they
  are changed again and saved.

(2) Comment fields (optional)

You can add comments anywhere you find an Add Comment button. The top section is for
entering an overall message about the financial review for the month. Typically, you want to include
a high-level statement about the state of the budget and possibly explanations for significant
variances. The field is limited to 400 characters.

To edit a saved comment, click Edit Comment. To delete a comment, click **Edit
Comment**, remove the text in the comment box, then click Save.

(3) Operating Expenses YTD

This section displays your budget and variance at the highest level.

(4) Cumulative Budget Variance

This section displays the budget variance by period (column) and the YTD cumulative budget
variance (trend line). Ideally, the cumulative variance should approach or be trending to zero to
meet the financial plan.

(5) Accountability

This section displays your budget variance by owner, typically the CIO-1 level. A comment can be
added to explain any variance at this level.

(6) Outliers

This section displays your budget variance by cost center and account sub-group using the
parameters you set in the Configure Email pane (element 1). You can optionally enter
explanations for each.

(7) Details

Clicking the Questions link from the received email message will bring you to the budget
variance review report in Apptio.

## Questions answered

You can use this report to answer the following questions:

- Which cost centers are driving spend vs. plan variance?
- Which accounts within the cost center accountability are driving the greatest variance (over or
  under)?
