---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Reference data dimensions"
breadcrumb: []
source_path: "planning/manage-reference-data.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Reference data dimensions

Applies to: Apptio planning applications with [Project Financial Planning](pfp/gs-project-financial.dita "(Opens in a new tab or window)"). The tasks below require you to
license Project Financial Planning. To enable Project Financial Planning features, see [Edit the Company Profile](edit-company-profile.dita "(Opens in a new tab or window)"). The
tasks below can only be performed by users assigned to the Admin or Budget Process Owner roles. For
additional information on roles, see Frontdoor permissions and roles.

Dimensions are the essential data categories in budget line items. Many built-in dimensions have
dependencies on other dimensions. See [Reference data attribute and
dimensions dependencies](#Referencedatadimensions__Referencedataattributeanddimensionsdependencies). In Apptio planning applications, you can work with TBM Studio data
in Excel, work with master data sets, and update reference data. See [Manage reference data](manage-itfmf-reference.dita "(Opens in a new tab or window)").

For detailed data and format information for all of the reference and financial data required for
Planning, see the [Planning Reference Data Guide](https://community.apptio.com/docs/DOC-8065 "(Opens in a new tab or window)") .

## View default dimensions

Navigate to Planning > Configuration > Reference Data. If you do not see the dimension or group
you are looking for, you may need to enable these features (see [Edit the Company Profile](edit-company-profile.dita "(Opens in a new tab or window)")).

The following are descriptions of the default Dimensions. Select a dimension title for
field-level descriptions and examples.

## Standard dimensions

Standard dimensions can include the following categories:

[Financial
dimensions](manage-financial-dimensions.dita "(Opens in a new tab or window)"):

- Account
- Account Category
- Cost Center
- Department
- Location
- Variance Driver
- Vendor

[Labor Configuration
dimensions](manage-labor-configuration.dita "(Opens in a new tab or window)"):

- Labor Allocation Rules
- Labor Rates
- Roles

[Contract
Configuration dimensions](manage-contract-configuration.dita "(Opens in a new tab or window)"):

- Contract Type
- VAT Rates

[Cost Object Permissions
dimensions](manage-cost-object.dita "(Opens in a new tab or window)"):

- Cost Object Permissions

[Asset Configuration
dimensions](manage-asset-configuration.dita "(Opens in a new tab or window)"):

- Asset Class

## Project Financial Planning dimensions

The following are the default dimensions for licensed Project Financial Planning users:

[Project
Configuration dimensions](pfp/manage-project-configuration.dita "(Opens in a new tab or window)"):

- Project
- Project Group
- Score

[Labor
dimensions](manage-labor-configuration.dita "(Opens in a new tab or window)"):

- External Labor Pools
- Internal Labor Pools

[Allocation
dimensions](manage-allocation-configuration.dita "(Opens in a new tab or window)"):

- Transfer Account Default

## Service Demand Planning dimensions

The following are the default dimensions for licensed Service Demand Planning users.

[Service
dimensions](sdp/manage-service-reference.dita "(Opens in a new tab or window)"):

- Business Unit
- Price Group
- Service
- Service Categories
- Service Price Adjustments
- Unit of Measure

[Labor Configuration
dimensions](manage-labor-configuration.dita "(Opens in a new tab or window)"):

- External Labor Pools
- Internal Labor Pools
- Labor Allocation Rules
- Labor Rates
- Role

[Allocation
dimensions](manage-allocation-configuration.dita "(Opens in a new tab or window)"):

- Transfer Account Default

## Multiple currency dimensions

The following features are visible only if support for multiple currencies is enabled See [Edit the Company Profile](edit-company-profile.dita "(Opens in a new tab or window)").
Following are the default dimensions for multiple currency support. See [Support for multiple
currencies](support-multiple-currencies.dita "(Opens in a new tab or window)").

[Rate Tables
dimensions](manage-multi-currency.dita "(Opens in a new tab or window)"):

- Actuals Currency Rate
- Plan Currency Rate

## Reference data attribute and dimensions dependencies

Many dimensions are related. Information from one dimension can be dependent on another dimension
(dependencies) in the system. This can influence which attributes can be deleted.

The following are the dimensions and attributes that may depend on other dimensions:

| Dimension | Dependent attribute | Source dimension |
| --- | --- | --- |
| Department | Cost Center Code | Cost Center |
| External Labor Pool | Vendor | Vendor |
| Internal Labor Pool | Department Code | Department |
| Labor Allocation Rules | Account Code | Account |
| Role | Labor Role |
| Location | Location |
| Vendor | Vendor |
| Contract Types | Account Code | Account |
| VAT Rates | Location | Location |
| Asset Class | Depreciation Account Code | Account |
| Purchase Account Code |
| Transfer Account Default | Transfer In Account Code | Account |
| Transfer Out Account Code |
| Project | Cost Center Code | Cost Center |
| Parent Code | Project Group |
| Business Unit | Cost Center Code | Cost Center |
| Services | Cost Center Code | Cost Center |
| Parent Code | Service Categories |
| Unit Code | Unit of Measure |

Dimensions with no dependencies include the following:

- Unit of Measure
- Location
- Vendor
- Role

## Configure reference data

|  |  |  |
| --- | --- | --- |
|  | 1. | Navigate to Planning > Configuration > Reference Data. |

|  |  |  |
| --- | --- | --- |
|  | 2. | Click the specific dimension from the correct group. |

The specific dimension details are displayed in a tabular format. Click ![](../../resources/images/icons/icon-options.png) on the right side to view a list of options.
Depending on the type of dimension, the options available and are applicable may vary.

| Option | Details |
| --- | --- |
| Identifiers Template | [Change the identifier for Cost Objects and Dimensions](change-identifier.dita "(Opens in a new tab or window)") |
| Change Identifiers | [Change the identifier for Cost Objects and Dimensions](change-identifier.dita "(Opens in a new tab or window)") |
| Export Template | [Edit and publish reference data tables](edit-publish-reference.dita "(Opens in a new tab or window)") |
| Export | [Edit and publish reference data tables](edit-publish-reference.dita "(Opens in a new tab or window)") |
| Import | [Edit and publish reference data tables](edit-publish-reference.dita "(Opens in a new tab or window)") |
| Publish | [Edit and publish reference data tables](edit-publish-reference.dita "(Opens in a new tab or window)") |
| Revert | [Edit and publish reference data tables](edit-publish-reference.dita "(Opens in a new tab or window)") |
| Import from Cost Transparency | [Integrate with Cost Transparency](integrate-ct.dita "(Opens in a new tab or window)") [Import and publish actuals](import-publish-actuals.dita "(Opens in a new tab or window)") |
| Close Show/Hide Columns | Close the Show/Hide Columns bar |

SEE ALSO:

- [Edit and publish Reference
  Data tables](edit-publish-reference.dita "(Opens in a new tab or window)")
- [Manage Custom reference
  data (dimensions and lists)](manage-custom-reference.dita "(Opens in a new tab or window)")
- [Force a plan to use updated
  reference data](force-plan-use.dita "(Opens in a new tab or window)")
- [Reference
  Table Dependencies Diagram](https://community.apptio.com/docs/DOC-9956 "(Opens in a new tab or window)")
