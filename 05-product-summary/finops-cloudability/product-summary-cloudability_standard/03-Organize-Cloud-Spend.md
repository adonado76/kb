---
source_system: "apptio-cloudability-standard"
practice: "finops"
language: "en"
doc_type: "cloudability-standard"
consolidated_file: "03-Organize-Cloud-Spend"
source_files_count: 7
last_updated: "2026-07-13"
---

# 03-Organize-Cloud-Spend

## Organize Your Cloud Spend

<!-- sub-header -->
- **breadcrumb:** Setup > Organize Your Cloud Spend
- **source_path:** SSVCLNQ/admin/tag-data.html
- **original_file:** setup-organize-your-cloud-spend.md
- **images:** []

Native cloud billing data is inherently granular, provider-specific, and optimized for metering, not for business analysis. To make cloud costs meaningful for the various teams and personas within your FinOps practice, Cloudability provides a set of organize features that transform raw billing data into consistent, business-aligned views of spend.

At a high level, these features help answer questions such as:

- Who owns this spend?
- What is the cost by team, application, or business unit?
- How do we enforce consistency and governance for tagging across various parts of the business?
- How can we keep team, department, and group‑level cost reporting aligned as our reporting hierarchy evolves?
- What is the cloud cost per unit of business activity?

Cloudability organizes cloud spend using three complementary capabilities:

Tag & Label Mapping – normalizes inconsistent tagging

Tag & Label Mapping allows you to standardize multiple versions of the same tag into a single, consistent dimension. This ensures that logically equivalent tags are treated as one, even when they differ in format or source. For example, mapping various tag keys of "Env", "ENV", and "enviro" to a single dimension named "Environment".

Account Groups – structures spend by cloud account hierarchy (linked accounts, projects, subscriptions)

Account Groups allow logical grouping of cloud accounts across vendors into meaningful collections, such as environments or departments. By organizing spend at the account level, Account Groups provide a stable, easy-to-understand way to segment costs at a high-level.

Business Mappings – applies custom business logic to allocate and categorize costs

Business Mappings provide a rules-based engine that evaluates billing and usage data and assigns costs to Business Dimensions aligned with your organizational taxonomy. These mappings translate vendor-specific metadata such as tags, account names, regions, or services into business categories optimized for analytics and decision-making. This ensures that every dollar is categorized and allocated appropriately.

Furthermore, Hierarchical Business Mappings can be used to define and maintain parent‑child relationships between related Business Dimensions, enabling scalable cost rollups and consistent reporting across organizational levels as structures change.

Business Metrics – applies custom, rules‑based arithmetic calculations to cloud cost and usage data to produce business‑specific financial metrics

Business Metrics extend Cloudability’s standard cost metrics by allowing you to define custom financial calculations that translate raw cloud cost and usage data into business‑relevant measures. Using configurable formulas and conditional logic, Business Metrics enable teams to model chargeback rates, unit costs, efficiency ratios, and other organization‑specific KPIs.

---

## Account groups

<!-- sub-header -->
- **breadcrumb:** Setup > Organize Your Cloud Spend > Account groups
- **source_path:** SSVCLNQ/admin/account-groups-spend.html
- **original_file:** spend-account-groups.md
- **images:**
  - 03-media/apptio-cloudability-standard/create_and_assign_account_groups_1.jpg
  - 03-media/apptio-cloudability-standard/create_and_assign_account_groups_2.jpg
  - 03-media/apptio-cloudability-standard/create_and_assign_account_groups_3.jpg
  - 03-media/apptio-cloudability-standard/create_and_assign_account_groups_4.jpg
  - 03-media/apptio-cloudability-standard/create_and_assign_account_groups_5.jpg
  - 03-media/apptio-cloudability-standard/create_and_assign_account_groups_6.jpg
  - 03-media/apptio-cloudability-standard/create_and_assign_account_groups_7.jpg
  - 03-media/apptio-cloudability-standard/am_sort_accounts.jpg

Accounts and Account Groups enable you to edit and group accounts that are accessed with Cloudability. They also function like tags for AWS accounts, Azure Subscriptions and GCP projects. They allow you to assign a key/value pair where Account Group is the key and Account Group Entry maps the value. For example, you might create an Account Group of Environment and use Account Group Entries to assign a value of "Production", "Staging" or "Development" to individual cloud accounts in Cloudability.

Groups are used to categorize your accounts according to different variables. You can designate the key values for your groups; you might, for example, have groups called "Region, "Product," and "Department." This will allow you to categorize individual accounts according to which region, product, and department they're associated with.

1. Navigate to Organize > Account Groups . When you first navigate to the page, you'll see all of the accounts that you access with Cloudability listed by Account, Account Number, and Vendor.
1. Select Edit Account Groups to the upper right corner of the page. This will bring up a pane where you can designate the key values for your groups. You might, for example, have groups called Region, Product, and Department. This will allow you to categorize individual accounts according to which region, product, and department they're associated with.

Select the Pencil icon to the far right of any account to edit the name and assign it to groups.

You can edit these details for multiple accounts at once by selecting them with the check box, then selecting Edit Accounts .

You can now map your account manually to account groups in Cloudability.

At the top of the Account Management page, select Add Filter to filter by account group.

Click Search Accounts to search for specific accounts.

Select the column headers to sort your accounts.

Select Categorize accounts in the page header. This will navigate you to the Vendor Credentials page to edit credentials for your accounts.

---

## Business mapping

<!-- sub-header -->
- **breadcrumb:** Setup > Organize Your Cloud Spend > Business mapping
- **source_path:** SSVCLNQ/admin/business-tags.html
- **original_file:** spend-business-mapping.md
- **images:**
  - 03-media/apptio-cloudability-standard/business-mapping-rule-structure.png
  - 03-media/apptio-cloudability-standard/business-mapping-listview.png
  - 03-media/apptio-cloudability-standard/business-mapping-addnew.png
  - 03-media/apptio-cloudability-standard/business-mapping-addstmt.png
  - 03-media/apptio-cloudability-standard/export_import_bm.png
  - 03-media/apptio-cloudability-standard/business-mapping-edit.png
  - 03-media/apptio-cloudability-standard/tagging-flow.png
  - 03-media/apptio-cloudability-standard/business_mapping_mceclip3.jpg
  - 03-media/apptio-cloudability-standard/business_mappingmceclip4.jpg
  - 03-media/apptio-cloudability-standard/business_mappingmceclip6.jpg
  - 03-media/apptio-cloudability-standard/execution-flow.png

### What are Business Mappings?

Business Mappings are used to create Business Dimensions that categorize cloud spending according to your organization’s taxonomy.

Unlike vendor-provided or billing-based dimensions, Business Dimensions offer greater flexibility and control. They use evaluation rules—called Business Mapping statements —to translate vendor- and billing-specific metadata into meaningful business concepts. Business concepts are the categories and structures an organization uses to interpret raw data and turn it into information suitable for reporting and decision-making.

The Business Mapping rules engine supports complex logic and can evaluate a wide range of attributes from both billing and usage data. These include vendor-supplied fields such as tags, account names, regions, and service names. Cloudability further extends this capability by offering enhanced attributes like usage family and lease type , enabling more granular and insightful categorization.

The maximum number of Statements for one Business Dimension is 300 000.

The maximum number of Statements across all Business Dimensions is 500 000.

### How do Business Mappings work?

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

### Working with Business Mappings

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

### Execution Order & Short-Circuit Evaluation

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

---

## Business Metrics in Cloudability

<!-- sub-header -->
- **breadcrumb:** Setup > Organize Your Cloud Spend > Business mapping > Business Metrics in Cloudability
- **source_path:** SSVCLNQ/admin/business-metrics.html
- **original_file:** mapping-business-metrics-in-cloudability.md
- **images:**
  - 03-media/apptio-cloudability-standard/business-mappings-new1.png

Overview

Business Metrics allow you to organize your cloud infrastructure to match your business needs. These custom metrics enable you to create meaningful reports that align with your organization's specific financial and operational requirements.

What are Business Metrics?

Business Metrics are customizable financial calculations that you can define in Cloudability to track specific aspects of your cloud spending. Unlike standard metrics, Business Metrics allow you to:

- Create custom formulas using existing cost data
- Apply conditional logic based on dimensions like vendor, service, or account
- Transform raw cloud cost data into business-relevant financial metrics
- Set specific conditions for when metrics should be applied

Creating a Business Metric (using Cloudability UI)

To create a business metric, follow the steps below:

1. Navigate to the Business Mapping section.
1. Select the Metrics tab.
1. Click the New Business Metric button.
1. Enter a meaningful name for your metric.
1. Choose the value format (Currency or Number).
1. Set up the metric definition using either: Default Value: A simple value or metric reference Fixed Value Metric Scenario: Standard cost per employee for chargeback Metric Name: "Cost Per Employee" Type: Default Value Value: 150 Usage: Allocate $150 per employee per month for cloud infrastructure Metric Reference Calculate cost efficiency ratio Metric Name: "Cost Efficiency Ratio" Type: Default Value Formula: Total_Cost / Total_Usage_Hours Where: Total_Cost = Sum of all cloud costs Total_Usage_Hours = Sum of instance hours Prematch Expression: Conditions that determine when the metric applies Scenario: Different cost allocation rates for different environments Metric Name: "Environment Cost Multiplier" Type: Prematch Expression Prematch Expression 1: IF tag:Environment = "Production" THEN Multiplier = 1.0 Prematch Expression 2: IF tag:Environment = "Staging" THEN Multiplier = 0.5 Prematch Expression 3: IF tag:Environment = "Development" THEN Multiplier = 0.3 Default: Multiplier = 0.1

Defining Your Metric Logic

Business Metrics use statements to define their behavior. Each statement consists of:

1. Match Expression: Conditions that determine when the statement applies Example: DIMENSION['vendor'] == 'GCP' Example: DIMENSION['date'] >= '2021-12-01' && DIMENSION['date'] < '2026-12-01'
1. Value Expression: The calculation to perform when conditions match Example: METRIC['bytes_transferred'] Example: METRIC['unblended_cost'] Example: {Cost (Adjusted Amortized)} * 0.83
1. 

Multiple statements can be created for a single metric, and they will be evaluated in the order they appear in the list.

Using Business Metrics in Reports

Once created, your Business Metrics can be used in reports just like any standard metric:

1. Create or edit a report.
1. Add your custom Business Metric to the report.
1. Combine with dimensions like ATUM mappings, vendor, or service name.

Common Use Cases

- Cost Normalization: Create metrics that normalize costs across different cloud vendors
- Internal Pricing: Implement custom pricing models for internal chargeback
- Budget Tracking: Track spending against predefined budgets
- Savings Calculations: Calculate realized or potential savings from optimization efforts
- Custom Amortization: Define your own amortization rules for reserved instances or savings plans
- Unit Economics: Calculate cost per user, transaction or user to understand your economics better

Advanced Features

- Use mathematical operators (+, -, *, /) to create complex formulas
- Reference existing metrics using the {} syntax
- Apply conditional logic using && (AND) and || (OR) operators
- Filter based on specific dimension values like vendor, service name, or region

How do Business Metrics work with Business Mappings?

Business Metrics are crafted using Business Mapping statements that leverage a combination of existing billing data and customer-provided data. Users can create custom metrics related to Cloud billing concepts, populated with the specific values from the logic that best fits their reporting needs in the context of their businesses.

Evaluated at ingestion

When Cloudability ingests the detailed billing data from cloud vendors, we evaluate each cost line item against the Business Mapping statements for your configured Business Metrics. For those of you with a programming background, you can think of the list of statements as similar to a case statement. As soon as there is a match, then the name of the statement itself is evaluated and the resultant value is arithmetically calculated and used to populate the Business Metric for that item. This custom metric name can simply be a meaningful string that you provide. When cloud vendors post new billing data, we'll automatically pick up any changes or additions you make to your Business Mapping statements. To have historic months reflect the updated rules, you can reach out to support or your TAM for this to be actioned.

The custom metric name

Every Business Metric you create requires a name. Think deeply about the business context that you're trying to share and choose a name that people will quickly make sense of. You're giving a name to the custom metric as it will appear in Cloudability reports and dashboards.

The custom metric format

As well as a name, you must decide if this custom metric will surface data formatted as currency or a regular number. The use case driving this custom metric will help you decide on the appropriate format.

For example: If your use case is to provide a surcharge for management fees, then the custom metric format will be currency.

The default value

Once you've decided on a name and a format, you need to set a default value. This is the value the Business Metric will inherit if none of the statements you declare match.

For example: an option here would be to use the cost amount already in the billing data. As you build your Business Metrics, each use case will help you with determining a good default value.

It's about matching with statements

Every statement has two components:

An expression for what to match against. This expression can involve complex boolean logic, a time frame, and has a very comprehensive list of operators that can be applied against all the important attributes of the cost items.

An expression to evaluate, resulting in the value for the Business Metric if the criteria in #1 happens to match.

Below is a simple example:

```
"statements": [{
	"matchExpression": "DIMENSION['vendor'] == 'Amazon'
		|| DIMENSION['vendor'] == 'Azure' ",
	"valueExpression": "METRIC['unblended_cost'] * 1.15"
}]
```

Why do you use business metrics?

Use cases

Business Metrics can help address several use cases where, in addition to Cloudability 's native metrics, you may need custom metrics for your business' reporting requirements. Below are examples of a few of the more popular customer use cases:

| Unit Economics | Also known as Cost per X. A customer can contextualize their Cloud spend as a unit cost in a single in-app metric. For example: cost per ride, cost per active user, cost per subscription, etc. |
| --- | --- |
| Unit Economics | Also known as Cost per X. A customer can contextualize their Cloud spend as a unit cost in a single in-app metric. For example: cost per ride, cost per active user, cost per subscription, etc. |
| KPI Driven Cost | Cost in the context of a business-specific KPI. For example, a customer can contextualize cost in terms of full-time engineers (cost in FTEs) to understand their cloud spend in terms of the number of dev ops engineers needed to support a deployed application. |
| Surcharge/ Markup | A surcharge or markup for Cloud spend can be built in and surface costs inclusive of management fees, license costs, or other surcharges using a single in-app metric. |

The rules engine that drives this feature is equipped with sophisticated logic capabilities, and individual rules can be based on pretty much all of the important attributes that vendors supply with the billing and usage data. These attributes include vendor-supplied dimensions and metrics like cost tags, account names, Unblended Cost but also include enhanced dimensions and metrics provided by Cloudability like Usage Family, Lease Type, and Adjusted Cost.

Creating a Business Metric (using Cloudability API)

Business Metrics can be created using API by leveraging the Business Mapping expression language. Rules are defined through JSON-formatted expressions and statements which are arithmetically evaluated, resulting in a custom metric and corresponding value.

Working with Business Metrics

From the Business Mappings End Point , you can see a feature overview, including the Business Metrics endpoints with corresponding descriptions and examples available for you to work with Business Metrics. Additionally, you'll find templates that you can use to help kickstart your custom metric setup and other helpful resources.

You can set up a maximum of five Business Metrics.

Below are quick references and examples for (i) listing a Business Metric you've already created, (ii) creating a new Business Metric, and (iii) updating an existing Business Metric.

Listing Business Metric

```
 curl -X GET 'https://api.cloudability.com/v3/business-mappings/metrics/' -u '[auth_token]:' 
```

Create a Business Metric

```
 curl -X POST 'https://api.cloudability.com/v3/internal/business-mappings/metrics/' \
  -H 'Content-Type: application/json' \
  -u '[auth_token]:' \
  -d @- >> EOF
{
  "name": "Cost (Surcharge)",
  "numberFormat": "number",
  "defaultValueExpression": "METRIC['unblended_cost']",
  "statements": [
    {
      "matchExpression": "DIMENSION['vendor'] == 'Amazon' || DIMENSION['vendor'] == 'Azure' ",
      "valueExpression": "METRIC['unblended_cost'] * 1.15"
    }
  ]
}
EOF 
```

Expected Output

```
{
  "result": {
    "name": "Cost (Surcharge)",
    "index": 1,
    "kind": "BUSINESS_METRIC",
    "defaultValue": "METRIC['unblended_cost']",
    "numberFormat": "number",
    "updatedAt": "2025-11-12T07:29:27.182Z",
    "statements": [
      {
        "matchExpression": "DIMENSION['vendor'] == 'Amazon' || DIMENSION['vendor'] == 'Azure' ",
        "valueExpression": "METRIC['unblended_cost'] * 1.15"
      }
    ]
  }
}
```

Update a Business Metric

```
curl -X PUT 'https://api.cloudability.com/v3/internal/business-mappings/1/metrics/' \
  -H 'Content-Type: application/json' \
  -u '[auth_token]:' \
  -d @- >> EOF
{
  "name": "Cost (Surcharge)",
  "numberFormat": "number",
  "defaultValueExpression": "METRIC['unblended_cost']",
  "statements": [
    {
      "matchExpression": "DIMENSION['vendor'] == 'Amazon' || DIMENSION['vendor'] == 'Azure' ",
      "valueExpression": "METRIC['unblended_cost'] * 1.25"
    }
  ]
}
EOF
```

Expected Output

```
 {
  "result": {
    "name": "Cost (Surcharge)",
    "index": 1,
    "kind": "BUSINESS_METRIC",
    "defaultValue": "METRIC['unblended_cost']",
    "numberFormat": "number",
    "updatedAt": "2025-11-12T07:32:16.858Z",
    "statements": [
      {
        "matchExpression": "DIMENSION['vendor'] == 'Amazon' || DIMENSION['vendor'] == 'Azure' ",
        "valueExpression": "METRIC['unblended_cost'] * 1.25"
      }
    ]
  }
} 
```

Operators

Using the Business Mappings expression language, you'll have a vast array of operators to test the logic of your statements. Some examples of operators available for you to use include greater than which can be handy for testing against things like dates. Choose an operator which makes your statement as straightforward as possible. By using our API, you'll have additional options, including regular expressions.

For example, timeboxing a business metric value between two dates :

```
 {
  "name": "Cost (Surcharge)",
  "numberFormat": "number",
  "defaultValueExpression": "METRIC['unblended_cost']",
  "statements": [
    {
      "matchExpression": "DIMENSION['date'] >= '2019-01-01T00:00' && DIMENSION['date'] <= '2019-01-31T23:59'",
      "valueExpression": "METRIC['unblended_cost'] * 1.25"
    }
  ]
} 
```

Boolean Logic

Within an individual statement, you can group expressions together using OR operators and combine with AND operators to get the exact logical outcome to match your business rules.

Below is a very basic example:

```
{
  "name": "Cost (in FTEs)",
  "numberFormat": "number",
  "defaultValueExpression": "METRIC['unblended_cost']",
  "statements": [
    {
      "matchExpression": "DIMENSION['date'] >= '2019-01-01T00:00:00' && DIMENSION['date'] <= '2019-01-31T23:59:59' && (DIMENSION['transaction_type'] == 'usage' || DIMENSION['transaction_type'] == 'recurring')",
      "valueExpression": "METRIC['unblended_cost']  / 115000"
    }
  ]
}

```

For additional guidance on using Business Metrics effectively, please contact your account representative or submit a support ticket.

---

## Organize data using hierarchical business mappings

<!-- sub-header -->
- **breadcrumb:** Setup > Organize Your Cloud Spend > Business mapping > Organize data using hierarchical business mappings
- **source_path:** SSVCLNQ/admin/hierarchical-business-mapping.html
- **original_file:** mapping-organize-data-using-hierarchical-business-mappings.md
- **images:**
  - 03-media/apptio-cloudability-standard/hier-business-mapping-listing.png
  - 03-media/apptio-cloudability-standard/hier-business-mapping-create-start.png
  - 03-media/apptio-cloudability-standard/hier-business-mapping-create-name.png
  - 03-media/apptio-cloudability-standard/hier-business-mapping-create-add-layer.png
  - 03-media/apptio-cloudability-standard/hier-business-mapping-create-add-name-layer.png
  - 03-media/apptio-cloudability-standard/hier-business-mapping-create-add-layer2.png
  - 03-media/apptio-cloudability-standard/hier-business-mapping-create-upload-mapping.png
  - 03-media/apptio-cloudability-standard/hier-business-mapping-upload-rev.png

Hierarchical Business Mappings currently have a limit of 1000 Business Mappings rows.

A Hierarchical Business Mapping is a specialized form of Business Mapping designed to create and maintain hierarchical data relationships between Business Dimensions (up to five). Business Dimensions are synthetic dimensions generated using business logic (Business Mapping statements) to map cloud- and vendor-specific tags to meaningful business concepts.

A Hierarchical Business Mapping (HBM) enables you to create a related set of Business Dimensions that can support cost rollups in Cloudability Reporting, View Filters, and Plans. This approach simplifies the creation and maintenance of the necessary business logic needed to keep related Business Dimensions synchronized.

### How does it work?

Imagine you need to report on costs at different levels of cost ownership within your organization: Team, Department, and Group. You want a Business Dimension for each level and you would typically need to create separate Business Mappings for each. However, these dimensions follow a hierarchical structure — Teams roll up to Departments, which in turn roll up to Groups.

To define these relationships using standard Business Mappings, you would need to create statements specifying how each Team maps to a Department and how each Department maps to a Group. While this approach may work for a small number of Teams, Departments, and Groups, it becomes difficult to manage at scale—especially when rollup relationships change over time (e.g., new Teams or Departments are added, or reporting structures are reorganized).

A Hierarchical Business Mapping (HBM) simplifies this process by allowing you to define a single Business Mapping that applies to multiple Business Dimensions in a structured rollup hierarchy. Instead of manually defining individual Business Mappings using complex and inter-dependent IF-THEN style logic, you can create the entire hierarchy using a simple declarative approach:

1. Select a Business Dimension to use as the base of your hierarchy (e.g., Team).
1. Specify the additional hierarchy levels you want (e.g., Department and Group).
1. Upload a mapping file that specifies how values in each tier relate to their parent tier.

Cloudability automatically generates new Business Dimensions and Business Mapping statements for each hierarchy level. If rollup relationships change—such as the addition or removal of Departments or Groups—you simply upload a new mapping file, and the system updates all Business Mapping statements accordingly. This ensures that the correct values of Team, Department, and Group are assigned consistently to guarantee accurate cost rollups.

Additionally, the Hierarchical Business Mapping can be used to create Views that align with the HBM cost rollup structure. See Organize Views Using Hierarchical Views to learn more.

### What is a mapping file?

A mapping file is a structured way to define how values in each Hierarchical Business Mapping (HBM) tier roll up to their parent tier. It is a table (CSV file), where:

- The leftmost column represents the base dimension.
- Each subsequent column represents a parent tier in the hierarchy.
- Each row defines how a value in the base dimension maps to its parent tiers.

For example, the table below shows a mapping file for an HBM where Team is the base dimension, rolling up into Department and then Group. There are 10 Teams (Team 1 through Team 10), and each row specifies how a Team maps to its corresponding Department and Group.

| Team | Department | Group |
| --- | --- | --- |
| Team 1 | Dept A | Group X |
| Team 2 | Dept D | Group Y |
| Team 3 | Dept B | Group X |
| Team 4 | Dept A | Group X |
| Team 5 | Dept C | Group Y |
| Team 6 | Dept B | Group X |
| Team 7 | Dept C | Group Y |
| Team 8 | Dept D | Group Y |
| Team 9 | Dept B | Group X |
| Team 10 | Dept C | Group Y |

For illustrative purposes, here is the same table but reformatted to highlight the hierarchical relationships between Teams, Departments, and Groups. This format makes it easier to see how Groups are composed of multiple Departments , and in turn, how each Department contains specific Teams.

| Team | Department | Group |
| --- | --- | --- |
| Team 1 | Dept A | Group X |
| Team 4 |
| Team 3 | Dept B |
| Team 6 |
| Team 9 |
| Team 5 | Dept C | Group Y |
| Team 7 |
| Team 10 |
| Team 2 | Dept D |
| Team 8 |

In this example mapping file:

- Group X includes Dept A and Dept B : Dept A consists of Team 1 and Team 4 . Dept B consists of Team 3, Team 6, and Team 9 .
- Group Y includes Dept C and Dept D : Dept C consists of Team 5, Team 7, and Team 10 . Dept D consists of Team 2 and Team 8 .

### Hierarchical Business Dimension (HBM) Concepts

Name

The name of the overall hierarchy. This is a required attribute. Choose a name that clearly conveys its overall structure or purpose, as it will appear as the root node for the hierarchy – i.e. the name of the top-level View if you create a Hierarchical View structure for the HBM.

Base Dimension

Every hierarchy is built on top of a base business dimension. This must be an existing business dimension, and cannot be a dimension used in another HBM.

Hierarchy Layers

Additional hierarchy (roll up) layers. Each layer must have a name, and that name must be unique (cannot be the name of an existing business dimension). These will be generated as new business dimensions upon completion of the HBM setup.

### How to set up Hierarchical Business Mappings

Listing and reviewing hierarchical business dimensions

From the Business Mappings home page, under the Hierarchical Dimensions tab, you can see a list of all the hierarchical business dimensions you have set up.

Creating hierarchical business dimensions

To create a new hierarchical business dimension:

1. On the Hierarchical Dimensions tab, select New Business Dimension Hierarchy from the Add menu.
1. The Create Dimension Hierarchy drawer will open on the Overview step > Select Next to advance to the next step ( Define Layers ).
1. Give the hierarchy a name > type the desired name (e.g., Cost Org ) in the Hierarchy Name field. Note: The hierarchy name is used as the root View name its corresponding Hierarchical View. See Organize Views using Hierarchical Views to learn more.
1. Select an existing business dimension as the base of the hierarchy > Click the select the base dimension dropdown and pick a dimension from the list (e.g. Team ). Note: You must select a base dimension before you will be able to add hierarchy layers.
1. Add additional layers to the hierarchy > click the Add Hierarchy Layer button and enter the desired dimension name (e.g. Department ) in the modal that appears. Click Add . Note: Default Value is not used and can be ignored.
1. Repeat Step 5 to add additional hierarchy layers. You may add up to a total of four (4) layers on top of the base dimension. Click Next to finish adding layers to advance to the next step ( Import Values ).
1. Upload a mapping file that describes how base dimension values map to parent tier values > click browse for a file or drag/drop a CSV file into the import box. Click Import to import the mapping file and create the HBM. Note: Clicking the Export the CSV template link will download a template CSV file pre-populated with the current base dimension values ready to be filled in with parent dimension values.

Editing hierarchical business dimensions

To modify an existing hierarchical business mapping:

1. Select the Edit Business Mapping option from the Options (gear) menu. This will open the Edit Dimension Hierarchy drawer on the Import Values step.
1. Rename the Hierarchical Business Dimension >click Next to update.
1. Upload a revised mapping file > click browse for a file or drag/drop a CSV file into the import box. Click Update to import the mapping file and update the HBM with the new mappings. Note: Any associated Hierarchical View will automatically update to mirror the changes in the revised mapping. For more information, refer to Organize Views using Hierarchical Views.

Deleting hierarchical business dimensions

To delete an existing hierarchical business mapping, select the Delete Business Mapping option from the Options (gear) menu. This will remove the hierarchical business mapping from the system and delete the HBM tier business dimensions, but not the base business dimension.

Before deleting an HBM, as best practice, you should first delete its associated Hierarchical View.

For more information, refer to Organize Views using Hierarchical Views.

---

## Calculated Metrics

<!-- sub-header -->
- **breadcrumb:** Setup > Organize Your Cloud Spend > Calculated Metrics
- **source_path:** SSVCLNQ/admin/calculated_metrics.html
- **original_file:** spend-calculated-metrics.md
- **images:**
  - 03-media/apptio-cloudability-standard/calculated-metric-add-button.png
  - 03-media/apptio-cloudability-standard/calculated-metric-create-modal.png
  - 03-media/apptio-cloudability-standard/calculated-metric-edit-dropdown.png
  - 03-media/apptio-cloudability-standard/calculated-metric-update-modal.png
  - 03-media/apptio-cloudability-standard/calculated-metric-delete-dropdown.png
  - 03-media/apptio-cloudability-standard/calculated-metric-delete-message.png
  - 03-media/apptio-cloudability-standard/calculated-metric-details-page.png

### What are Calculated Metrics?

Calculated Metrics are custom, reusable metrics that you can create in Cloudability using standard metrics, business metrics, constants, and basic arithmetic operations.

Unlike vendor-provided metrics, Calculated Metrics offer flexibility to define business-specific KPIs and unit economics measurements that align with your organization's unique requirements.

Calculated Metrics support the following arithmetic operations:

- Addition ( + )
- Subtraction ( - )
- Multiplication ( * )
- Division ( / )

These metrics help tailor Cloudability reporting to your organization's unique business and financial use cases. Calculated Metrics enable teams to create reusable KPIs that can be consistently used across Dashboards and Reports without recreating formulas multiple times.

### How do Calculated Metrics work?

Evaluated at Query Time

When a Dashboard or Report is loaded, Cloudability evaluates Calculated Metrics against the aggregated result set. This means calculations are performed on the final aggregated data rather than on individual cost line items during data ingestion.

This approach provides several advantages:

- Metrics are available immediately after creation
- No data reprocessing is required
- Historical reports automatically reflect formula updates
- Changes take effect instantly across all reports and dashboards

Applied to Aggregated Results

Calculated Metrics operate on aggregated data after grouping and summarization. This means the formula is applied to totals, averages, or other aggregate values rather than individual rows.

Tips for Creating Calculated Metrics

Choose a Clear Name

Each Calculated Metric requires a unique name. Choose a name that clearly conveys its purpose, as it will appear in reports and throughout Cloudability. The name must be unique within your organization and cannot match existing base measure names.

Select the Appropriate Data Source

Choose between Cost or Usage as your data source. All measures referenced in your formula must match the selected data source type.

Define a Clear Formula

Create formulas using valid measure names, constants, and arithmetic operators. Ensure proper use of parentheses to control the order of operations.

Add a Description

Provide a clear description that explains the metric's purpose and calculation logic. This helps other users understand and correctly apply the metric in their reports.

### Working with Calculated Metrics

Listing and reviewing Calculated Metrics

From the Business Mappings page, you can view all Calculated Metrics you have created. The list shows the metric name, description, data source, and creation details.

Creating new Calculated Metrics

To create a new Calculated Metric:

1. Go to Organize → Business Mappings
1. Select New Calculated Metric from the New Business Dimension dropdown
1. Enter a Name for the metric The name must be unique within your organization Cannot match existing base measure names
1. Add a Description The description appears as a tooltip when the metric is used in Dashboards or Reports Helps other users understand the metric's purpose
1. Select a Metric Type (Number Format) Number - Default format for general numeric values Amount - For currency/cost values Percentage - For ratio or percentage calculations
1. Select the Data Source Cost - Use cost-related metrics (e.g., unblended_cost, amortized_cost) Usage - Use utilization metrics (e.g., avg_cpu_utilization, memory_usage) All measures in your formula must match the selected data source
1. Define the Formula Use valid measure names from your selected data source Include constants (numbers) as needed Apply arithmetic operators: +, -, *, / Use parentheses to control order of operations
1. Click Save to create the metric

Once saved, the Calculated Metric becomes immediately available throughout Cloudability reporting.

Editing Calculated Metrics

To update an existing Calculated Metric:

1. Go to Organize → Business Mappings
1. Find the Calculated Metric you want to edit from the list
1. Click on the gear icon and choose Edit metric from the dropdown
1. Update the fields as needed: Description Number Format Formula Data Source
1. Click Save to apply changes

Deleting Calculated Metrics

To delete a Calculated Metric:

1. Go to Organize → Business Mappings
1. Find the Calculated Metric you want to delete from the list
1. Click on the gear icon and choose Delete metric from the dropdown
1. Click OK on the Delete Calculated Metric confirmation message

Important: A Calculated Metric can only be deleted if it is not currently referenced by any saved reports, dashboards, or widgets. If the metric is in use, you must remove those references before deletion.

Viewing Calculated Metric Details

To view the details of a specific Calculated Metric:

1. Go to Organize → Business Mappings
1. Find the Calculated Metric you want to view from the list
1. Click on the Name of the metric
1. View the complete details on the metric details page

The details page displays:

- Full Metric name and description
- Full Expression
- Creation and modification timestamps
- Creator and last modifier information

### Common Use Cases

Compare Cloud Cost Models

Understand the difference between original cloud cost and effective amortized cloud cost to measure the financial impact of commitments, discounts, and negotiated pricing.

Example:

```
Cost (List) - Cost (Amortized)
```

This calculation shows the total savings achieved through pricing optimizations.

Analyze Savings Efficiency

Measure how effectively pricing optimizations reduce costs across vendors, services, teams, and business units.

Example:

```
(Cost (List) - Cost (Amortized)) / Cost (List)
```

This percentage shows the proportion of list price saved through optimizations.

Build Unit Economics

Create operational KPIs to understand scalability and operational efficiency.

Examples:

- Cost per resource: unblended_cost / usage_quantity
- Cost per cluster: unblended_cost / cluster_count
- Cost per environment: unblended_cost / environment_count
- Cost per workload: unblended_cost / workload_count

Apply Discounts or Markups

Model different pricing scenarios by applying percentage-based adjustments.

Examples:

- 20% discount: unblended_cost * 0.8
- 10% markup: unblended_cost * 1.1
- Tiered pricing: (unblended_cost + 100) / 2

Calculate Utilization Buffers

Add safety margins to utilization metrics for capacity planning.

Example:

```
avg_cpu_utilization * 1.1
```

This adds a 10% buffer to CPU utilization for planning purposes.

### Permissions

Calculated Metrics support three permission levels that control user access and capabilities.

Full Access

Permission: CalculatedMetricsFeatureFullAccess

Users with full access can:

- View all calculated metrics
- Create new calculated metrics
- Update any calculated metric
- Delete any calculated metric

Own Edit Access

Permission: CalculatedMetricsFeatureOwnEditAccess

Users with own-edit access can:

- View all calculated metrics
- Create new calculated metrics
- Update only metrics they created
- Delete only metrics they created

View Only Access

Permission: CalculatedMetricsFeatureViewOnlyAccess

Users with view-only access can:

- View all calculated metrics
- View metric definitions and formulas
- Use metrics in reports and dashboards
- Cannot create, edit, or delete metrics

### What's the difference between Calculated Metrics vs Business Metrics?

| Feature | Calculated Metrics | Business Metrics |
| --- | --- | --- |
| Evaluation Timing | Evaluated at query time | Evaluated at ingestion |
| Processing Level | Applied to aggregated results | Applied to each row separately |
| Conditional Logic | No conditional expressions | Supports match expressions |
| Availability | Available immediately | Requires data reprocessing |
| Metric Limits | Unlimited | Up to 5 Business Metrics |
| Formula Complexity | Arithmetic operations only | Supports complex conditional logic |
| Historical Data | Updates apply retroactively | Requires reprocessing for historical data |

### Expression Rules and Validation

Supported Operators

- + Addition
- - Subtraction
- * Multiplication
- / Division

Validation Rules

- Name: Must be unique within the organization and cannot match existing base measure names
- Expression: Must use valid operators and valid measure names for your organization
- Source Type: All measures in the expression must match the specified source_type (cost or usage)
- Parentheses: Must be properly balanced in expressions
- Measure Names: Can contain letters, digits, and underscores
- Decimals: Use period (.) for decimal numbers

Expression Examples

Cost Metrics:

```
unblended_cost * 0.8
(unblended_cost + 100) / 2
business_metric9 / total_adjusted_amortized_cost * bytes_transferred
```

Usage Metrics:

```
avg_cpu_utilization * 1.1
burst_balance * 100
avg_running_instances_per_hour / business_metric9
```

### Frequently Asked Questions (FAQ)

When are Calculated Metrics evaluated?

Calculated Metrics are evaluated at query time. This means calculations are performed when a Dashboard or Report is loaded rather than during billing data ingestion.

As a result:

- Metrics are available immediately after creation
- Historical reports automatically reflect formula updates
- No data reprocessing is required
- Changes take effect instantly across all reports

What types of formulas are supported?

Calculated Metrics support formulas built using:

- Standard metrics (cost and usage measures)
- Business metrics
- Constant values (numbers)
- Addition ( + )
- Subtraction ( - )
- Multiplication ( * )
- Division ( / )
- Parentheses for order of operations

Example:

```
(Cost (List) - Cost (Amortized)) / Cost (List)
```

Can Calculated Metrics use conditional logic?

No. Calculated Metrics do not support:

- IF/THEN logic
- CASE statements
- Boolean conditions
- Match expressions

For conditional or rule-based logic, use Business Metrics or Business Mappings instead.

Do Calculated Metrics require data reprocessing?

No. Calculated Metrics are available immediately after creation or modification and do not require billing data reprocessing. Changes to formulas automatically apply to all historical data when reports are run.

Is there a limit to the number of Calculated Metrics?

No. Cloudability supports an unlimited number of Calculated Metrics per organization.

Can Calculated Metrics reference other Calculated Metrics?

No. Calculated Metrics are designed to use standard metrics, business metrics, constants, and arithmetic operations. Nested or chained Calculated Metrics (where one Calculated Metric references another) are not currently supported.

What happens if I delete a Calculated Metric that's in use?

You cannot delete a Calculated Metric if it is currently referenced by any saved reports, dashboards, or widgets. You must first remove all references to the metric before deletion is allowed. This prevents breaking existing reports and dashboards.

How can I use the API to manage Calculated Metrics?

You can use Cloudability APIs to create, read, update, and delete Calculated Metrics programmatically. API documentations to mange Calculated Metrics is available on the Calculated Metrics Endpoint topic.

---

## Tag and Label Mapping

<!-- sub-header -->
- **breadcrumb:** Setup > Organize Your Cloud Spend > Tag and Label Mapping
- **source_path:** SSVCLNQ/admin/map-tags.html
- **original_file:** spend-tag-label-mapping.md
- **images:** []

Cloudability enables comprehensive cost allocation by ingesting and normalizing tags and labels from supported cloud providers, SaaS platforms, and container environments. This document describes the tag and label types supported by each vendor, how they are collected (billing data vs. APIs), required permissions, and key considerations such as formatting differences, precedence rules, and known limitations

### Tag and label support by vendor

AWS Tags

- Resource level tags These are part of the AWS CUR files and no extra permissions are required within Cloudability for enabling these
- Account level tags (via API) To get account level tags from AWS Organizations, Cloudability needs an additional permission named organizations:ListTagsForResource . Note: Account level tags are currently not available in Cloudability Gov. These are displayed in the following format in Cloudability: cldy:aws:accountLevelTag:<tag key>

Difference between AWS Legacy CUR and CUR 2.0 tags:

Legacy CUR tags format:

- AWS tags = aws:<tag key> e.g. aws:autoscaling:groupname
- user tags = <tag key>

CUR 2.0 tags format:

- AWS tags= aws_<tag key> will be separated with an underscore = e.g. aws_autoscaling_group_name
- user tags = user_<tag key> e.g. user_application

Azure Tags

Cloudability supports the below types of tags for Azure:

- Resource level tags These are part of the Azure Export files and no extra permissions are required within Cloudability for enabling these Tags format - cldy:Azure:ResourceTag:<resource tag key>
- Resource group tags (via API) To get Resource group tags from Azure, Cloudability needs an additional permissions for advance credentials either management:Reader or Microsoft.Resources/subscriptions/resourceGroups/read on the subscription. Tags format - cldy:Azure:ResourceGroupTag:<resource group tag key> Important: If a tag key exists on a resource at both the resource level and the resource group level, and you map the plain tag key from the drop-down (for example, project ), Cloudability will resolve the value as follows: The resource-level tag is used when present. If the resource-level tag is missing or null, the resource group tag is used as a fallback. If you do not want the resource group tag to be used as a fallback, map the explicit resource-level tag instead (for example, cldy:Azure:ResourceTag:project ).
- Subscription level tags (via API) To get subscription level tags from Azure, Cloudability needs an additional permission: subscription:ReadSubscription Tags format - cldy:Azure:SubscriptionLevelTag:<subscription tag key>

GCP Tags and Labels

Cloudability supports the below mentioned types of tags and labels for GCP:

- GCP Labels These are part of the GCP Billing data extract and no extra permissions are required within Cloudability for enabling these. Cloudability supports the below labels: Resource labels Project labels System labels If same key is configured for project, system and resource labels, the precedence to show the label on Cloudability UI is as follows: Resource > Project > System Note: Cloudability does not support mapping of labels which are a result of the "GKE cost allocation" feature from GCP. Labels such as goog-k8s-* or k8s-* will result in (not set) values. To benefit from container cost allocation, clusters should be provisioned for use in the Cloudability Containers feature which enables namespace and label level costs.
- GCP Tags These are part of the GCP Billing data extract and no extra permissions are required within Cloudability for enabling these Format of the GCP tags supported in Cloudability: cldy:gcp:tag:<tagKey> for direct tag assignments cldy:gcp:tag:<tagKey>:inherited for inherited tags cldy:gcp:tag:<tagKey>:namespace for tag attachment level

OCI Tags

- Resource and compartment level tags Resource level or compartment level assigned by namespace. These are part of the OCI Billing data and no extra permissions are required within Cloudability for enabling these Compartment level tags must be assigned via a Tag Namespace first and then assigned as a Tag Default in OCI

```
cldy:oci:compartmentname
```

```
cldy:oci:compartmentid
```

IBM Tags

- Resource level tags These are part of the IBM Billing data and no extra permissions are required within Cloudability for enabling these

- Resource level custom tags These are part of the Databricks Billing data and no extra permissions are required within Cloudability for enabling these

```
cldy:databricks:workspaceid
```

- Resource level tags These are part of the MongoDB invoice data and no extra permissions are required within Cloudability for enabling these

```
cldy:mongodb:groupid
```

```
cldy:mongodb:groupname
```

Snowflake Tags

We support Snowflake warehouse and account level tags in the below format. Be aware that there are specific requirements for warehouse tags to populate, including enabling the TAG_REFERENCES view in Snowflake. Please see the credentialing documentation for more details.

cldy:snowflake:account:<tagkey>

cldy:snowflake:warehouse:<tagkey>

Kubernetes (K8s) Labels for containers

Different from typical vendor cost allocation tags, Kubernetes labels are also supported within the Tag & Label Mapping feature. These labels are fundamentally different than cost tags/labels as they do not exist in the billing data, instead they're a result of the Cloudability Container Insights feature which provides granular cost allocation for your supported container spend (EKS, GKE, AKS, OpenShift).

These labels will be available for mapping once you provision a supported cluster with the IBM FinOps Agent. For more information, please see "Define additional dimensions based on K8s labels" under Container Cost Allocation .

### Frequently asked questions

Why are AWS resource-level tags missing on the Tag & Label Mapping page?

Before mapping, you must instruct AWS which tags to include in your cost data exports. You can do this in the AWS Billing Preferences. Only the selected tag keys will appear in the CUR.

Why do I see a (not set) tag value in reports?

If you've built a report in Cloudability with a tag column, you've likely seen a value called (not set) .

This could mean one of these things:

- You have not told the vendor (like AWS) to include all your tags in your billing data
- You have resources that are taggable but are not yet tagged
- You have spend that is not taggable
- You didn't request to reprocess the historical data

How do I know what resources are taggable?

Each vendor has their own definitions and restrictions on what they define as a "taggable resource". Cloudability offers the Tag Explorer feature to assist you in getting transparency of your top taggable and untaggable spend which can help you understand where to focus your tagging efforts.

When in doubt, it is best to refer to the vendor-specific documentation on whether a specific type of usage is taggable. Common examples of untaggable spend are Support costs, commitment fees, Tax, EBS snapshots, and some marketplace charges.

Why aren't my Azure resource group tags showing up?

To populate resource group and subscription-level tags for Azure, we require additional permissions to fetch them from the Azure API (known as "advanced credentials" in Cloudability). Please reference the previous portion of this document to check the permissions that are required.

Can I map multiple tag keys to a single tag dimension in Cloudability utilizing a tool like regex or wildcards?

At present, Cloudability does not allow you to map multiple tag keys to a single dimension using regex or wildcards.

How does Cloudability handle multiple tag keys?

If the same resource has multiple tag keys then Cloudability will pick up the first valid tag key (one with a value) which was added to the tag key list for the given dimension.

How can I extract a value from a tag?

1. Using Tag Explorer: Navigate to Insights > Tag Explorer, under Taggable Spend tab, apply filter for ' Tags & Labels' Dimension. In the chart, you can mouse hover to different Tag and view the tag values.
1. Using Reports: You can generate a report by including a specific Tag (Value) dimension in the report. The result will display all the different Tag (Values) for different Tag (Keys).

What is the limit on tags that can be mapped in tags and labels?

In Cloudability, the current dimension limit for Tags & Labels is 50.

Can we add more than 30 Tag & Label mappings?

Cloudability has increased the number of available 'Tags & Label' mappings in Cloudability by 20. This means customers can now have up to 50 reporting dimensions in the platform that are specific to mapped tags and labels. This will particularly help customers who are multi-cloud and have many tag or label keys in their environment. Cloudability administrators can add these additional mappings in the 'Tag & Labels' Mapping feature.

If a tag value changes in the CSP raw data, how will it appear in Cloudability?

Suppose you changed the tag on CSPs side from 'playground' to 'game'. The old tag value has already been written to previous billing data, and any change in value wouldn’t be retroactive. So, any new billing data, associated will reflect the new tag value. You should leverage business mappings, which can be applied to historical data.

You cannot update historical tags unless the you upload new billing files for old months with the new tag value. If you'd like to pursue this, open a support case and Apptio Support can trigger a data refetch for the updated data. Be aware when data is refetched , all previous data will be overwritten with the current values. So in the case of hierarchical tags (account/subscription level), Cloudability will take in the current value of those tags and apply it to all refetched data.

How will Cloudability process the tags if the same resource has multiple tag categories assigned to it i.e., resource tag, resource group tag and account level tag?

If a customer has 3 resources namely Resource A, Resource B and Resource C.

- Resource A has a resource tag called Owner with value as R1
- Resource B has a resource tag called Owner with value as R2
- Resource C has no tag assigned

These 3 resources belong to a resource group namely Resource X that has a resource group tag called Owner with value = RG1

Resource X belongs to an Azure subscription namely Subscription Z that has a subscription level tag called Owner with value = S1

In Cloudability, customer creates a new tag dimension called CLDY Owner and maps the above tag keys in the below mentioned sequence:

cldy:azure:resourcetag:owner | cldy:azure:subscriptionleveltag:owner | cldy:azure:resourcegrouptag:owner

Resource A has all 3 tags (resource tag, resource group tag and subscription tag) but because resource tag is the first in the sequence per the dimension created above (CLDY Owner), resource tag will be picked first for Resource A with tag key Owner and value = R1, and resource group tag and subscription tags will be ignored. Same will happen for Resource B, where resource tag will be picked up with tag key = Owner and value = R2. When it comes to Resource C, there is no resource tag associated with it, so it will check what is next in the sequence in the dimension created. Since the next is resource group tag, resource group tag with tag key = Owner and value = RG1 will get assigned to Resource C.

Now lets say if the customer created the tag dimension in a different order as below, where resource group tags come first:

cldy:azure:resourcegrouptag:owner | cldy:azure:resourcetag:owner | cldy:azure:subscriptionleveltag:owner

In this case, resource group tag will be assigned to all 3 resources because they all have resource group tags (tag key = Owner and value = RG1). Resource tags and subscription tags will get ignored here, because resource group tags comes first in the sequence and all 3 resources have resource group tags associated with them.

Similarly if subscription level tag was the first one added in the sequence, then the subscription tag with tag key = Owner and value = S1 will get assigned to the tag dimension and resource group tags and resource tags will be ignored.

---
