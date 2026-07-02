---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Glossary - Apptio Planning applications"
breadcrumb: []
source_path: "it-planning/planning/glossary-apptio-planning.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Glossary - Apptio Planning applications

## A

Actuals Actual costs incurred, per month. See [Import and publish actuals](import-publish-actuals.html).

Actuals currency conversion rate table When support for multiple currencies is enabled,
the Actuals rate table defines currency conversion (FX) rates against the *common currency* for
actuals imported into the Spend Management component. See [Support multiple
currencies](support-multiple-currencies.html).

Admin role An assigned role in Apptio Planning applications. The Admin is the
highest-level role in Apptio applications. Admin users are granted all available permissions. See
Frontdoor permissions and roles.

Approver role Designated people who can approve or reject submitted plans. Approvers are
not tied to credential hierarchy, but to Cost Object hierarchy. Apptio Planning applications support
up to five levels of approvers. See [Manage Cost Object Permissions reference data](manage-cost-object.html "Cost Object Permissions determine which users can view, edit, submit, or approve Department-level plans (Cost Objects). Each Department can have one or more users assigned with edit-level permissions and, for Multi-Level Approvals, approval-level permissions.").

Asset class A set of attributes that, when applied to a specific capital asset, determine
how the asset's purchase and depreciation are accounted for in OpEx and CapEx budgets. Asset classes
are maintained as reference data. See [Manage Asset reference data](manage-asset-configuration.html).

## B

Base currency See *common currency*.

Baseline An existing forecast or budget plan on which a new plan can be based. When used,
the baseline provides the initial line item details for subsequent annual budget plans, or monthly
or other duration forecasts. See [Create a plan or forecast](create-budget-plan.html). After creating a new plan using a baseline, a Budget Process
Owner can make global or individual adjustments to its baseline values. See [Enter financial details and adjust
baseline values](enter-financial-details.html).

Budget The financial expression of an organization's fiscal year plan, divided into
monthly increments. Apptio Planning applications enable and govern a predictable, controlled budget
creation process based on monitoring and tracking changes and approvals. See [Budget planning and
forecasting](budget-planning-forecasting.html).

Budget Owner role This role inputs and edits Cost Object budget information. This can
apply to owners of single or a group of departments, projects, services, or business units. See
[Budget planning and
forecasting](budget-planning-forecasting.html).

Budget Process Owner role This role can create, open, review, and close budget plans. See
Frontdoor permissions and roles.

Business Relationship Manager role Represents a Business Unit regarding service requests.
This role is responsible for submitting planned Business Unit consumption for specific service
offerings. See [Request
services for Projects and Business Units](sdp/request-services-projects.html).

Business Unit A logical element or segment of a company (such as accounting or marketing)
representing a specific business function and a place on the organizational chart under the domain
of a manager. See[Service
reference data](sdp/manage-service-reference.html)
[Manage Service reference
data](sdp/manage-service-reference.html).

Business Unit Owner role The owner of a Business Unit specified in reference data. The
Business Unit Owner can edit their assigned Business Unit budget data.

## C

Charges Internal "revenue" received from other Cost Objects due to usage. The total
internal revenue is the quantity consumed times the service unit price*.* See [Calculate unit cost and unit
price](sdp/calculate-service-unit.html) or [Forecast
demand for services](sdp/forecast-demand-services.html).

Common currency Also called the base or company currency, the common currency is a single
currency used for all currency conversions. This is usually the organization's currency of record.
All currency conversion rates are set against this currency. See [Support multiple
currencies](support-multiple-currencies.html).

Consumers Cost Objects that are using the cost and resources of another Cost Objects, and,
as a result, incur cost. See [Forecast indirect service costs](sdp/forecast-indirect-service.html).

Contract type Attributes of contracts that map to specific general ledger account codes.
Good contract type names help cost center owners categorize contracts in ways that make the most
sense to them and their budget context, yet map to the correct general ledger account codes.
Contract types are maintained as reference data. See [Manage Contract reference data](manage-contract-configuration.html "The tasks below can only be performed by users assigned to the Admin or Budget Process Owner roles. For additional information on roles, see Frontdoor permissions and roles.").

Cost center A built-in dimension in Reference data that aligns to your Cost Objects in
your budget plan structure. See [Manage dimensions](manage-reference-data.html).

Cost Center Owner role The owner of a Cost Object. This role enables owners of Cost
Objects to edit those Cost Objects. See Frontdoor permissions and roles.

**Currency conversion rate tables** When multiple currency support is
enabled, the application supports two rate tables: Plan and Actual. The rate tables define currency
conversion (FX) rates, against the common currency. See [Support multiple currencies](support-multiple-currencies.html).

Cost Objects Entities for which a cost is compiled. In Apptio Planning applications, these
consist of Departments, Projects, Services, Business Units, and Labor Pools. See [Manage Cost Object Permissions reference
data](manage-cost-object.html "Cost Object Permissions determine which users can view, edit, submit, or approve Department-level plans (Cost Objects). Each Department can have one or more users assigned with edit-level permissions and, for Multi-Level Approvals, approval-level permissions.").

## D

Department Represents a section of your company that contributes or supports the company's
overall mission and goals. In Apptio Planning applications, Departments are centered around the IT
organization. They represent the basic structure of the IT organization in budgeting and reporting
rollup. They should align to Cost Centers, but this is not a requirement. See [Manage Financial reference
data](manage-financial-dimensions.html "The tasks below can only be performed by users assigned to the Admin or Budget Process Owner roles. For additional information on roles, see Frontdoor permissions and roles.").

Department Owner role The owner of a department specified in Reference data. The
Department Owner can edit their assigned departmental budget data. See [Manage Financial reference
data](manage-financial-dimensions.html "The tasks below can only be performed by users assigned to the Admin or Budget Process Owner roles. For additional information on roles, see Frontdoor permissions and roles.").

Dimensions Essential data categories in budget line items. Use dimensions as groups and
filters to analyze data. Apptio Planning applications include several built-in dimensions, and you
can add your own custom dimensions. Dimension definitions and values are a type of reference data.
See [Manage custom
dimensions](manage-custom-reference.html "The tasks below can only be performed by users assigned to the Admin or Budget Process Owner roles. For additional information on roles, see Frontdoor permissions and roles.").

Direct costs Costs that have been planned and directly entered. See [Manage direct costs](manage-direct-costs.html "The Expenses page provides visibility on expected direct costs associated with all the Cost Objects in Apptio Planning applications. Indirect costs are calculated differently, depending on the cost object.").

Dynamic Pricing A supported pricing strategies in Service Demand Planning. Dynamic pricing
changes price with the goal of recovering the cost of the service. Therefore, the price of the
service, when dynamic pricing is enabled, is the cost of providing the service (Price = Unit Cost).
See [Manage Service
reference data](sdp/manage-service-reference.html).

## F

Flexible plan details Support for custom data that enhances your analysis and reporting
capabilities. Flexible plan details include built-in and custom dimensions, and custom attributes of
both. See [Manage custom
dimensions](manage-custom-reference.html "The tasks below can only be performed by users assigned to the Admin or Budget Process Owner roles. For additional information on roles, see Frontdoor permissions and roles.").

Fixed Price A price that is locked in for a period of time. In Service Demand Planning,
the Dynamic pricing model also supports Fixed prices. A Service Owner can override the
dynamically-set price of a service to a user-determined price. See [Manage Service reference
data](sdp/manage-service-reference.html).

Forecast A current view of projected financial results combining historical actuals and
projections for future periods. A forecast uses a prior budget or forecast baseline (optionally),
and incorporates prior month actuals, if available. See [Budget planning and forecasting](budget-planning-forecasting.html).

## G

Goods and Services Tax See [Value Added Tax](#GlossaryApptioplanningapplications__VAT).

## I

Indirect costs Costs not directly associated with a single activity, event, or other Cost
Object. The total indirect cost is the quantity consumed times the price of the services. See [Forecast indirect service
costs](sdp/forecast-indirect-service.html).

## L

Labor Resource Pools A group of trained people from which to source staff. In Apptio Planning applications, these are people whose skill set that can be leveraged across various
services and projects. See [Manage Labor reference data](manage-labor-configuration.html "The tasks below can only be performed by users assigned to the Admin or Budget Process Owner roles. For additional information on roles, see Frontdoor permissions and roles.").

## M

Multi-currency Multiple currency support that, when enabled, supports the planning,
reporting, and analysis needs of organizations that work with multiple currencies. See [Support multiple
currencies](support-multiple-currencies.html).

Multi-year planning A single plan with a duration of up to 6 years (72 months). A multiple
year plan allows you to plan and track IT financials in a continuous, years long time horizon.
Planning for multiple years allows for long-range plans and rolling forecasts across fiscal year
boundaries. See [Plan for multiple
years](plan-multiple-years.html "Use multiple-year planning features to plan and track your IT financials in a continuous, multi-year time horizon. You can support long-range plans and rolling forecasts across fiscal year boundaries.").

## N

Net Expenses The sum of all direct costs and indirect costs minus any charges (Direct Cost
+ Indirect Cost - Charges = Net Expenses). See [View net expenses](view-net-expense.html).

## P

Plan currency conversion rate table When support for multiple currencies is enabled, the
Plan rate table defines currency conversion (FX) rates against the common currency for budget plans
and forecasts. See [Support multiple currencies](support-multiple-currencies.html).

Project IT Projects are any planned initiative of the IT department. This can be software
development, network upgrades, and so forth. See [Project Financial Planning](pfp/gs-project-financial.html "◆ Applies to: Planning with Project Financial Planning.").

Project Owner Role The owner of a project specified in reference data. The Project Owner
can edit their assigned project budget data. See [Project Financial Planning](pfp/gs-project-financial.html "◆ Applies to: Planning with Project Financial Planning.").

## R

Rate tables A multiple currency support feature. See [Currency conversion rate tables](#GlossaryApptioplanningapplications__currencyconvert).

Reference data The cost centers, chart of accounts, custom dimensions, and historical
budget data used by a plan. This data is normally uploaded and maintained by the Admin or Business
Process Owner. See [Configure and administer Planning](configure-administer-apptio.html).

Region-based Pricing A pricing model that applies adjustments to the base-price of a
service, based upon the region of the consumer.

Revenue (for services) Credits received from charges to consumers based upon their usage
of your service. See [Calculate unit cost and unit price](sdp/calculate-service-unit.html).

## S

Service Technology components that Apptio Planning applications provide and maintain for
the business. Examples include applications, equipment, computers, laptops, phones, and
communication services (voice, internet, wifi access). See [Service Demand Planning](sdp/gs-service-demand.html).

Service Owner roleThe owner of a service specified in reference data. The Service Owner
can edit their assigned service budget data. See [Forecast demand for services](sdp/forecast-demand-services.html).

Simplified Submission The revised submission and approval process of plans. After
permissions are set up, the approval workflow is separated from the Cost Center hierarchy. See [Manage Cost Object Permissions reference
data](manage-cost-object.html "Cost Object Permissions determine which users can view, edit, submit, or approve Department-level plans (Cost Objects). Each Department can have one or more users assigned with edit-level permissions and, for Multi-Level Approvals, approval-level permissions.").

## T

Target (budget) A financial budget threshold per cost center. In the Summary page Tree Map
chart, cost centers budget values are color-coded to indicate the degree to which they are above or
below their target value. See [Set financial targets](set-financial-targets.html).

Target (labor) An annual headcount threshold per cost center. In the Labor table, labor
headcount KPIs report the plan, target, and variance values. See [Set labor headcount targets](set-labor-headcount.html).

Tiered Pricing A pricing model that provides different prices for the same service based.
The price group of the consumer determines which price a consumer is charged. See [Edit the Company Profile](edit-company-profile.html "The Company Profile allows Admin and Budget Process Owner users to configure application-wide settings that customize the display, enable or disable features, and define workflow behavior across Apptio Planning.").

## U

Units (Volume)A Single, discrete quantity of a specific service or project. See
[Manage Service reference
data](sdp/manage-service-reference.html).

## V

**Value Added Tax (VAT)** A type of consumption tax that is placed on a product
whenever value is added at a stage of production and at final sale. See [Manage Contract reference
data](manage-contract-configuration.html "The tasks below can only be performed by users assigned to the Admin or Budget Process Owner roles. For additional information on roles, see Frontdoor permissions and roles.").
