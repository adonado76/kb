---
source_system: "apptio-costing-essentials"
practice: "tbm"
language: "en"
doc_type: "apptio-cost-management"
title: "Key Concepts & Terminologies"
breadcrumb:
  - "Costing Essentials"
  - "Getting started"
source_path: "apptio-cost-management/getting_started/acm-glossary.html"
images: []
capability_ids: []
last_updated: "2026-02-27"
summary: ""
---
# Key Concepts & Terminologies

| Fields | Description |
| --- | --- |
| Allocation Weighting | Percentage of spend in source object that is allocated to destination objects  Maybe 100% allocation (insert ‘1’), or split across multiple Solution Types/Categories |
| Account | The Account from the general ledger that is used to collect and store amounts. Account is the identification code used in the GL. |
| Account Description | The name of the account from the general ledger. |
| Account Group | The first-level, hierarchical grouping of accounts in the general ledger Account classification/grouping to be used in reporting. This needs to be manually added to ITP so that the CT reports are populated |
| Account Subgroup | The second-level, hierarchical grouping of accounts in the general ledger. Out of box, Apptio supports three tiers: Account Group, Account Sub-Group, Account |
| Allocation Methods | Allocations method include  Direct Allocation  For allocation between one Source and one target  Weighting should default to 1 and should only have one row.  Percent Split  For weighted Percentage based allocations  should have 2 or more rows with relative weighting assigned.  Volume Split  For allocations based on Volume/Quantity attributes (eg Count of Application licenses  Should have 2 or more rows with volumes assigned.  Weighted Estimated Usage  enables % Headcount Usage and User Weighting columns  should have 2 or more rows. |
| AP Transaction ID | A unique identifier for an individual line item in the Accounts Payable data set. |
| AP Transaction Description | The description of this Accounts Payable ID line entry. |
| Backfill | Is the open headcount to replace an existing employee or contractor |
| Business Relationship  Manager | The primary IT account manager responsible for a specific business unit. |
| Business Unit | A logical element or segment of a company (such as accounting, production, marketing) representing a specific business function, and a definite place on the organizational chart, under the domain of a manager.  In Apptio's definition, Business Unit is Level 1 in the organization hierarchy and Department is Level 2 org hierarchy. |
| Business Unit Type | A categorization of whether the BU (or department) is revenue generating or not.  Apptio Recommended values include: "Revenue Generating", "Non-Revenue Generating". |
| Compensation | The total compensation for the employee.  For example: May include Superannuation + Bonus in addition to base salary |
| Contract Amount | The agreed upon amount to be paid for the services delivered in the contract. |
| Contract Description | A brief description of the contract. |
| Contract Notify Days | The lead time (in days) that notification must be provided to a vendor around contract non-renewal or change requests. |
| Contract Automatic Renewal | Designates whether a contract auto renews. |
| Contract Number | The number assigned to the contract by the business. |
| Contract Owner | The name of the person responsible for the contract. |
| Contract Renewal Plans | Designates the plan for the future of the contract. Valid values: Competitive RFP, Extend as is, Move in-house, Move to other vendor, No longer needed, Renegotiate terms |
| Contract Title | The title of the contract. |
| Contract Term | The duration in days between the contract start and end date. |
| Cost Center/Cost Center Code | A Cost Center is the department or "subunit" of a company that is responsible for its costs. Cost Center is the identification code used in the GL and subledgers.  Cost Center refer to both department that incurred the original expense (e.g IT cost Center) and those who will be charged for consumer IT Services (Business cost center) |
| Cost Center Name | The name of the Cost Center associated with the Cost Center code. |
| Cost Pool and Cost Sub Pool | ATUM provides an industry standard Taxonomy to categorize expenses, that readily identify the purpose of expenses and aids comparative analysis to industry benchmarks.  Refer to TBM Framework & Taxonomy and the Cost Pool Taxonomy sheet in ATUM V4.0 spreadsheet for full definition of ATUM Cost Pools and Cost Sub pools |
| Depreciation Amount | The amount the asset is depreciated each period. |
| Delivery | Sourcing of the vendor service/solution offering; typically: "On Prem"; "Private Cloud", or "Public Cloud" |
| Employee Type | Categorizes Labour resources as either  **Internal**: Salaried resources considered part of IDPs Headcount/FTE  **External**: Staff Augmentation including Individual Contractors (proprietors) and Recruitment firms |
| Expense Type | Designates a of expenditure as OpEx or Capex |
| Fixed Asset Ledger ID | A user-defined unique identifier for the Fixed Asset Ledger |
| Fixed Asset Number | The asset number or ID of the asset |
| Govrning Body | Governing Body Owner represents a higher level organizational structure than the Business Unit. This may be used to distinguish between different operating entities or perhaps different international structures within the Company. |
| Investment Objective | forward looking investment strategy for the application/service Used to prioritize application/service resources and investments for new and existing applications/services that are aligned to  business' imperatives and objectives. |
| Is CSP | (Is this a Cloud Service Provider)  Designates of Vendor provides Cloud IaaS or PaaS Service (e.g. Cloud Compute, Cloud Storage) services to IDP  Core CSP Vendors supported OOTB are Amazon/AWS, Microsoft/Azure, Google/GCP, Oracle/OCI  ACM can automatically ingest Billing data from CSP Vendors, automatically map and allocate billed resources to Service Offerings in ACM |
| Journal ID | The Journal Identification code for the transaction or journal entry. The journal entry contains the date, the account name and amount to be debited or credited in the General Ledger. |
| Labor ID | A user-defined unique identifier for the Labor data set |
| Labor Role | The employees primary role within the technology organization. |
| Life Cycle Stage | The current state of the Application/Business Service.  Apptio recommended values include: In Development, In Service, Retired. |
| Organization ID | Unique Identifier for each Consumer (Business Unit)  Select from a Consumer list, ingested into ACM from IDP’s Organizational master data source, and enriched in ACM via the Organization Mapping workbench |
| Parent Contract | The parent contract of the current contract used to roll-up contract spend for larger contracts with sub-contracts. |
| PO Number | A number that identifies a purchase order associated with this Accounts Payable line entry. |
| PO Rate | The purchase order rate for the external contractor role. |
| Project Approved Budget | The amount of capital and operating expenditure approved for a specific project. This number reflects the latest total approved project budget for the year and may differ from the original / baseline project budget. |
| Project Business Initiative | The specific business initiative as defined by the company to which the project is aligned. This is used to determine the number of projects and IT investments being made against the various business initiatives to determine if the investments align with the company's strategy and key initiatives. |
| Project Business Sponsor | The primary business person who is sponsoring or requesting the specific project. |
| Project Business Sponsor Unit | The name of the business unit that is the primary sponsor of the project. May be IT or LOB depending on the type of project (e.g. infrastructure project vs. LOB project). |
| Project Id | The project or investment Unique identifier as defined by the project portfolio or investment management system.    Select from Project list, ingested into ACM from IDP’s Project Portfolio Management (PPM) system of record, and enriched in ACM via the Project Mapping workbench |
| Project Managers | The primary project manager responsible for the planning and execution of the project from a project management disciple perspective. |
| Project Name | The unique name for the project or investment. |
| Purchase Order Number | The number that identifies a purchase order associated with this Accounts Payable line entry. |
| Project Program | Program refers to a group of related projects or investments. |
| Project Portfolio | The grouping of related investments into a "portfolio". Refers to  the specific portfolio the project or investment belongs to. |
| Project Spend Type | The investment categorization of the IT expenditure or budget. Valid values are typically either Run/Change the Business (RTB, CTB)or Run/Grow/Transform the Business (RTB, GTB, TTB). |
| Reason Planned | The reason for the open headcount. |
| Req Number | The requisition number for the approved headcount position. |
| Salary Band | The salary band used for weighted cost allocations in the cost model. |
| Solution Offering ID | The unique identifier for the name of the Offering.    Select from values in the IDP Service Catalogue ingested into ACM, and enriched in ACM via the Solution Mapping workbench |
| Solution Category | Meta data that categorizes and organizes Services Offerings within your Service Catalogue  Level One of the TBM solution layer taxonomy.  Select from values in the IDP Service Catalogue ingested into ACM, and enriched in ACM via the Solution Mapping workbench |
| Solution IT Owner | The primary IT person responsible for the development and support of the specific offering. |
| Solution Offering Type | Identifies if the offering is referred to as an application, product, or service depending upon the IT operating model. |
| Solution Type | Meta data that categorizes and organizes Services Offerings within your Service Catalogue  Level Two of the TBM solution layer taxonomy.  Select from values in the IDP Service Catalogue ingested into ACM, and enriched in ACM via the Solution Mapping workbench |
| User Interaction | A categorization of the primary consumer of the product and service as it relates to the direct delivery and interaction with the vendor. Recommended values include: Business Facing (e.g. business users within the company), Customer Facing (e.g. the company's customers), Internal Facing (e.g. internal within the IT  organization) |
| Vendor Category | A high-level categorization of the function that the vendor provides.  Can enable richer analysis of Vendor spend. For example: Compare Spend for Vendors in the same category |
| Vendor ID | The Vendor ID used system to track the company providing the product or service    Unique Identifier for each Vendor  Selected from a Vendor list, ingested into ACM from IDP’s Vendor system of record, and enriched in ACM via the Vendor Mapping workbench  The Vendor list does not include all Vendors, but those who represent the majority of your Annual spend (eg. 80%).  Vendor list will not include Vendors who provide Staff Augmentation services, as these expenses are considered  (External) Labour expenses |
| Vendor Manager | The name of the person primarily responsible for managing the vendor relationship. May be a formal procurement / vendor manager or the IT manager who has contracted the products or services from the vendor. |
| Vendor Primary Service | A classification of the primary type of product or service the vendor provides.    Can enable richer analysis of Vendor spend. For example: Compare Spend for Vendor providing the same services/ performing the same function |
| Vendor Type | A classification of vendors to provide appropriate management and oversight to optimize pricing and risk. Recommended categories are: Strategic, Preferred and Transactional    Recommended categories are: Strategic, Preferred, Transactional and Legacy. |
| Weighting | Refer to Allocation Weighting |
