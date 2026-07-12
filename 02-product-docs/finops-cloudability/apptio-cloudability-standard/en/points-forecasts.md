---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Forecasts"
breadcrumb:
  - "Cloudability API"
  - "Budgets & Forecasting End Points"
  - "Forecasts"
source_path: "SSVCLNQ/api-v3/forecasts.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Forecasts

Generating a Forecast

Arguments

| Argument | Required | Description | Type |
| --- | --- | --- | --- |
| viewId | Yes | The id of the view you are generating the forecast for. viewId=0 will apply forecast to all cost data. | string |
| basis | Yes | The cost basis for the estimate. Must be one of [cash, amortized, adjusted, adjustedAmortized, list] | string |
| monthsBack | Yes | How many months of history to use when predicting future costs. Must be between 3 and 24 | int |
| monthsForward | Yes | How many months of spending to forecast. Must be between 1 and 24 | int |
| useCurrentEstimate | No | Whether to include the current month estimate in spending model. Defaults to false. | bool |
| removeCredits | No | Whether to remove credits from the spending model. Defaults to false. | bool |
| removeOneTimeCharges | No | Whether to remove one time charges from the spending model. Defaults to false. | bool |

The Forecast Object

currentMonth (string) - the current month, format YYYY-MM

currentEstimate (number) - estimated spending for the current month

forecastTotal (number) - Total spending over the duration of your forecast

actualTotal (number) - Total spending over the comparison historical period

parameters (object) - The list of parameters used for your forecast

viewId (string)

monthsForward (integer)

monthsBack (integer)

basis (string)

useCurrentEstimate (boolean)

removeOneTimeCharges (boolean)

removeCredits (boolean)

actual - A list of month-spend objects for comparative historical cloud costs

month (string) - the month YYYY-MM

spend (number) - the recorded spend

actualDetail - A list of detailed month-spend objects for comparative historical cloud costs

month (string) - the month YYYY-MM

spend (number) - the recorded spend

serviceName (string) - The normalised service name. Example 'AWS EC2'

usageFamily (string) - The usage family. Example 'Instance Usage'

forecast - A list of month-spend objects for projected spend

month (string) - the month YYYY-MM

spend (number) - the projected spend

lowerBound (number) - projected lower bound of spend

upperBound (number) - projected upper bound of spend

forecastDetail - A list of detailed month-spend objects for projected spend

month (string) - the month YYYY-MM

spend (number) - the projected spend

serviceName (string) - The normalised service name. Example 'AWS EC2'

usageFamily (string) - The usage family. Example 'Instance Usage'

Example Forecast Object

In this sample response, we're only showing the first three entries of "actual," "actualDetail," "forecast" and "forecastDetail" for readability purposes.

```
{
  "result": {
    "parameters": {
      "viewId": "0",
      "monthsForward": 8,
      "monthsBack": 6,
      "basis": "cash",
      "useCurrentEstimate": false,
      "removeOneTimeCharges": false,
      "removeCredits": false
    },
    "currentMonth": "2018-09",
    "currentEstimate": 169444.38000000006,
    "forecastTotal": 1972164.1539731494,
    "actualTotal": 1518.7159940000001,
    "actual": [
      {
        "month": "2017-09",
        "spend": 187078.84031799991
      },
      {
        "month": "2017-10",
        "spend": 192950.680001
      },
      {
        "month": "2017-11",
        "spend": 170649.45000099996
      }
    ],
    "actualDetail": [
      {
        "month": "2017-09",
        "spend": 0.012558,
        "serviceName": "AWS API Gateway",
        "usageFamily": "API Request"
      },
      {
        "month": "2017-09",
        "spend": 2.6000000000000002e-05,
        "serviceName": "AWS API Gateway",
        "usageFamily": "Data Transfer"
      },
      {
        "month": "2017-09",
        "spend": 0.014471999999999999,
        "serviceName": "AWS Administrative",
        "usageFamily": "Other"
      }
    ],
    "forecast": [
      {
        "month": "2018-10",
        "lowerBound": 152748.68445406112,
        "spend": 204665.66745104585,
        "upperBound": 256582.65044803056
      },
      {
        "month": "2018-11",
        "lowerBound": 164779.69238992754,
        "spend": 217735.0150468521,
        "upperBound": 270690.3377037764
      },
      {
        "month": "2018-12",
        "lowerBound": 176197.59003756387,
        "spend": 230212.01914762674,
        "upperBound": 284226.4482576897
      }
    ],
    "forecastDetail": [
      {
        "month": "2018-10",
        "spend": 1.244314631343604,
        "serviceName": "AWS API Gateway",
        "usageFamily": "API Request"
      },
      {
        "month": "2018-11",
        "spend": 1.3898872510930294,
        "serviceName": "AWS API Gateway",
        "usageFamily": "API Request"
      },
      {
        "month": "2018-12",
        "spend": 1.528232288256353,
        "serviceName": "AWS API Gateway",
        "usageFamily": "API Request"
      }
    ]
  }
}
```

Example Forecast Request

Retrieve Current Forecast

Quite simply perform a GET request at the /forecast end point, specifying all required parameters.

```
curl "https://api.cloudability.com/v3/forecast?basis=cash&monthsForward=12&monthsBack=6&viewId=11235"\\
     -u ‘[auth_token]:’
```
