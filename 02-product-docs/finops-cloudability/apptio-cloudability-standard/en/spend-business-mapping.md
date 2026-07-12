---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Business mapping"
breadcrumb:
  - "Setup"
  - "Organize Your Cloud Spend"
  - "Business mapping"
source_path: "SSVCLNQ/admin/business-tags.html"
images:
  - "03-media/apptio-cloudability-standard/business-mapping-rule-structure.png"
  - "03-media/apptio-cloudability-standard/business-mapping-listview.png"
  - "03-media/apptio-cloudability-standard/business-mapping-addnew.png"
  - "03-media/apptio-cloudability-standard/business-mapping-addstmt.png"
  - "03-media/apptio-cloudability-standard/export_import_bm.png"
  - "03-media/apptio-cloudability-standard/business-mapping-edit.png"
  - "03-media/apptio-cloudability-standard/tagging-flow.png"
  - "03-media/apptio-cloudability-standard/business_mapping_mceclip3.jpg"
  - "03-media/apptio-cloudability-standard/business_mappingmceclip4.jpg"
  - "03-media/apptio-cloudability-standard/business_mappingmceclip6.jpg"
  - "03-media/apptio-cloudability-standard/execution-flow.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Business mapping

## What are Business Mappings?

Business Mappings are used to create Business Dimensions that categorize cloud spending according to your organization’s taxonomy.

Unlike vendor-provided or billing-based dimensions, Business Dimensions offer greater flexibility and control. They use evaluation rules—called Business Mapping statements —to translate vendor- and billing-specific metadata into meaningful business concepts. Business concepts are the categories and structures an organization uses to interpret raw data and turn it into information suitable for reporting and decision-making.

The Business Mapping rules engine supports complex logic and can evaluate a wide range of attributes from both billing and usage data. These include vendor-supplied fields such as tags, account names, regions, and service names. Cloudability further extends this capability by offering enhanced attributes like usage family and lease type , enabling more granular and insightful categorization.

The maximum number of Statements for one Business Dimension is 300 000.

The maximum number of Statements across all Business Dimensions is 500 000.

## How do Business Mappings work?

Evaulated at Ingestion

When billing data is ingested, Cloudability evaluates each cost line item against your Business Mapping rules. You can think of these rules as similar to a case statement—when a match is found, the associated statement name is used as the value for the Business Dimension.

This value can be:

- A static label you define (e.g., Marketing, Non-Compliant), or
- A dynamic attribute (e.g., a tag value from the item itself).

Once a rule matches, processing stops, and no further rules are evaluated. If no rule matches, the default value is assigned.

Automatic Updates

Each time your cloud provider delivers a new billing dataset, Cloudability re-applies the current set of Business Mapping statements.

Tips for Creating Business Dimensions

Choose a Clear Name

Each Business Dimension requires a name. Choose a name that clearly conveys its purpose, as it will appear in reports and throughout Cloudability.

Set a Default Value

Provide a fallback value, which is assigned when no rules match. Common defaults include Unallocated, Unknown, Non-Compliant, or Not Set .

Understand Rule Structure

Each Business Mapping statement consists of:

1. Name – The value assigned to the Business Dimension when a match occurs. This can be a static value or dynamically populated from a cost item attribute (e.g., a tag).
1. Match Expression – A condition that evaluates cost item attributes. These expressions can use complex Boolean logic, a comprehensive set of operators, and any relevant cost item attributes.

Note: Changes to Business Mapping statements are automatically applied to billing data for the current month. To apply updates to historical data, submit a reprocessing request or contact Cloudability support or your TAM for assistance.

The diagram can help understand the concepts standing behind Business Mapping structure:

1. Business Mapping (Top Level)

- The overall cost allocation framework
- Contains multiple dimensions

2. Dimensions (Categories)

- Business organizational units
- Examples: Department, Cost Center, Project, Environment
- Each dimension contains multiple rules

3. Rules (Mapping Logic)

- Define how resources are assigned to categories
- Each rule contains one or more statements
- Rules have priority order

4. Statements (Conditions)

- Individual logical conditions
- Check specific cloud metadata
- Multiple statements combine with AND/OR logic

```

Business Mapping: "Cost Allocation Framework"
│
├── Dimension: "Department"
│   │
│   ├── Rule 1 (Priority 1): "Engineering Resources"
│   │   ├── Statement 1: tag:Department EQUALS "Engineering"
│   │   └── Statement 2: tag:Environment EQUALS "Production"
│   │   → Result: Assign to "Engineering"
│   │
│   ├── Rule 2 (Priority 2): "Marketing Resources"
│   │   └── Statement 1: account_id EQUALS "123456789"
│   │   → Result: Assign to "Marketing"
│   │
│   └── Rule 3 (Priority 3): "Default"
│       └── Statement 1: tag:Department IS EMPTY
│       → Result: Assign to "Unallocated"
│
└── Dimension: "Environment"
    │
    ├── Rule 1: "Production"
    │   └── Statement 1: tag:Environment EQUALS "Production"
    │   → Result: Assign to "Production"
    │
    └── Rule 2: "Non-Production"
        ├── Statement 1: tag:Environment EQUALS "Development"
        └── Statement 2: tag:Environment EQUALS "Testing"
        → Result: Assign to "Non-Production"

```

## Working with Business Mappings

Listing and reviewing business dimensions

From the Business Mappings home page, you can see a list of all the business dimensions you have set up and there are a variety of actions you can take. You can set up a maximum of 10 business dimensions.

Creating new business dimensions

1. On the Business Mapping page, select New Business Dimension from the Add menu.
1. In the Add a Business Mapping window, put the dimension name and the default value > Select Add a Business Mapping .
1. On the Business Mapping page, select the Settings (gear) icon next to the newly created dimension > Select Edit Business Mapping.
1. Click Add a statement .
1. Give the statement a name > Select Account ID as the Dimension and Operator as equals . Choose a value from the Select Value drop down > Click Save .
1. You can also populate Business Dimension using Import/Export functionality. Simply attach JSON file with defined Business Dimension object structure described here Business Mappings Endpoint

Editing or creating a business dimension

Most of your interactions on this page will be with managing business metric statements for your business dimensions. That is adding, editing, or deleting statements that form the backbone of any mapping. We’ll cover the key elements of any statement in the following sections.

When a Business Mapping has a reference to another mapping, updating the referenced dimension will also update the Last Updated field of the dependent dimension. For example, if Business Mapping B references Business Mapping A, any update made to Mapping A will automatically update the Last Updated timestamp for both Business Mapping A and Business Mapping B.

Options for the Name

As mentioned earlier, the name you supply when crafting any statement will become the value for the Business Dimension if the match component returns true. You have two options for the name itself. You could just enter a static string.

You can also create a Dynamic Dimension Name by selecting the Pencil icon next to the name.

Then, you'll receive a list of dimensions to choose from which includes tags and many other familiar items. The point of this capability is that on a match, the Business Dimension can take the value of any attribute of the cost item itself. A good example of how to use this dynamic aspect would be something like If Tag A exists, then the Business Dimension should assume Tag A's value . The next statement would then likely involve what to do given Tag A doesn't exist.

What It Means

Instead of assigning a fixed value to a Business Dimension, you can assign the actual value from a tag or attribute of the resource itself. This makes mappings flexible and scalable.

Static Assignment (Fixed Value):

```
IF tag:Department EQUALS "Engineering"
THEN Department = "Engineering"  ← Fixed value

```

Dynamic Assignment (Use Tag's Value):

```
IF tag:Department IS NOT EMPTY
THEN Department = [value of tag:Department]  ← Dynamic value

```

Complete Example: Department Mapping

Let's say you have resources with different department tags:

- Resource 1: tag:Department = "Engineering"
- Resource 2: tag:Department = "Marketing"
- Resource 3: tag:Department = "Sales"
- Resource 4: No Department tag

Traditional Approach (Multiple Static Rules):

```
Rule 1:
  IF tag:Department EQUALS "Engineering"
  THEN Department = "Engineering"

Rule 2:
  IF tag:Department EQUALS "Marketing"
  THEN Department = "Marketing"

Rule 3:
  IF tag:Department EQUALS "Sales"
  THEN Department = "Sales"

Rule 4:
  IF tag:Department IS EMPTY
  THEN Department = "Unallocated"

```

Dynamic Approach (Single Rule):

```
Rule 1 (Priority 1):
  IF tag:Department IS NOT EMPTY
  THEN Department = [value of tag:Department]
  
Rule 2 (Priority 2):
  IF tag:Department IS EMPTY
  THEN Department = "Unallocated"

```

Operators

Using the Business Mapping UI, you'll have a vast array of operators to test the logic of your statement. Below shows some of the examples which include operators like greater than which can be handy for testing against things like dates. Choose an operator that makes your statement as straightforward as possible. Using our API, you'll have some additional options including regular expressions.

Boolean Logic

Within an individual statement, you can group expressions together using OR operators and combine with AND operators to get the exact logical outcome to match your business rules. Below is a very basic example:

Business Mappings use two primary boolean operators:

- AND : All statements must be TRUE
- OR : At least one statement must be TRUE

Execution Flow

AND Logic Execution

All statements must evaluate to TRUE:

```
Rule: "Production Engineering Resources"

Statement 1: tag:Department EQUALS "Engineering"
AND
Statement 2: tag:Environment EQUALS "Production"
AND
Statement 3: region STARTS WITH "us-"

Execution:
┌─────────────────────────────────────────────┐
│ Resource: EC2 Instance                      │
│ - tag:Department = "Engineering"  → TRUE    │
│ - tag:Environment = "Production"  → TRUE    │
│ - region = "us-east-1"            → TRUE    │
│                                             │
│ Result: TRUE AND TRUE AND TRUE = TRUE       │
│ Action: Apply mapping                       │
└─────────────────────────────────────────────┘

┌─────────────────────────────────────────────┐
│ Resource: RDS Instance                      │
│ - tag:Department = "Engineering"  → TRUE    │
│ - tag:Environment = "Development" → FALSE   │
│ - region = "us-west-2"            → TRUE    │
│                                             │
│ Result: TRUE AND FALSE AND TRUE = FALSE     │
│ Action: Skip to next rule                   │
└─────────────────────────────────────────────┘

```

OR Logic Execution

At least one statement must evaluate to TRUE

```
Rule: "Engineering or DevOps Resources"

Statement 1: tag:Department EQUALS "Engineering"
OR
Statement 2: tag:Department EQUALS "DevOps"
OR
Statement 3: tag:Team EQUALS "Platform"

Execution:
┌─────────────────────────────────────────────┐
│ Resource: Lambda Function                   │
│ - tag:Department = "Marketing"    → FALSE   │
│ - tag:Department = "DevOps"       → TRUE    │
│ - tag:Team = "Sales"              → FALSE   │
│                                             │
│ Result: FALSE OR TRUE OR FALSE = TRUE       │
│ Action: Apply mapping                       │
└─────────────────────────────────────────────┘

┌─────────────────────────────────────────────┐
│ Resource: S3 Bucket                         │
│ - tag:Department = "Marketing"    → FALSE   │
│ - tag:Department = "Sales"        → FALSE   │
│ - tag:Team = "Support"            → FALSE   │
│                                             │
│ Result: FALSE OR FALSE OR FALSE = FALSE     │
│ Action: Skip to next rule                   │
└─────────────────────────────────────────────┘

```

Mixed Boolean Logic (AND + OR)

```
(Statement 1: tag:Department EQUALS "Engineering"
 OR
 Statement 2: tag:Department EQUALS "DevOps")
AND
Statement 3: tag:Environment EQUALS "Production"

```

Execution Order:

1. Evaluate OR group first: (Statement 1 OR Statement 2)

2. Then evaluate AND with Statement 3

Example 1:

```

┌─────────────────────────────────────────────┐
│ Resource: EC2 Instance                      │
│ Step 1: Evaluate OR group                   │
│   - tag:Department = "Engineering" → TRUE   │
│   - tag:Department = "DevOps"      → FALSE  │
│   - Result: TRUE OR FALSE = TRUE            │
│                                             │
│ Step 2: Evaluate AND                        │
│   - OR Result = TRUE                        │
│   - tag:Environment = "Production" → TRUE   │
│   - Result: TRUE AND TRUE = TRUE            │
│                                             │
│ Final Result: TRUE                          │
│ Action: Apply mapping                       │
└─────────────────────────────────────────────┘

```

Example 2:

```

┌─────────────────────────────────────────────┐
│ Resource: RDS Instance                      │
│ Step 1: Evaluate OR group                   │
│   - tag:Department = "Marketing"   → FALSE  │
│   - tag:Department = "DevOps"      → FALSE  │
│   - Result: FALSE OR FALSE = FALSE          │
│                                             │
│ Step 2: Evaluate AND                        │
│   - OR Result = FALSE                       │
│   - tag:Environment = "Production" → TRUE   │
│   - Result: FALSE AND TRUE = FALSE          │
│                                             │
│ Final Result: FALSE                         │
│ Action: Skip to next rule                   │
└─────────────────────────────────────────────┘

```

## Execution Order & Short-Circuit Evaluation

AND Logic - Short Circuit:

Statement 1 AND Statement 2 AND Statement 3

If Statement 1 = FALSE

→ Stop evaluation (result is already FALSE)

→ Don't evaluate Statement 2 or 3

→ Move to next rule

OR Logic - Short Circuit:

Statement 1 OR Statement 2 OR Statement 3

If Statement 1 = TRUE

→ Stop evaluation (result is already TRUE)

→ Don't evaluate Statement 2 or 3

→ Apply mapping

How can I use API to extract data / Update BMs?

You can use Cloudability APIs to extract and update Business Mappings (BMs). API documentations to extract or update the Business Mappings is available on the Business Mappings Endpoint topic.

How Can I Create Business mapping rule with multiple statements and expressions?

Cloudability allows you to create your own custom dimensions using Business Mappings which is a rule-based engine, where a rule can have more than one statement. Within an individual statement, you can group expressions together using OR operators and combine with AND operators to get the exact logical outcome to match your business rules.

Values of more than one expression in the statement can return True, the final evaluated value would depend on AND/OR operator. e.g. There are two expressions: Exp1 and Exp2

If Exp1 = True and Exp2 = True then Exp1 AND Exp2 would return True and Exp1 OR Exp2 would return True

If Exp1 = True and Exp2 = False or vice-versa then Exp1 AND Exp2 would return False and Exp1 OR Exp2 would return True

If Exp1 = False and Exp2 = False then Exp1 AND Exp2 would return False and Exp1 OR Exp2 would return False

How can I read /access the logic of BMs

Navigate to Organize > Business Mappings. Business mappings list will be is displayed. Click the gear icon to edit business mappings. This displays the statements used in the logic of Business Mappings. Further, you can use the down arrow icon to see the statement rule expression.

Dimensions and Metrics FAQ

How do various cost metrics align to different use cases?

Cloudability supports the following fivecommon Cost Metrics:

Cost(List), Cost(Total), Cost(Adjusted), Cost(Amortized) and Cost(Adjusted Amortized).

The most appropriate use case for each cost metric depends on the specific requirements of the business. It is important to carefully consider the business needs and goals when selecting the appropriate metric.

Can we prevent users from seeing certain dimensions or metrics within Cloudability?

Currently, users cannot be prevented from seeing a certain dimensions or metrics within the Cloudability. By default, all the users would be able to see all the dimensions or metrics in Cloudability.
