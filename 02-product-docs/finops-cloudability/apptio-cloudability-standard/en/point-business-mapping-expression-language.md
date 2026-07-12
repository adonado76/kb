---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Business Mapping Expression Language"
breadcrumb:
  - "Cloudability API"
  - "Business Mappings End Point"
  - "Business Mapping Expression Language"
source_path: "SSVCLNQ/api-v3/business_mapping_expression.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Business Mapping Expression Language

Summary

We have created a DSL especially so that you can to define the matchExpression and valueExpression fields in your mapping rules elegantly, and the syntax is pretty simple. If you’ve ever written code in Java, JavaScript, Ruby, Python, or any other popular programming language, the concepts of our expression language should be pretty familiar. Even if you haven't it's very straightforward to create these expressions and Cloudability will provide plenty of examples.

Literals: Text, Date-times Objects, and Numbers

The expression language has three different types of literal data: text, date-time objects, and numbers. Although you can use either single-quotes or double quotes to express literal text objects (with backslashes to escape literal quotes or apostrophes embedded within the string) it's advisable to use single quotes since it will be awkward to use double-quoted expression strings within double-quoted JSON strings.

```
'This is also text.'
'This text has \\'embedded apostrophes\\'.'
'This text has "embedded quotes", but is wrapped in apostrophes.'
```

To create date-time objects, just create a string literal whose contents conform with a well-known date format, either YYYY-MM-DD , to specify the date only (with the time set to midnight UTC), or YYYY-MM-DDTHH:MM:SS.000Z , to specify the complete date-time.

You can omit the final “Z” character -- as well as the millisecond fractions and the decimal point, from the complete date-time object -- but the timestamp will always be interpreted with UTC timezone.

```
'2018-01-01'
'2017-04-10T10:10:10'
'2017-04-10T10:10:10.123Z'
```

For numbers, you can use numerals, minus signs, decimal points, and exponential notation

```
1
3.14159
-2.5
6.02e+23
0.05e-23
```

Field Lookups

Field lookups let you define an expression based on any attribute within the line item data-point: including all dimensions, metrics, account groups, tags, and business dimensions. Field lookups are written by declaring the slot kind in all caps, and then using square-brackets enclosing a string with the name of the appropriate key. It will feel similar to retrieving a value from a hash in many programming languages. Go to the bottom of this page for a full list of available dimensions and metrics.

Note key names are not case-sensitive, so you can write them in uppercase or lowercase, like this:

```
DIMENSION['account_identifier']
METRIC['adjusted_cost']
ACCOUNT_GROUP['Environment']
TAG['NAME']
BUSINESS_DIMENSION['Business Unit']
BUSINESS_METRIC['Cost (Storage Backup 10% Surcharge)']
```

When you lookup METRIC or BUSINESS_METRIC values, the result will always be numeric, but most other kinds of field-lookup (dimensions, account groups, tags, and business dimensions) will generally produce text results.

The only exception is the DIMENSION['date'] expression which will always produce a date-time result.

Operators

Existence Operator

When writing an expression that uses these field lookups, the most basic logical test we can perform is the test of existence. The EXISTS operator checks that a text-field with a particular key exists, and has a non-empty value. For example, consider an expression like this:

```
EXISTS TAG['business unit']
```

We can use this expression to test whether a tag named “business unit” exists on this data point. If so, then the expression successfully matches. Likewise, we can use the negated EXISTS operator to match on data-points with no such value:

```
!EXISTS TAG['business unit']
```

Text Operators

These operators allow you to match the text in dimensions, account groups, tags, and business dimensions. You can compare these field-lookup text values with one another, or with literal string values in the expression. Text comparisons are always done in a case-insensitive manner (where the two strings “ABC” vs “abc” are considered equal to one another)

You can check any text for equality using the equality operator (==), or conversely, you can use the inequality operator (!=), to match text that’s not equal, like this:

```
DIMENSION['vendor_account_identifier'] == '123456789012'
DIMENSION['vendor_account_identifier'] != '123456789012'
```

While it’s obvious that you can compare the text in a dimension value to the text in a literal string, you can actually also compare two dimension values to each other, like this:

```
DIMENSION['vendor_account_identifier'] == DIMENSION['account_identifier']
```

You can perform partial text matching, using the three self-explanatory operators STARTS_WITH , ENDS_WITH , and CONTAINS , like this:

```
DIMENSION['item_description'] CONTAINS '-maps-'
DIMENSION['region'] STARTS_WITH 'us-'
DIMENSION['compute_usage_type'] ENDS_WITH 'xlarge'
```

You can also take the logical opposite of any of these operators by including the NOT operator (!) immediately before the operator name, like this:

```
DIMENSION['item_description'] !CONTAINS '-maps-'
DIMENSION['region'] !STARTS_WITH 'us-'
DIMENSION['compute_usage_type'] !ENDS_WITH 'xlarge'
```

You can perform letter case conversion using the operators LOWER and UPPER .

To convert letters to lower case:

```
{

  "matchExpression" : "EXISTS TAG['cost category']",

  "valueExpression" : "LOWER(TAG['cost category'])"

}
```

To convert letters to upper case:

```
{

  "matchExpression" : "EXISTS TAG['cost category']",

  "valueExpression" : "UPPER(TAG['cost category'])"
}
```

You can use the IN operator to match a text value against a comma-delimited list of candidate values, like this:

```
DIMENSION['region'] IN ('us-east-1', 'us-west-1', 'eu-west-1')
'abc-123' IN (TAG['product-code'], BUSINESS_DIMENSION['service-code'])
```

Regular Expression Operators

We provide the FIND operator for use with matchExpressions to match a given text value against a Regular Expression pattern, like this:

```
TAG['created_by'] FIND /[a-z]+@example.com/
```

Regular Expression patterns are always contained within a pair of forward-slash characters (/) and the syntax of the expression conforms with the Pattern syntax, as implemented in the Java Standard Library.

It’s important to note that, since these Regular Expression patterns are always contained within JSON strings, any backslash-escape sequences need to use double-backslashes, like this:

```
TAG['two_words separated_by_whitespace'] FIND /\\w+\\s+\\w+/
```

The FIND operator searches for any instances of the designated Regular Expression within the target string, even if it doesn’t match the entire string. To match the entire string, be sure to include the boundary markers for start of text (^) and end-of-text ($), like this:

```
'abc-xyz' FIND /^[a-z]{3}-[a-z]{3}$/
```

It’s worth reiterating here that all text-comparisons in the expression language are case-insensitive, so we compile all regular expressions in a case-insensitive manner as well.

The FIND operator above purely tests for truth in matchExpressions. We also provide a special operator for valueExpressions to capture string elements described below.

We provide the REPLACE operator for use with valueExpressions such that text elements can be captured using regular expressions and surfaced for your business dimension. The format is very similar to that used with the FIND operator with the notable addition of an extra forward slash character (/). We use standard notation for regex captures such as using closed parenthesis to capture the groups and $1, $2... to reference them. The REPLACE operator is particularly handy where you have multiple concepts delimited within a dimension - often tags - and you want a clean way to extract individual concepts. Let's say we have a tag for ownership which looks something like "TeamAlpha:DepartmentBeta:BusinessCharlie" we could extract and surface the team with the following expression:

```
TAG['ownership'] REPLACE /^(\\w+):.*/$1/
```

The above expression would yield "teamalpha".

REPLACE can support more sophisticated requirements. For example we can handle surfacing multiple captures and join them with regular text. The following expression:

```
TAG['ownership'] REPLACE /^(.+):.+:(.+)/team-$1-business-$2/
```

would yield the value "team-teamalpha-business-businesscharlie"

Join Operator

You can join any two strings of text using the text-combining operator (~), like this:

```
TAG['primary_code'] ~ '-' ~ TAG['secondary_code']
```

In the example above we are joining the strings with '-' placed between them, but you can combine however you like. The text-combining operator is most useful in a valueExpression expression (rather than in the matchExpression), as a way of extracting values from dimensions and tags, to build composite text values assembled from those other bits and pieces.

Numeric and Date-time Operators

Since this expression language allows you to write rules based on METRIC values, which are numeric rather than textual, you’ll need a set of operators for comparing and manipulating numbers.

The set of comparison operators includes: equality (==), inequality (!=), greater-than (>), greater-than-or-equal (>=), less-than (<), and less-than-or-equal (<=). The set of arithmetic operators includes: addition (+), subtraction (-), multiplication (*), division (/), and exponentiation (^).

These examples show how you can create expressions that compare metric values using numeric operators:

```
METRIC['cost_adjusted'] == 0.0
METRIC['on_demand_hours'] != 0.0
METRIC['adjusted_cost'] <= METRIC['Cost']
METRIC['usage_quantity'] >= 100
METRIC['reserved_hours'] >= METRIC['on_demand_hours']
```

These same operators can also be applied to date-time objects, including date-time DIMENSION values, like this:

```
DIMENSION['date'] < '2018-01-01'
DIMENSION['date'] >= '2017-04-10T10:10:10'
DIMENSION['date'] == '2017-10-31T00:00:00.000Z'
```

Logical Operators and Parentheses

Finally, within any matchExpression, you can use logical operators like AND (&&), OR (||), and NOT (!) to apply Boolean logic to your sub-expressions, like this:

```
DIMENSION['region'] == 'us-east-1' && TAG['Environment'] != 'staging'
```

By default, these Boolean expressions follow the same order-of-operations as standard programming languages (like Java or Python), and also like those languages, you can wrap sub-expressions in parentheses to clarify or override the default logical ordering:

```
!(

  DIMENSION['compute_usage_type'] !STARTS_WITH 'm'

  &&
  (

	TAG['Environment'] == 'production'

	||

	TAG['Environment'] == 'staging'

  )
)
&&
EXISTS BUSINESS_DIMENSION['Business Unit']
```
