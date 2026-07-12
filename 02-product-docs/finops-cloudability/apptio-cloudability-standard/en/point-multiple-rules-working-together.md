---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Multiple Rules Working Together"
breadcrumb:
  - "Cloudability API"
  - "Business Mappings End Point"
  - "Multiple Rules Working Together"
source_path: "SSVCLNQ/api-v3/multiple_rules_working_together.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Multiple Rules Working Together

Most organization will have multiple Business Mappings, working together as a set. You can even have some Business Mappings that depend upon the output (the resultant Business Dimension or Business Metric) of other Business Mappings.

The Mapping Rule engine knows how to solve the hierarchy of dependencies between those rules, validating that the entire set of rules for any given organization actually make sense together, without stepping on one another’s toes, and rejecting any new Tag Rules that violate those constraints.

Unique Names

For example, it doesn’t make sense to have two different rules with the same name and the API will return a 400 error if you attempt this.

Preventing Cyclic Dependencies

The Mapping Rule engine allows some rules to depend on the output of other rules, and it automatically figures out how to evaluate rules in the correct order, so that you don’t need to worry about it.

Examples

In the Business Dimension example below, the rule for mapping ABC depends on the value of BUSINESS_DIMENSION['XYZ'] , which depends on TAG['AppServiceId'] .

```
[
  {
    "name": "ABC",
    "index": 1,
    "defaultValue": "Unallocated",
    "statements": [
      {
        "matchExpression": "EXISTS BUSINESS_DIMENSION['XYZ']",
        "valueExpression": "BUSINESS_DIMENSION['XYZ']"
      }
    ]
  },
  {
    "name": "XYZ",
    "index": 2,
    "defaultValue": "Unallocated",
    "statements": [
      {
        "matchExpression": "EXISTS TAG['AppServiceId']",
        "valueExpression": "TAG['AppServiceId']"
      }
    ]
  }
]
```

The Mapping Rule engine is smart enough to know that it needs to lookup the TAG['AppServiceId'] value first, and then use that value to calculate BUSINESS_DIMENSION['XYZ'] , and finally to use that value to calculate BUSINESS_DIMENSION['ABC'] . You don’t have to do anything special to force the correct ordering. The Mapping Rule engine does it for you.

But if you define rules whose dependency chain creates an infinite loop, then the engine will reject those rules when you attempt to create them. The next example illustrates this point:

```
[
  {
    "name": "ABC",
    "index": 1,
    "defaultValue": "Unallocated",
    "statements": [
      {
        "match": "EXISTS BUSINESS_DIMENSION['XYZ']",
        "name": "BUSINESS_DIMENSION['XYZ']"
      }
    ]
  },
  {
    "name": "XYZ",
    "index": 2,
    "defaultValue": "Unallocated",
    "statements": [
      {
        "matchExpression": "EXISTS BUSINESS_DIMENSION['ABC']",
        "valueExpression": "BUSINESS_DIMENSION[ABC]"
      }
    ]
  }
]
```

In this example, we’ve created a rule that calculates BUSINESS_DIMENSION['ABC'] based upon the value of BUSINESS_DIMENSION['XYZ'] . But the other rule, which calculates BUSINESS_DIMENSION['XYZ'] depends upon the value of BUSINESS_DIMENSION['ABC'] .

On their own, each of these rules looks valid, but when we try to combine them into a cohesive rule-set, they create an infinite dependency loop upon one another, and the Mapping Rule engine will reject them.

Similar to the above example, in the context of Business Metrics, the example below highlights how you can use the output value from one Business Metric as input to a new custom metric.

```
{
	"name": "Cost (Per XYZ)",
	"numberFormat": "currency",
	"preMatchExpression": "",
	"defaultValueExpression": "METRIC['unblended_cost']",
	"statements": [{
			"matchExpression": "DIMENSION['date'] == '2019-01-01'",
			"valueExpression": "METRIC['unblended_cost'] / 34989890"
		},
		{
			"matchExpression": "DIMENSION['date'] == '2019-01-02'",
			"valueExpression": "METRIC['unblended_cost'] / 35901234"
		},
		{
			"matchExpression": "DIMENSION['date'] == '2019-01-03'",
			"valueExpression": "METRIC['unblended_cost'] / 34336077"
		}
	]
}
```

In this unit economics use case example, we are starting out by calculating the "cost per XYZ" where this could be cost per number of active users, or cost per ride share, cost per subscription, etc ...

We can then take those results and further contextualize our Cloud spend by surfacing the "cost per XYZ" in terms of FTEs (full time engineers). For example:

```
{
	"name": "Cost in FTEs (Per XYZ)",
	"numberFormat": "number",
	"preMatchExpression": "",
	"defaultValueExpression": "METRIC['unblended_cost']",
	"statements": [{
			"matchExpression": "DIMENSION['date'] == '2019-01-01'",
			"valueExpression": "BUSINESS_METRIC['Cost (Per XYZ)'] / 120000"
		},
		{
			"matchExpression": "DIMENSION['date'] == '2019-01-02'",
			"valueExpression": "BUSINESS_METRIC['Cost (Per XYZ)'] / 120000"
		},
		{
			"matchExpression": "DIMENSION['date'] == '2019-01-03'",
			"valueExpression": "BUSINESS_METRIC['Cost (Per XYZ)'] / 120000"
		}
	]
}
```
