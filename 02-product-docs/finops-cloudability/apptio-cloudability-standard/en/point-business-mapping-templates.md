---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Business Mapping Templates"
breadcrumb:
  - "Cloudability API"
  - "Business Mappings End Point"
  - "Business Mapping Templates"
source_path: "SSVCLNQ/api-v3/business_mapping_templates.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Business Mapping Templates

Business Mapping Dimensions

Sample Mapping of a Business Dimension for Compliance

There are a number of attributes of a cloud spend item that you could use to describe it as a compliant or not. For example is it of a compliant instance type, have the right tags applied or exit in a compliant region? Here is an example for region compliance.

```
  {
    "name": "Region Compliance",
    "defaultValue": "Non Compliant",
    "statements": [
      {
        "matchExpression": "!EXISTS DIMENSION['region']",
        "valueExpression": "'Not Applicable'"
      },
      {
        "matchExpression": "DIMENSION['region'] == 'ap-southeast-2'",
        "valueExpression": "'Compliant'"
      },
      {
        "matchExpression": "DIMENSION['region'] == 'us-west-2'",
        "valueExpression": "'Compliant'"
      },
      {
        "matchExpression": "DIMENSION['region'] == 'eu-west-1'",
        "valueExpression": "'Compliant'"
      }
    ]
 }
```

Sample Mapping of a Business Dimension for Chargeback - Canonical List of Tag Values

Many organizations will use an ITSM tool such as Service Now to keep a catalog of official chargeback/application codes. We can utilize these within mappings to create logical groupings. Note below that we explicitly categorize costs which are tagged but aren't a member of the canonical list.

```
{
  "name": "Business Application",
  "defaultValue": "Untagged",
  "statements": [
    {
      "matchExpression": "TAG['Movie'] == 'Coco' || TAG['Movie'] == 'Brave' || TAG['Movie'] == 'A Bugs Life'",
      "valueExpression": "'Pixar Original'"
    },
    {
      "matchExpression": "TAG['Movie'] CONTAINS 'Toy Story' || TAG['Movie'] CONTAINS 'The Incredibles'",
      "valueExpression": "'Pixar Series'"
    },
    {
      "matchExpression": "TAG['Movie'] == 'Shrek' || TAG['Movie'] == 'Kung Fu Panda'",
      "valueExpression": "'Dreamworks'"
    },
    {
      "matchExpression": "EXISTS TAG['Movie']",
      "valueExpression": "'Non Canonical Value'"
    }
  ]
}
```

Sample Mapping of a Business Dimension for Chargeback - Use Tag Value if Exists, Fall Back to Account

We see a number of our customers take this approach. The goal, as always, is to have every dollar spent allocated. Tagging will be the primary mechanism for allocation, but 'account owners' will be responsible for items that fall between the cracks. Note below how we explicitly default to 'Unallocated' for items that aren't picked up by the statements. These items could then be addressed with further statements focused on account ownership, a different tag or a completely different billing attribute.

```
{
  "name": "Business Unit",
  "defaultValue": "Unallocated",
  "statements": [
    {
      "matchExpression": "EXISTS TAG['Business']",
      "valueExpression": "TAG['Business']"
    },
    {
      "matchExpression": "DIMENSION['vendor_account_identifier'] == '123456789012'",
      "valueExpression": "'Business Unit A'"
    },
    {
      "matchExpression": "DIMENSION['vendor_account_identifier'] == '888844442222'",
      "valueExpression": "'Business Unit B'"
    },
    {
      "matchExpression": "DIMENSION['vendor_account_identifier'] == '666633331111'",
      "valueExpression": "'Business Unit C'"
    }
  ]
}
```

Business Mapping Metrics

Sample Mapping of a Business Metric to Contextualize Spend in Unit Economic Terms

Users have reporting questions that are specific to their business when understanding Cloud costs. Being able to contextualize Cloud spending against business specific KPIs (like "cost per X") to visualize trends will enable stakeholders to make decisions based on data that is meaningful to the business. For example, understanding your Cloud spend as a cost per million daily active users.

```
{
    "name": "Cost (Per Million DAU)",
    "numberFormat": "currency",
    "preMatchExpression": "",
    "defaultValueExpression": "",
    "statements": [
        {
            "matchExpression": "DIMENSION['date'] == '2019-01-01'",
            "valueExpression": "METRIC['unblended_cost'] / 68989980 * 1000000"
        },
        {
            "matchExpression": "DIMENSION['date'] == '2019-01-02'",
            "valueExpression": "METRIC['unblended_cost'] / 70901268 * 1000000"
        },
        {
            "matchExpression": "DIMENSION['date'] == '2019-01-03'",
            "valueExpression": "METRIC['unblended_cost'] / 68336154 * 1000000"
        }
    ]
}
```

Sample Mapping of a Business Metric to Build in a Surcharge

Build in and surface costs inclusive of management fees, provided services, licensing fees or any other costs incurred - captured in a single in-app metric.

For example: create a surcharge (markup / upcharge) for all storage backups managed on behalf of external and/or internal customers.

```
{
 "name": "Cost (Storage Backup 10% Surcharge)",
 "kind": "BUSINESS_METRIC",
 "numberFormat": "currency",
 "preMatchExpression": "(DIMENSION['vendor'] == 'amazon' && DIMENSION['usage_family'] == 'storage'",
 "defaultValueExpression": "METRIC['unblended_cost']",
 "statements": [{
   "matchExpression": "DIMENSION['invoice_date'] == '2019-09-01' && DIMENSION['transaction_type'] == 'usage' && DIMENSION['usage_type'] CONTAINS 'snapshot'",
   "valueExpression": "METRIC['unblended_cost'] * 1.10"
  },
  {
   "matchExpression": "DIMENSION['invoice_date'] == '2019-10-01' && DIMENSION['transaction_type'] == 'usage' && DIMENSION['usage_type'] CONTAINS 'snapshot'",
   "valueExpression": "METRIC['unblended_cost'] * 1.10"
  },
  {
   "matchExpression": "DIMENSION['invoice_date'] == '2019-11-01'  && DIMENSION['transaction_type'] == 'usage' && DIMENSION['usage_type'] CONTAINS 'snapshot'",
   "valueExpression": "METRIC['unblended_cost'] * 1.10"
  }]
}
```
