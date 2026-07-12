---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "RI Planner End Point"
breadcrumb:
  - "Cloudability API"
  - "RI Planner End Point"
source_path: "SSVCLNQ/api-v3/ri_planner_endpoint.html"
images:
  - "03-media/apptio-cloudability-standard/ri_top_of_planner.jpg"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# RI Planner End Point

Summary

The RI Planner end point can be used to generate a list of recommendations for reserving instances (RIs) based on parameters that suit your business. Done well reserved instances are a very powerful way to save money on your AWS bill and Cloudability supports planning for EC2, RDS, Redshift and Elasticache.

Special Note: RI planning is a rather complex activity and this end point matches that reality. The documentation here will focus on the most useful and common interactions for end users. Accordingly you'll find the documentation format to be slightly different to that of other end points.

- This end point does not support filtering and sorting.

End Point Particulars

These end points are readonly and are used for generating an RI plan(lists of RI recommendations)

End point : /reservations/aws/recommendations/ec2

End point : /reservations/aws/recommendations/rds

End point : /reservations/aws/recommendations/redshift

End point : /reservations/aws/recommendations/elasticache

Creating your RI Plan - Query Arguments

Arguments

| Argument | Required? | Description |
| --- | --- | --- |
| startDate | Yes | Start date for the window of instance usage you'd like to analyse in generating a plan. Format YYYY-MM-DD |
| endDate | Yes | End date for the window of instance usage you'd like to analyse in generating a plan. Format YYYY-MM-DD |
| vendorAccountIds | Yes | The unique ID provided by the cloud vendor for the account you wish to create an RI plan for. Format 1234-4567-8901 |
| include | No | You will nearly always want to use this parameter. Use cases: include=associatedAccounts when running against a master payer account to pickup linked account usage. include=associatedAccounts,costs to also return a cost summary for the plan include=associatedAccounts,costs,summary to also return summary info for each RI classification. See details below |
| excludedPricingOptions | No | Exclude partial-upfront , no-upfront or all-upfront payment types from the plan. If argument not included RI plan will be forced to partial-upfront . To exclude multiple types separate with comma: excludedPricingOptions=no-upfront,partial-upfront |
| offeringClass | No | Create a plan for convertible or standard RIs. Defaults to standard. |
| term | No | one-year or three-year . Defaults to one-year |
| scope | No | region or availabilityZone . Defaults to region |
| optimizations | No | all , no-mods or mods-only . mods-only . all returns all recommendations. mods-only only returns RI modification recommendations. no-mods removes RI modification recommendations from what is returned. Defaults to all . |
| usageThreshold | No | Set the waterline usage level requirement for the RIs. For a 90% waterline use: usageThreshold=90 |
| savingsThreshold | No | Set a minimum savings rate for individual RI purchases savingsThreshold=20 would only recommend RIs that save at least 20% over running on demand. |

Cost Summary

The Cost Summary provides a summary of the impact available by following all RI purchase recommendations. It is powerful in conveying the surface area that can be impacted with smart RI decisions. It is the API equivalent of this summary in the UI version of the planner

To get the cost summary returned add 'costs' to the include parameter, for example 'include=associatedAccounts,costs'. Example curl:

```
curl "https://api.cloudability.com/v3/reservations/aws/recommendations/ec2?startDate=2018-04-05&endDate=2018-04-19&include=associatedAccounts,costs&vendorAccountIds=1234-4567-8901" \\
-H "apptio-opentoken: [apptio opentoken]" -H "apptio-environmentid: [environment id]"
```

The Cost Summary Attributes

onDemandMonthlyCost (number) - For the reservation count recommended, what would this cost to run fully on demand per month (i.e. what would it cost if we didn't reserve these)

totalOnDemandCost (number) - For the reservation count recommended, what would this cost to run fully on demand for the term of the reservation.

uncoveredOnDemandCost (number) - This represents the total amount of on-demand usage that the plan does NOT cover with RIs for the full term of your plan. The RI planner makes sure to not recommend RIs for usage which falls below the break even point (for example cyclical or spiky usage).

onDemandUpfront (integer) - This attribute is just here for convenience to tell us that running instances on demand has zero upfront cost, hence the value is always zero (0).

reservationUpfront (integer) - The upfront payment associated with the purchase count recommended. For no upfront RIs this will always return as 0.

reservationTotalCost (number) - The total cost of reserving the recommended amount for the full term, including upfront and recurring costs.

reservationAmortizedMonthlyCost (number) - the monthly cost of the RI purchase including upfront and recurring elements. i.e reservationTotalCost divided by the RI term in months.

totalEstimatedSavings (number) - The total savings you would make by following all recommendations. equivalent to ( totalOnDemandCost - reservationTotalCost )

savingsRate (number) - effectively a decimal value representing your savings percentage for the combined value of all recommendations. Determined by the ratio between totalOnDemandCost and reservationTotalCost .

breakEvenThreshold - The percentage of utilization an RI requires for it to be 'profitable'. The higher the savings rate the less utilisation any RI requires to be viable.

daysToBreakEven - How many days before the combined RI purchases recommended fully break even. See this blog post and the definition of 'Total RI Cost Break Even" for more details.

Example Cost Summary

```
"costs": {
      "onDemandUpfront": 0,
      "onDemandMonthlyCost": 126962.695,
      "totalOnDemandCost": 1523552.34,
      "uncoveredOnDemandCost": 255138.69629,
      "reservationUpfront": 549100,
      "reservationAmortizedMonthlyCost": 90948.10733,
      "reservationTotalCost": 1091377.288,
      "totalEstimatedSavings": 432175.052,
      "savingsRate": 0.28366,
      "daysToBreakEven": 261.46309
    }
```

RI Purchase Summary

The RI Purchase Summary provides a consumable list of recommended RI purchases. You can think of each item in the list as an individual recommendation similar to what you see in the main page of Cloudability 's RI planner. Individual recommendations are essentially a classification that can be reserved into, for example r4.large Linux instances in the ap-southeast-2 region and will take into account characteristics such as ISF/region scoping depending on your scenario.

Special Note: Classifications will be listed for cases where any related instance happens to run in the time window or if an RI is owned regardless of whether an action is recommended. For example no action may be present if RI utilization would be below the break even point or if the specific classification is covered by a ISF recommendation. Use your client side tool to manage this as shown below using jq.

To get the purchase summary returned add 'summary' to the include parameter, for example 'include=associatedAccounts,summary'. Example curl:

```
curl "https://api.cloudability.com/v3/reservations/aws/recommendations/ec2?startDate=2018-04-05&endDate=2018-04-19&include=associatedAccounts,summary&vendorAccountIds=1234-4567-8901" \\
-H "apptio-opentoken: [apptio opentoken]" -H "apptio-environmentid: [environment id]"
```

The Purchase Summary Attributes:

Each recommendation in the list will contain these attributes:

classification (object) - An object that describes the classification you can reserve into.

regionZone (string) - The region or zone to reserve into.

instanceType (string) - The instance type to reserve against

platform (string) - For EC2 this will be the OS and RDS this will be the engine .

tenancy (string) - Applicable for EC2, shared or dedicated tenancy.

ownedQuantity (integer) - How many of this classification of RIs do you already own

ownedReservations (object) - An object that describes relevant RIs you already own

light (integer) - Active RIs of this deprecated RI type

medium (integer) - Active RIs of this deprecated RI type

heavy (integer) - Active RIs of this deprecated RI type

noUpfront (integer) - Active RIs purchased through On Upfront payment option

partialUpfront (integer) - Active RIs purchased through Partial Upfront payment option

allUpfront (integer) - Active RIs purchased through All Upfront payment option

allocationCounts (object) - An object that describes the means to achieve desired RI level

modifiedToCover (integer) - Instance count that can be gained by modifying an existing underutilized RI.

coveredByRegionalScope (integer) - Current RIs that cover usage via being regionally scoped, but not ISF.

coveredByAzScope (integer) - Current RIs that cover usage via being AZ scoped.

coveredBySizeFlexibility (integer) - Current RIs that cover usage via being ISF scoped.

buyToCover (integer) - Recommend RI count to purchase to reach desired level.

exchangeToCover (integer) - Recommended convertible exchange actions will result in this amount of new RIs

recommendedQuantity (integer) - Quantity of RIs to own for maximum savings

recommendedQuantityUsage (number) - The percentage utilization of the last RI recommended, i.e. the least utilized RI that still happens to be above the break even point.

alreadyCovered (integer) - How many of the desired quantity are covered by RIs already owned. See 'covered' items in allocationCounts attribute for a breakdown of this number.

ownedPoints (integer) - ISF related. How many 'points' do you already own within the family due to active ISF RIs. Similar to the AWS normalization factor , but we base our values on nano being equal to 1 instead of 0.25 (thus allowing us to avoid decimals).

reallocatedPoints (integer) - ISF related. The points within a classification that are actually recommended to be modified out to a different classification.

unusedPoints (integer) - ISF related. The owned points within a classification that aren't currently used and can't be modified to salvage them.

totalHoursRunning (integer) - How many hours in your time window of analysis is there at least 1 instance running for the classification.

reservationCost (object) - A cost summary object as described above , but in this case being specific to just this classification.

Example Purchase Summary

```
"summary": {
      "coverage": [
        {
          "classification": {
            "regionZone": "ap-southeast-2",
            "instanceType": "r4.large",
            "platform": "linux",
            "tenancy": "shared"
          },
          "ownedQuantity": 37,
          "ownedReservations": {
            "light": 0,
            "medium": 0,
            "heavy": 0,
            "noUpfront": 0,
            "partialUpfront": 37,
            "allUpfront": 0
          },
          "allocationCounts": {
            "modifiedToCover": 0,
            "coveredByRegionalScope": 0,
            "coveredByAzScope": 0,
            "coveredBySizeFlexibility": 37,
            "buyToCover": 25,
            "exchangeToCover": 0
          },
          "recommendedQuantity": 62,
          "recommendedQuantityUsage": 0.90,
          "alreadyCovered": 37,
          "ownedPoints": 592,
          "reallocatedPoints": 0,
          "unusedPoints": 0,
          "totalHoursRunning": 360,
          "reservationCost": {
            "onDemandUpfront": 0,
            "onDemandMonthlyCost": 2912.7,
            "totalOnDemandCost": 34952.4,
            "uncoveredOnDemandCost": 0,
            "reservationUpfront": 10475,
            "reservationAmortizedMonthlyCost": 1748.91667,
            "reservationTotalCost": 20987,
            "totalEstimatedSavings": 13965.4,
            "savingsRate": 0.39955,
            "breakEvenThreshold": 0.60045,
            "daysToBreakEven": 219.16249
          }
        }
      ]
    }
```

Example Requests

A Three Year, All Upfront, Convertible RI Plan with 100% utilisation

```
curl "https://api.cloudability.com/v3/reservations/aws/recommendations/ec2?startDate=2018-04-05&endDate=2018-04-19&include=associatedAccounts,costs&vendorAccountIds=1234-4567-8901&usageThreshold=100&offeringClass=convertible&term=three-year&excludedPricingOptions=no-upfront,partial-upfront" \\
-u ‘[auth_token]:’
```

List Out All Buy Recommendations, Order by Highest Savings First

Important : This is effectively the list of recommendations you get when you go into the Cloudability RI planner and run a default plan.

```
curl "https://api.cloudability.com/v3/reservations/aws/recommendations/ec2?startDate=2018-04-05&endDate=2018-04-19&include=associatedAccounts,summary&vendorAccountIds=1234-4567-8901" \\
-u ‘[auth_token]:’ | jq '.result.summary.coverage | sort_by(.reservationCost.totalEstimatedSavings) | reverse'
```

Print Classification Details, Savings, and Buy Count for Highest Savings RIs

This is the same request as above. We are using jq to print out a very human friendly version of the list of recommendations.

```
curl "https://api.cloudability.com/v3/reservations/aws/recommendations/ec2?startDate=2018-04-05&endDate=2018-04-19&include=associatedAccounts,summary&vendorAccountIds=1234-4567-8901" \\
-u ‘[auth_token]:’ | jq '.result.summary.coverage | sort_by(.reservationCost.totalEstimatedSavings) | reverse | .[] | .classification + {savings: .reservationCost.totalEstimatedSavings} + {buy_count: .allocationCounts.buyToCover} '
```

List out Buy Recommendations with Savings over $10k

This is handy to remove no-action classifications and those with low savings figures.

```
curl "https://api.cloudability.com/v3/reservations/aws/recommendations/ec2?startDate=2018-04-05&endDate=2018-04-19&include=associatedAccounts,summary&vendorAccountIds=1234-4567-8901" \\-u ‘[auth_token]:’ | jq '.result.summary.coverage | .[] | select( .reservationCost.totalEstimatedSavings > 10000)'
```
