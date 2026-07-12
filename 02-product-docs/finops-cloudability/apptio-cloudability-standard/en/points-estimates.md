---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Estimates"
breadcrumb:
  - "Cloudability API"
  - "Budgets & Forecasting End Points"
  - "Estimates"
source_path: "SSVCLNQ/api-v3/estimates.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Estimates

Generating an Estimate

Arguments

| Argument | Required | Description |
| --- | --- | --- |
| viewId | Yes | The id of the view you are generating the estimate for. viewId=0 will apply estimate to all cost data. |
| basis | Yes | The cost basis for the estimate. examples: basis=cash basis=amortized basis=adjusted basis=adjustedAmortized basis=list |

The Estimate Object

Summary Block - Here are the headline figures for your estimate

estimatedSpend (number) - estimated spending for the current month

previousMonthSpend (number) - total spending in the previous month

cumulativeMtdSpend (array) - list of spending objects. Each object includes date and value.

previousMonthFinalized (boolean) - whether the invoice for the prior month is finalized

currentDate (string) - effective date for the estimate

details Block - a list of Spending Driver objects defined by serviceName/usageFamily combinations. Each object contains:

serviceName (string) - Vendor service name such as AWS EC2, AWS RDS...

usageFamily (string) - Type of cost activity such as Instance Usage, Storage...

previousMonthSpend (number) - How much was spent on this item last month

mtdSpend (number) - current month spending to date for this item

estimatedSpend (number) - Estimated spend for this item at end of month

Cumulative Month-To-Date Spend(cumulativeMtdSpend) Block - a list of date-spend objects

date (string) - Date of spend YYYY-MM-DD

spend (number) - Spend for that date in USD.

Example Estimate Object

In this sample response, we're only showing the first three entries of "cumulativeMtdSpend" and "details" for readability purposes.

```
{
  "result": {
    "estimatedSpend": 138429.32,
    "previousMonthSpend": 142252.16238499997,
    "previousMonthFinalized": true,
    "currentDate": "2018-06-11",
    "cumulativeMtdSpend": [
      {
        "date": "2018-06-01",
        "spend": 10418.500360999999
      },
      {
        "date": "2018-06-02",
        "spend": 14226.970056999999
      },
      {
        "date": "2018-06-03",
        "spend": 18270.250674
      }
    ]
  },
  "details": [
    {
      "serviceName": "AWS EC2",
      "estimatedSpend": 54638.37,
      "mtdSpend": 23101.275903,
      "previousMonthSpend": 56600.280253,
      "usageFamily": "Instance Usage"
    },
    {
      "serviceName": "AWS Support",
      "estimatedSpend": 15000,
      "mtdSpend": 0,
      "previousMonthSpend": 15000,
      "usageFamily": "Support"
    },
    {
      "serviceName": "AWS RDS",
      "estimatedSpend": 13761.53,
      "mtdSpend": 5101.559999999999,
      "previousMonthSpend": 13690.639,
      "usageFamily": "Instance Usage"
    }
  ]
}
```

Example Estimate Request

Retrieve Current Month Estimate

Quite simply perform a GET request at the /estimate end point, specifying a cost basis.

You must supply a viewId for your request. Set viewId=0 to see the estimate for all of your spending.

```
curl "https://api.cloudability.com/v3/estimate?basis=cash&viewId=11235"\\
     -u ‘[auth_token]:
```

The estimate endpoint is limited to 10 requests per user per minute and 20 requests per org per minute.
