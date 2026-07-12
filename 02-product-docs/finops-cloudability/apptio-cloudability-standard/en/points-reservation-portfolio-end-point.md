---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Reservation Portfolio End Point"
breadcrumb:
  - "Cloudability API"
  - "RI Portfolio End Points"
  - "Reservation Portfolio End Point"
source_path: "SSVCLNQ/api-v3/reservation_portfolio_endpoint.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Reservation Portfolio End Point

Summary

The RI Portfolio end point can be used to retrieve a detailed list of all Reserved Instances (RIs) as well as understand how well utilized these reservations were over a particular period of time.

Learn more about the Reservation Portfolio.

Included examples in this document will focus on compute reservations an commitments but the patterns for other supported AWS services (i.e. RDS, Redshift and ElastiCache) are consistent with EC2 examples.

End Point Particulars

The end points are read-only for retrieving a list of Reservation Objects

- AWS EC2 RI end point : /reservations/aws/savings/ec2
- AWS Savings Plan end point : /reservations/aws/portfolio/savingsPlan
- **Azure compute RI end point **: /reservations/azure/portfolio/compute
- GCP compute CUD end point : /reservations/gcp/portfolio/ce
- AWS RDS RI end point : /reservations/aws/savings/rds
- AWS Redshift RI end point : /reservations/aws/savings/redshift
- AWS ElastiCache end point : /reservations/aws/savings/elasticache

AWS RI Arguments

| Argument | Required? | Description | Type |
| --- | --- | --- | --- |
| start | yes | Beginning of time window to look for RI usage, e.g. "2018-01-01" | string |
| end | yes | End of time window to look for RI usage e.g. "2018-01-01" | string |
| basis | no | Defaults to 'cash' though you may pass 'adjusted' to see savings net of any custom pricing rules | string |
| viewId | no | Defaults to 0. Only account-group based views are supported | integer |

The AWS Reservation Object

- availabilityZone (string): If applicable
- count (integer): Number of reserved instances in the RI
- duration (integer): duration of the RI in seconds
- end (string): The timestamp when the RI ends e.g., '2018-07-06T18:00:00Z'
- instanceType (string): e.g., 'r3.large'
- multiAz (string): Single-AZ or Multi-AZ (RDS only)
- netSavings (number): Total savings, reflecting the difference between what you paid for an RI and how much the hours you actually consumed would have cost if purchased On-Demand
- offeringClass (string): 'standard' or 'convertible
- offeringType (string): 'NoUpfront ', 'PartialUpfront' or 'AllUpfront'
- operatingSystem (string): Software and associated licensing info. e.g., "Linux" or "Windows with SQL Server Standard
- overallUtilization (number): The percent of purchased hours that were applied to a running instance
- region (string): e.g., 'us-east-1',
- reservationIdentifier (string): The vendor supplied unique id for your reservation
- scope (string): 'Region' or 'Availability Zone'
- start (string): The timestamp when the RI begins e.g., '2018-07-06T18:00:00Z'
- state (string): 'retired' or 'active'
- tenancy (string): 'default' or 'dedicated'
- term (integer): duration of the RI in years
- units (integer): number of ISF-Normalized hours in the RI
- unrealizedSavings (number): Any additional savings you could have achieved assuming complete RI utilization
- vendorAccountId (string): 12 digit string corresponding to your AWS account ID

Example AWS Reservation Object

```
{
  "result": [
    {
      "availabilityZone": "",
      "count": 1,
      "duration": 10368000,
      "end": "2018-11-03T16:17:39Z",
      "instanceType": "t2.large",
      "multiAz": "(not set)",
      "netSavings": 25.416000000000015,
      "offeringClass": "standard",
      "offeringType": "NoUpfront",
      "operatingSystem": "Linux",
      "overallUtilization": 1,
      "region": "us-east-1",
      "reservationIdentifier": "0202a336-1712-1712-1712-0202a336",
      "scope": "Region",
      "start": "2018-07-06T18:00:00Z",
      "state": "active",
      "tenancy": "default",
      "term": 1,
      "units": 4,
      "unrealizedSavings": 0,
      "vendorAccountId": "0123456789"
    }
  ]
}
```

Example AWS Reservation Portfolio Requests

List Subscriptions

The following will list any EC2 reservations that were active between March 1 and March 15, 2018 and with no view restrictions.

```
curl "https://api.cloudability.com/v3/reservations/aws/savings/ec2?basis=cash&start=2018-08-01&end=2018-08-15&viewId=0" \\
     -u ‘[auth_token]:’
```

AWS Savings Plan Arguments

| Argument | Required | Description | Type |
| --- | --- | --- | --- |
| filter | No | Attributes Measure(field) and value that savings plans in response must have. E.g. ‘InstanceFamily’ ‘r5’ | string |
| limit | No | Part of pagination range request for maximum count per page. | integer |
| offset | No | Part of pagination range request designating the first asset to be returned in the response. | integer |
| sortOrder | No | Measure(field) and direction (ascending/descending) order of assets in response. | string |
| viewId | No | Cloudability ViewID to be respected in response. | integer |

The AWS Savings Plan Object

- vendorAccountId (string): 12 digit string corresponding to your AWS account ID
- savingsPlanId (string): the vendor assigned identifier for the Savings Plan
- savingsPlanArn (string): The vendor assigned Savings Plan unique global identifier
- duration (integer): duration of the savings plan in seconds
- start (integer): The Epoch millisecond formatted time stamp of the Savings Plan becoming active
- end (integer): The Epoch millisecond formatted time stamp of when the Savings Plan will terminate
- term (integer): Savings Plan Term length in years
- type (string): Savings Plan type (EC2 or Compute)
- state (string): Current state of the Savings plan (e.g. Active)
- region (string): EC2 Savings Plan region designation (not applicable for Compute plans)
- ec2InstanceFamil (string): EC2 Savings Plan applicable instance family designation (not applicable for Compute plans)
- offeringType (string): Payment method/model designation (e.g. No Upfront)
- hourlyCommitment (integer): Hourly Savings Plan monetary commitment
- totalCommitment (integer): Total monetary commitment over the life of the savings plan
- currencyCode (string): Monetary units for Savings Plan hourly and total commitment
- upfront (integer): Initial payment made at inception of Savings Plan
- frequency (string): Applicable pricing interval units
- amount

(integer): Applicable pricing per frequency unit specified

Example AWS Savings Plan Object

```
{
  "result": [
    {
      "vendorAccountId": "############",
      "accountName": "AWS Consolidated Master",
      "savingsPlanId": "xx###x##x-xxxx-#xxx-xx##-x####x###xxx",
      "savingsPlanArn": "arn:aws:savingsplans::############:savingsplan/xx###x##x-xxxx-#xxx-xx##-x####x###xxx",
      "description": "1 year No Upfront r5 EC2 Instance Savings Plan in us-east-1",
      "start": 1573079358000,
      "end": 1604615357000,
      "duration": 31536000,
      "term": 1,
      "type": "EC2Instance",
      "state": "active",
      "region": "us-east-1",
      "ec2InstanceFamily": "r5",
      "offeringType": "No Upfront",
      "hourlyCommitment": 1,
      "totalCommitment": 8760,
      "pricing": {
        "offeringId": "c#####xx#-xxx#-##xx-x##x-#xx####xx#x#",
        "currencyCode": "USD",
        "upfront": 0,
        "recurring": {
          "frequency": "Hourly",
          "amount": 1
        }
      },
      "tags": []
    },
    {
      "vendorAccountId": "############",
      "accountName": "AWS Consolidated Master",
      "savingsPlanId": "xx###x##x-xxxx-#xxx-xx##-x####x###xxx",
      "savingsPlanArn": "arn:aws:savingsplans::############:savingsplan/xx###x##x-xxxx-#xxx-xx##-x####x###xxx",
      "description": "1 year No Upfront Compute Savings Plan",
      "start": 1573145364000,
      "end": 1604681363000,
      "duration": 31536000,
      "term": 1,
      "type": "Compute",
      "state": "active",
      "region": "(not set)",
      "ec2InstanceFamily": "(not set)",
      "offeringType": "No Upfront",
      "hourlyCommitment": 1,
      "totalCommitment": 8760,
      "pricing": {
        "offeringId": "c#####xx#-xxx#-##xx-x##x-#xx####xx#x#",
        "currencyCode": "USD",
        "upfront": 0,
        "recurring": {
          "frequency": "Hourly",
          "amount": 1
        }
      },
      "tags": []
    }
  ],
  "meta": {
    "aggregate": {
      "quantity": 2,
      "hourlyCommitment": 2
    },
    "pagination": {
      "totalCount": 2
    }
  }
}
```

Example Savings Plan Inventory Request

List Savings Plans

The following will list the first 50 active or expired r5 EC2 Savings Plans in us-east-1 sorted by expiration date from those expiring soonest to those expiring farthest in the future.

```
curl "https://api.cloudability.com/v3/reservations/aws/portfolio/savingsPlan?filter&limit=50&offset=0&product=savingsPlan&sortOrder=%2Bend&viewId=0" \\
     -H "apptio-opentoken: [apptio opentoken]" -H "apptio-environmentid: [environment id]"
```

The Google Cloud Platform(GCP) Commitment Endpoint

The following api endpoint will provide a list of commitments.

The following curl will work with GET/ POST requests: GET with query parameters and POST with request body.

```
curl 'https://api.cloudability.com/v3/reservations/gcp/portfolio/commitment' 
	 -H 'accept: application/json, text/plain, /' 
	 -H 'accept-language: en-US,en;q=0.9' 
	 -H 'authorization: Bearer [auth_token]' 
	 -H 'content-type: application/json' 
	 --data-raw '{"start":"2025-02-28","end":"2025-03-30","basis":"adjusted","filter":"commitment_category==spend","viewId":0,"limit":10,"offset":0,"sortOrder":"-billingAccountIdentifier","service":"scud-groups","services":"compute_engine"}'
		
```

The following table lists the valid payload options:

| Payload Options | Valid Format | Details |
| --- | --- | --- |
| start | Date in the format “YYYY-MM-DD" |  |
| end | Date in the format “YYYY-MM-DD" |  |
| basis | adjusted, cost |  |
| filter |  | Look how filters get formed in the developer toolbar. |
| sortOrder | A valid field e.g. billingAccountIdentifier for ALL, netsavings for other CUDs. |  |
| services | Comma separated string with values from compute_engine cloud_sql | Current supported services include “compute_engine” and “cloud_sql”. |

For SCUDs, RCUDs or ALL commitments to be returned via these endpoints, use the following in filters along with dates.

| Commitments | Filter Values | Details |
| --- | --- | --- |
| Flex CUDs Commitments | "commitment_category==spend" | When commitment category as spend is provided, the above endpoint should return Flex CUDs commitments only. |
| RCUDs Commitments | "commitment_category==resource" | When commitment category as resource is provided, the above endpoint should return Resource CUDs commitments only. |
| All Commitments | No filter added | When no commitment category is provided as filter, Flex CUDs and RCUDs are returned as response by merging the results of RCUD and SCUD commitments |
| Cloud SQL CUDs | "commitment_category==spend" | "commitment_category==spend" with services in payload should be “cloud_sql” |

The Google Cloud Platform(GCP) Commitment Endpoint Object

- commitmentGroupId (string): The commitment group id for the group commitment belongs to.
- billingAccountIdentifier (string): Billing Account Identifier in which commitment belong to.
- term (integer): CUD term length in years.
- region (string): Text description of the CUD's assigned region e.g. 'us-central'.
- status (string): Current CUD status.
- hourlyCommitmentAmount (string): Hourly commitment amount.
- hourlyCommitmentCost (string): Hourly commitment cost that is being paid.
- totalCommitmentAmount (string): Hourly commitment cost that is being paid.
- totalCommitmentCost (string): Total commitment cost to be paid.
- commitmentCostRemaining (string): Commitment remaining cost.
- remainingCost (string): Remaining cost of the CUD to be paid.
- commitmentDiscountRate (string): Commitment discount rate percentage / 100.
- creation (string): The creation date of the CUD was requested
- start (string): The start date of when the CUD began applying to usage
- end (string): The CUD expiration date
- expirationDate (string): The CUD expiration date
- offer (string): CUD offer details if available.
- description (string): Description of the CUD.
- name (string): User assigned CUD name
- accountIdentifier (string): User assigned account ID
- memory (integer): MB of memory allocated (at 1024MB/GB)
- vcpus (integer): vCPUs allocated to the CUD
- duration (integer): Duration of the RI in seconds
- statusMessage (string): Long form status description and explanation
- type (string): Flex-CUD or CUD type of the CUD
- commitmentGroupDetails (object): Commitment group details object {}
- service : Service name CUD belongs to
- reservationId/ commitmentId (string): Unique identifier of the CUD.
- commitmentCategory
- (string): Commitment category, Spend or Resource.

Example GCP Commitment Endpoint Object

This is example response for ALL Commitments with 1 Flex CUD (SCUD) and 1 RCUD.

```
"result": [
  {
    "commitmentGroupId": "01E091-D83A6B-1F55DD:spend:COMPUTE_ENGINE:all-regions",
    "billingAccountIdentifier": "01E091-D83A6B-1F55DD",
    "term": 1,
    "region": "n/a",
    "quantity": 0,
    "status": "Active",
    "hourlyCommitmentAmount": 0.12,
    "hourlyCommitmentCost": 0.086397,
    "totalCommitmentAmount": 89.28,
    "totalCommitmentCost": 64.279011,
    "commitmentCostRemaining": 275.78,
    "commitmentDiscountRate": 0.280029,
    "creation": "2024-01-04",
    "start": "2024-01-04",
    "end": "2025-01-04",
    "expirationDate": "2025-01-04",
    "offer": "services/compute.googleapis.com/standardOffers/ffe0f6a3-2f98-437e-8d49-fc443a05d3c2",
    "description": "billingAccounts/01E091-D83A6B-1F55DD/orders/2b455b7d-d3d2-4696-a9bd-6d046776edcf",
    "name": "James Smith requested Flex CUD",
    "accountIdentifier": "01E091-D83A6B-1F55DD",
    "memory": 0,
    "vcpus": 0,
    "duration": 0,
    "commitmentGroupDetails": {
    "reservationId": "01E091-D83A6B-1F55DD:spend:COMPUTE_ENGINE:all-regions",
    "commitmentCategory": "Spend",
    "region": "all-regions",
    "quantity": 3,
    "status": "Active",
    "nextExpirationDate": "2025-01-04",
    "netSavings": -13.279300,
    "realizedSavingsRate": -0.0991584521,
    "commitmentListDiscountRate": 0.290029,
    "hourlyCommitmentAmount": 0.180000,
    "totalCommitmentAmount": 133.920000,
    "hourlyCommitmentCost": 0.127795,
    "totalCommitmentCost": 95.079368,
    "scudGroupUtilization": 0.610836,
    "remainingCost": 503.310000,
    "accountIdentifier": "01E091-D83A6B-1F55DD",
    "unrealizedSavings": -13.279300,
    "nextExpiration": 0,
    "vcpus": 0,
    "memory": 0,
    "predefinedOnDemandPrice": 0.0,
    "customOnDemandPrice": 0.0,
    "commit1YrPrice": 0.0,
    "commit3YrPrice": 0.0,
    "orgId": 112844,
    "service": "COMPUTE_ENGINE",
    "billingAccountIdentifier": "01E091-D83A6B-1F55DD",
    "scuds": []
    },
     "orgId": 112844,
     "service": "COMPUTE_ENGINE",
     "reservationId": "2b455b7d-d3d2-4696-a9bd-6d046776edcf",
     "commitmentCategory": "Spend"
    },
	{
	 "commitmentGroupId": "staging-rightsizing:us-central1:GENERAL_PURPOSE_E2",
	 "billingAccountIdentifier": "staging-rightsizing",
	 "term": 1,
	 "region": "us-central1",
	 "quantity": 0,
	 "status": "ACTIVE",
	 "hourlyCommitmentAmount": 0.0,
	 "hourlyCommitmentCost": 0.0,
	 "totalCommitmentAmount": 0.0,
	 "totalCommitmentCost": 0.0,
	 "commitmentCostRemaining": 0.0,
	 "commitmentDiscountRate": 0.0,
	 "creation": "2024-06-18",
	 "start": "2024-06-19",
	 "end": "2025-06-19",
	 "expirationDate": "2025-06-19",
	 "offer": "0.0",
	 "description": "",
	 "name": "sean-e2-commitment",
	 "accountIdentifier": "staging-rightsizing",
	 "commitmentType": "GENERAL_PURPOSE_E2",
	 "memory": 2048,
	 "vcpus": 2,
	 "selfLink": "https://www.googleapis.com/compute/beta/projects/staging-rightsizing/regions/us-central1/commitments/sean-e2-commitment",
	 "statusMessage": "The commitment is active, and so will apply to current resource usage.",
	 "duration": 0,
	 "orgId": 112844,
	 "service": "COMPUTE_ENGINE",
	 "reservationId": "4034804980905703051",
	 "commitmentCategory": "Resource"
	},
	],
	"aggregate": {
	"quantity": 13,
	"unrealizedSavings": 0,
	"hourlyCommitment": 0.127795,
       "totalCommitment": 95.079368,
	"netSavings": 171.847206,
	"overallUtilization": 0.610836,
	"effectiveSavingsRate": 0.000000,
	"coverage": 0.007172,
	"remainingCommitmentCost": 503.310000,
	"rcudCoverageAmount": 964.089371,
	"scudCoverageAmount": 133.920001,
	"commitmentCoverageAmount": 1098.009372,
	"commitmentEligibleCoverageCost": 4456.955846,
	"relevantSpendCommitmentCoverageCost": 5554.965218,
	"rcudExclusiveEligibleCoverageCost": 6866.890625,
	"relevantAllCommitmentCoverageCost": 12421.855843,
	"costsUncoverableByCommitments": 4539.347407,
	"totalServiceODCost": 16961.203250,
	"sudCredit": -2038.881740
	},
	"pagination": {
	"totalCount": 2
	}


```

The commitment-groups endpoint has SCUDs or CUDs according to commitment category whereas commitment endpoint has commitmentGroupDetails against each commitment. But commitmentGroupDetails does not re-populate SCUDs or CUDs again for commitment endpoint.

The Google Cloud Platform(GCP) Commitment Groups Endpoint

The following api endpoint will provide a list of commitment groups and associated commitments in it.

The following curl will work with GET/ POST requests: GET with query parameters and POST with request body.

```
curl 'https://api.cloudability.com/v3/reservations/gcp/portfolio/commitment-groups' 
	 -H 'accept: application/json, text/plain, /' 
	 -H 'accept-language: en-US,en;q=0.9' 
	 -H 'authorization: Bearer [auth_token]' 
	 -H 'content-type: application/json' 
	 --data-raw '{"start":"2025-02-28","end":"2025-03-30","basis":"adjusted","filter":"commitment_category==spend","viewId":0,"limit":10,"offset":0,"sortOrder":"-netSavings","service":"scud-groups","services":"compute_engine"}'

```

The following table lists the valid payload options:

| Payload Options | Valid Format | Details |
| --- | --- | --- |
| start | Date in the format “YYYY-MM-DD" |  |
| end | Date in the format “YYYY-MM-DD" |  |
| basis | adjusted, cost |  |
| filter |  | Look how filters get formed in the developer toolbar. |
| sortOrder | A valid field e.g. billingAccountIdentifier for ALL, netsavings for other CUDs. |  |
| services | Comma separated string with values from compute_engine cloud_sql | Current supported services include “compute_engine” and “cloud_sql”. |

For SCUDs, RCUDs or ALL commitments to be returned via these endpoints, use the following in filters along with dates.

| Commitments | Filter Values | Details |
| --- | --- | --- |
| Flex CUDs Commitments | "commitment_category==spend" | When commitment category as spend is provided, the above endpoint should return Flex CUDs commitments only. |
| RCUDs Commitments | "commitment_category==resource" | When commitment category as resource is provided, the above endpoint should return Resource CUDs commitments only. |
| All Commitments | No filter added | When no commitment category is provided as filter, Flex CUDs and RCUDs are returned as response by merging the results of RCUD and SCUD commitments |
| Cloud SQL CUDs | "commitment_category==spend" | "commitment_category==spend" with services in payload should be “cloud_sql” |

The Google Cloud Platform(GCP) Commitment Groups Endpoint Object

- commitmentGroupId (string): The commitment group id for the group commitment belongs to.
- billingAccountIdentifier (string): Billing Account Identifier in which commitment belong to.
- term (integer): CUD term length in years.
- region (string): Text description of the CUD's assigned region e.g. 'us-central'.
- status (string): Current CUD status.
- hourlyCommitmentAmount (string): Hourly commitment amount.
- hourlyCommitmentCost (string): Hourly commitment cost that is being paid.
- totalCommitmentAmount (string): Hourly commitment cost that is being paid.
- totalCommitmentCost (string): Total commitment cost to be paid.
- commitmentCostRemaining (string): Commitment remaining cost.
- remainingCost (string): Remaining cost of the CUD to be paid.
- commitmentDiscountRate (string): Commitment discount rate percentage / 100.
- creation (string): The creation date of the CUD was requested
- start (string): The start date of when the CUD began applying to usage
- end (string): The CUD expiration date
- expirationDate (string): The CUD expiration date
- offer (string): CUD offer details if available.
- description (string): Description of the CUD.
- name (string): User assigned CUD name
- accountIdentifier (string): User assigned account ID
- memory (integer): MB of memory allocated (at 1024MB/GB)
- vcpus (integer): vCPUs allocated to the CUD
- duration (integer): Duration of the RI in seconds
- statusMessage (string): Long form status description and explanation
- type (string): Flex-CUD or CUD type of the CUD
- commitmentGroupDetails (object): Commitment group details object {}
- service : Service name CUD belongs to
- reservationId/ commitmentId (string): Unique identifier of the CUD.
- commitmentCategory (string): Commitment category, Spend or Resource.
- Example Google Cloud Platform(GCP) Commitment Groups Endpoint Object

This is an example response for Commitment Groups for Flex CUDs.

```
{
  {
   "result": [
	{
	 "reservationId": "01E091-D83A6B-1F55DD:spend:COMPUTE_ENGINE:all-regions",
	 "commitmentGroupId": "01E091-D83A6B-1F55DD:spend:COMPUTE_ENGINE:all-regions",
	 "commitmentCategory": "Spend",
	 "region": "all-regions",
	 "quantity": 3,
	 "status": "Active",
	 "nextExpirationDate": "2025-01-04",
	 "netSavings": 0.000000,
	 "commitmentListDiscountRate": 0.290000,
	 "hourlyCommitmentAmount": 0.180000,
	 "hourlyCommitmentCost": 0.127800,
	 "totalCommitmentAmount": 133.920000,
	 "totalCommitmentCost": 95.083200,
	 "totalLifeTimeCommitmentCost": 1214.136000,
	 "totalLifeTimeCommitmentAmount": 1752.000000,
	 "scudGroupUtilization": 0.000000,
	 "remainingCost": 261.010000,
	 "accountIdentifier": "n/a",
	 "unrealizedSavings": 0.000000,
	 "nextExpiration": 0,
	 "vcpus": 0,
	 "memory": 0,
	 "predefinedOnDemandPrice": 0.0,
	 "customOnDemandPrice": 0.0,
	 "commit1YrPrice": 0.0,
	 "commit3YrPrice": 0.0,
	 "scudsMinStartDate": "2024-01-04",
	 "orgId": 108194,
	 "service": "COMPUTE_ENGINE",
	 "billingAccountIdentifier": "01E091-D83A6B-1F55DD",
	 "scuds": [
	{
	 "commitmentGroupId": "01E091-D83A6B-1F55DD:spend:COMPUTE_ENGINE:all-regions",
	 "billingAccountIdentifier": "01E091-D83A6B-1F55DD",
	 "term": 1,
	 "region": "n/a",
	 "status": "Active",
	 "hourlyCommitmentAmount": 0.12,
	 "hourlyCommitmentCost": 0.0864,
	 "totalCommitmentAmount": 89.28,
	 "totalCommitmentCost": 64.2816,
	 "totalLifeTimeCommitmentCost": 756.864000,
	 "totalLifeTimeCommitmentAmount": 1051.200000,
	 "commitmentCostRemaining": 111.97,
	 "remainingCost": 111.97,
	 "commitmentDiscountRate": 0.28,
	 "creation": "2024-01-04",
	 "start": "2024-01-04",
	 "end": "2025-01-04",
	 "expirationDate": "2025-01-04",
	 "offer": "services/compute.googleapis.com/standardOffers/ffe0f6a3-2f98-437e-8d49-fc443a05d3c2",
	 "description": "billingAccounts/01E091-D83A6B-1F55DD/orders/2b455b7d-d3d2-4696-a9bd-6d046776edcf",
	 "name": "James Smith requested Flex CUD",
	 "accountIdentifier": "n/a",
	 "memory": 0,
	 "vcpus": 0,
	 "duration": 0,
	 "type": "Compute Flex-CUD",
	 "orgId": 108194,
	 "service": "COMPUTE_ENGINE",
	 "reservationId": "2b455b7d-d3d2-4696-a9bd-6d046776edcf",
	 "commitmentCategory": "Spend"
	},
	{
	 "commitmentGroupId": "01E091-D83A6B-1F55DD:spend:COMPUTE_ENGINE:all-regions",
	 "billingAccountIdentifier": "01E091-D83A6B-1F55DD",
	 "term": 1,
	 "region": "n/a",
	 "status": "Active",
	 "hourlyCommitmentAmount": 0.05,
	 "hourlyCommitmentCost": 0.036,
	 "totalCommitmentAmount": 37.2,
	 "totalCommitmentCost": 26.784,
	 "totalLifeTimeCommitmentCost": 315.360000,
	 "totalLifeTimeCommitmentAmount": 438.000000,
	 "commitmentCostRemaining": 46.66,
	 "remainingCost": 46.66,
	 "commitmentDiscountRate": 0.28,
	 "creation": "2024-01-04",
	 "start": "2024-01-04",
	 "end": "2025-01-04",
	 "expirationDate": "2025-01-04",
	 "offer": "services/compute.googleapis.com/standardOffers/ffe0f6a3-2f98-437e-8d49-fc443a05d3c2",
	 "description": "billingAccounts/01E091-D83A6B-1F55DD/orders/e3e36abf-36c6-4ebf-adb1-295e570f09da",
	 "name": "James Smith requested Flex CUD",
	 "accountIdentifier": "n/a",
	 "memory": 0,
	 "vcpus": 0,
	 "duration": 0,
	 "type": "Compute Flex-CUD",
	 "orgId": 108194,
	 "service": "COMPUTE_ENGINE",
	 "reservationId": "e3e36abf-36c6-4ebf-adb1-295e570f09da",
	 "commitmentCategory": "Spend"
	},
	{
	 "commitmentGroupId": "01E091-D83A6B-1F55DD:spend:COMPUTE_ENGINE:all-regions",
	 "billingAccountIdentifier": "01E091-D83A6B-1F55DD",
	 "term": 3,
	 "region": "n/a",
	 "status": "Active",
	 "hourlyCommitmentAmount": 0.01,
	 "hourlyCommitmentCost": 0.0054,
	 "totalCommitmentAmount": 7.44,
	 "totalCommitmentCost": 4.0176,
	 "totalLifeTimeCommitmentCost": 141.912000,
	 "totalLifeTimeCommitmentAmount": 262.800000,
	 "commitmentCostRemaining": 102.38,
	 "remainingCost": 102.38,
	 "commitmentDiscountRate": 0.46,
	 "creation": "2024-01-10",
	 "start": "2024-01-10",
	 "end": "2027-01-10",
	 "expirationDate": "2027-01-10",
	 "offer": "services/compute.googleapis.com/standardOffers/062a285d-8989-4ce7-8f9a-bed8d183236f",
	 "description": "billingAccounts/01E091-D83A6B-1F55DD/orders/fda5efd3-ca2e-4c79-9dfd-2d16f1746bbe",
	 "name": "Blake Corum 3 year commitment",
	 "accountIdentifier": "n/a",
	 "memory": 0,
	 "vcpus": 0,
	 "duration": 0,
	 "type": "Compute Flex-CUD",
	 "orgId": 108194,
	 "service": "COMPUTE_ENGINE",
	 "reservationId": "fda5efd3-ca2e-4c79-9dfd-2d16f1746bbe",
	 "commitmentCategory": "Spend"
      }
      ]
      }
      ],
	 "aggregate": {
        "quantity": 3,
	 "unrealizedSavings": 0.000000,
	 "netSavings": 0.000000,
	 "overallUtilization": 0.000000,
	 "effectiveSavingsRate": 0.000000,
	 "coverage": 0.000000,
	 "remainingCommitmentCost": 261.010000,
	 "totalRemainingCost": 261.010000,
	 "rcudCoverageAmount": 0.000000,
	 "scudCoverageAmount": 0.000000,
	 "spendCoveredResourceEligibleCost": 98.234687,
	 "resourceCoveredSpendEligibleCost": 166.385452,
	 "totalCoveredAmount": 0.000000,
	 "spendTotalCoveredAmount": 166.385452,
	 "resourceTotalCoveredAmount": 98.234687,
	 "spendCommitmentEligibleCoverageCost": 1199.875958,
	 "resourceCommitmentEligibleCoverageCost": 2769.947700,
	 "relevantResourceCommitmentCoverageCost": 2868.182387,
	 "relevantSpendCommitmentCoverageCost": 1366.261410,
	 "rcudExclusiveEligibleCoverageCost": 1573.353773,
	 "scudExclusiveEligibleCoverageCost": 3.282031,
	 "relevantAllCommitmentCoverageCost": 2773.229731,
	 "costsUncoverableByCommitments": 1185.002169,
	 "totalServiceODCost": 3958.231900,
	 "sudCredit": -634.953422,
	 "commitmentEligibleCoverageCost": 2773.229731,
	 "nonExclusiveEligibleCost": 1196.593927
	}
	 "pagination": {
	 "totalCount": 1
	}
       }


```

The commitment-groups endpoint has SCUDs or CUDs according to commitment category whereas commitment endpoint has commitmentGroupDetails against each commitment. But commitmentGroupDetails does not re-populate SCUDs or CUDs again for commitment endpoint.

The Azure Reserved Instance Object

- vendorAccountId (string): Vendor assigned unique alphanumeric subscription identifier
- reservationId (string): Vendor assigned unique alphanumeric reservation identifier
- AccountName (string): User assigned subscription name
- size (string): On demand instance family covered by the reservation(e.g.'DS1_v2')
- tier (string): On demand instance tier covered by the reservation (e.g.'Standard')
- term (integer): Reservation term length in years
- quantity (integer): Number of instances covered by the reservation
- region (string): Text description of the reservation's assigned region e.g. 'westus2'
- state (string): Current reservation status
- start (number): The Epoch millisecond formatted time stamp of when the CUD began applying to usage
- end (number): The Epoch millisecond formatted CUD expiration time stamp
- currencyCode (string): The currency reporting type for the reservation
- upfront (integer): The up front reservation purchase price in the applicable currency

Example Azure Reservation Object

```
{
  "result": [
    {
      "vendorAccountId": "2####252-2##4-4##e-9##7-b95#########",
      "reservationId": "45####04-3X#2-4##7-b##6-35c##XX###X#",
      "accountName": "AZU Staging US",
      "size": "DS1_v2",
      "tier": "Standard",
      "term": 1,
      "quantity": 3,
      "region": "westus2",
      "state": "Cancelled",
      "start": 1560211200000,
      "end": 1560729600000,
      "pricing": {
        "currencyCode": "USD",
        "upfront": 810
      }
    },
    {
      "vendorAccountId": "c####d37-eecc-##d6-###b-######da36a6",
      "reservationId": "XX6d##d7-b034-4XX8-a8a0-3bcc###a####",
      "accountName": "Azure Prod",
      "size": "B1s",
      "tier": "Standard",
      "term": 1,
      "quantity": 1,
      "region": "westus2",
      "state": "Succeeded",
      "start": 1557446400000,
      "end": 1588896000000,
      "pricing": {
        "currencyCode": "USD",
        "upfront": 53
      }
    },
    {
      "vendorAccountId": "26e#####-2##4-434e-####-b95f#####fd#",
      "reservationId": "3d####f7-0X##-40b0-b###-82bd######a#",
      "accountName": "AZU Staging US",
      "size": "DS1_v2",
      "tier": "Standard",
      "term": 1,
      "quantity": 2,
      "region": "westus2",
      "state": "Succeeded",
      "start": 1560729600000,
      "end": 1591747200000,
      "pricing": {
        "currencyCode": "USD",
        "upfront": 540
      }
    },
  "meta": {
    "aggregate": {
      "quantity": 6
    },
    "pagination": {
      "totalCount": 3
    }
  }
}
```

Example Azure Reservation Portfolio Request

The following will generate a list of Azure Reserved Instances

```
curl "https://api.cloudability.com/v3/reservations/azure/portfolio/compute" \\
     -u ‘[auth_token]:’
```
