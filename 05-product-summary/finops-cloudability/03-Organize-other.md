---
source_system: "apptio-cloudability-standard"
practice: "finops"
language: "en"
doc_type: "cloudability-standard"
consolidated_file: "03-Organize-other"
source_files_count: 1
last_updated: "2026-07-13"
---

# 03-Organize-other

## Data Reprocess

<!-- sub-header -->
- **breadcrumb:** Setup > Data Reprocess
- **source_path:** SSVCLNQ/product/data_reprocess.html
- **original_file:** setup-data-reprocess.md
- **images:**
  - 03-media/apptio-cloudability-standard/data_reprocess_1.jpg
  - 03-media/apptio-cloudability-standard/data_reprocess_2.jpg
  - 03-media/apptio-cloudability-standard/dp10.jpg
  - 03-media/apptio-cloudability-standard/data_reprocess_4.jpg
  - 03-media/apptio-cloudability-standard/dp11.jpg
  - 03-media/apptio-cloudability-standard/dp2.jpg
  - 03-media/apptio-cloudability-standard/dp3.jpg
  - 03-media/apptio-cloudability-standard/dp4.jpg
  - 03-media/apptio-cloudability-standard/dp5.jpg
  - 03-media/apptio-cloudability-standard/dp6.jpg
  - 03-media/apptio-cloudability-standard/dp7.jpg
  - 03-media/apptio-cloudability-standard/dp8.jpg

## Data Reprocess

Data Reprocess for Cloudability users

Data Reprocess for Cloudability - Costing & Planning users

Data Reprocess for Cloudability users

Typically, when you modify your business strategy, there is a need to adjust Business Mappings, Account Groups, and Tags & Labels in Cloudability with a retrospective refresh of historical data. This is where a data reprocess comes into the picture. If you are a Cloudability customer you might only need reprocessing within Cloudability. You can perform a self-service Data Reprocess to reprocess the data without depending on the Support or Customer Success teams.

The feature is not enabled by default as this is an Opt-in feature. Reach out to Support Team or your Customer Success Manager to get this feature enabled.

1. Navigate to Organize > Data Reprocess , and by default the Job Status ’ tab is displayed. This tab will have a list of your previous requests.
1. Navigate to New Request tab, enter the Job Name (for your identification), Start Date, End Date, and Reason. Select Start Reprocess button to submit the request. Note: You are provided with 12 Month-units for which reprocess can be requested in a month. Month-units : Each month of data reprocess is considered a Month-unit. For example, If you submit one reprocess request for the period of 12 months, you will consume 12 Month-units. If you submit two reprocess requests for three months each, you will consume six Month-units. The total Month-units and the remaining Month-units are displayed at the top. The maximum lookback period is 12 months for which a reprocess can be requested. Month-units being used by your current selection are displayed below the End Date. If the selection exceeds the remaining Month-units, an error message will be displayed at the bottom right. If the job fails for a specific month, your Month-units are not counted for that month, and you can resubmit the job for that specific month.
1. On submitting the Start Reprocess request, a confirmation message is displayed at the bottom right and you will be redirected to the Job Status tab.
1. The Job Status tab displays the status of your current and past jobs. You can also expand the Job ID and see the statuses of each month. Select Refresh to refresh the status page. Note: Once the reprocess request is submitted, it cannot be canceled. Two reprocess requests cannot be running at the same time for the overlapping period or month. However, you can submit two reprocess requests at the same time if there is no overlap in the period or the months selected. If you just need to reprocess your current month data, there is no requirement to submit a request. Cloudability already reprocesses the current month data on a daily basis which should be available in 24 hours.

When to contact TAM/CSM/Support

- The job fails more than once.
- You’ve exhausted your monthly limit of month-unit and there is an urgent business need to reprocess the data.
- You have feedback or any other issues.

Data Reprocess for Cloudability - Costing & Planning users

If you use Costing & Planning , then you might want to bring your cloud data to Costing & Planning from Cloudability or use Cloud Data Ingestion (CDI). However, there can be ongoing changes to your organization's business strategies, new accounts and applications may be added, or tagging strategy can change. Due to these changes, you might want to reprocess the data so that it applies any new additions or changes retrospectively and want to push this data to Costing & Planning .

This feature is on HOLD for customers having Apptio Costing & Planning offering along with Cloudability or CDI. We are actively working on enhancing the experience and expect to launch the improved feature early next year. Cloudability customers with Costing & Planning who already had access will continue to retain that access.

1. Navigate to Organize > Data Reprocess , and by default the Job Status tab is displayed. This tab will have a list of your previous requests.
1. Navigate to the New Request tab and the default Tags & Labels step is displayed. You may select/unselect specific tags and labels that you want to export/bring to Costing & Planning . Note: Changes in this selection only apply to data being exported to Costing & Planning or TBM Studio . All the business dimensions (Tags & Labels, Account Groups, and Business Mappings) get reprocessed for Cloudability. However, if you only intend to request a reprocess without changing data export to Costing & Planning or TBM Studio , continue to the last step to submit your request..
1. Select Next to select/unselect the Account Groups .
1. Select Next to select Business Mappings .
1. Select Next and review the selection you have made.
1. Select Next and the job submission page will be displayed. Enter the Job Name (for your identification), state date and end date, and Reason. Select the Start Reprocess button to submit the request. Note: You are provided with 12 Month-units for which Reprocess can be requested in a month. Month-units: Each month of data reprocess is considered a Month-unit. For example, if you submit 1 reprocess request for the period of 12 months, you’ll consume 12 month-unit. If you submit 2 reprocess requests for 3 months each, you’ll consume 6 month-unit. The total Month-units and remaining Month-units are displayed at the top. The maximum lookback period is 12 months for which reprocess can be requested. Two reprocess requests cannot be running at the same time for the overlapping period or month. However, you can submit 2 reprocess requests at the same time if there is no overlap in the period or the months selected. Month-units being used by your current selection are displayed below the End Date. If the selection exceeds the remaining month-units, it shows the message at the bottom right. If the job fails (the overall status of the job is ‘FAILED’), you’ll need to run the reprocess all over again for the same period.
1. On submitting the Start Reprocess button, a confirmation message is displayed at the bottom right and will be redirected to the Job Status tab.
1. The Status tab displays the status of your current and past jobs. You can also expand the Job ID and see the statuses of each month. Select Refresh to refresh the status page. Note: Only Tags & Labels, Account Groups and Business Mappings are selectable. Business Mappings containing Resource ID and/or Date columns in their definition will not be supported in Costing & Planning or TBM Studio . All Business Metrics that are set up will automatically flow to Costing & Planning . All default fields will continue to flow to Costing & Planning as before. Once the reprocess request is submitted, it cannot be canceled. When the request completes (Status = Done), you can run the (Data Link connector) DLC to pull the data to Costing & Planning . If you just need to reprocess your current month data, there is no requirement to submit a request. Cloudability already reprocesses the current month data on a daily basis which should be available in 24 hours.

When to contact TAM/CSM/Support

- The job fails more than once.
- You’ve exhausted your monthly limit of month-unit and there is an urgent business need to reprocess the data.
- You have feedback or any other issues.

---
