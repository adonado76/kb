---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "TBM Studio"
breadcrumb:
  - "TBM Studio"
source_path: "SSWRJM/studio/home.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# TBM Studio

## Release Notes

- Recent releases
- 2025 Release Notes
- 2024 Release Notes

## Getting Started

- What is TBM Studio?
- Core Concepts
- Quick Start Guide
- UI Overview Main Navigation Areas Environments Working with Documents Keyboard Shortcuts Customization Options
- Conversational Insights

## Learning Paths (Role-Based)

- Learning Paths for Business Analysts
- Learning Paths for IT Finance Teams
- Learning Paths for Administrators
- Learning Paths for Developers
- Next Steps for All Roles

## How-to Guides (Task-Based)

- Work with Data Data Import & Management Upload Data from Files (Excel, CSV) Connect to External Data Sources (DataLink) Version Tables for Monthly Data Transform & Enrich Data Clean and map data using Map Columns Join data from multiple sources \\ Apply formulas to transform data Filter data by date partition Append multiple data sources Manual Data Entry Create Blank Editable Tables Create Enriched Editable Tables Configure Dropdowns and Validation Set Up Editable Table Publishing Data Security How-To Guide 1: Apply Row-Level Security to Tables Apply row-level security How-To Guide 2: Control Access with User Mapping Best Practices for Row-Level Security Data Export How-To Guide: Configure Published Tables How-To Guide: Export Data via API
- Build Cost Models Model Basics Add a Table to the Model Understand Model Metrics (Cost, Budget, Forecast) View the Model Diagram Create Allocations Set Up Simple Allocations (One-to-One) Configure Drivers for Allocations Create Multi-Tier Allocations Handle Unallocated Costs Allocation Troubleshooting Reference Advanced Modeling Use Matching Logic for Allocations Configure Weighting Columns Trace Cost Flows Through the Model Create Model Reports (Sankey Diagrams)
- Create Reports Report Basics Create a Basic Report Add Tables to Reports Add Charts and Visualizations Use Slicers for Interactive Filtering Putting It All Together: Your First Report Report Customization Create Custom Perspectives Build Report Collections Design Master Reports (Templates) Configure Report Permissions Summary Advanced Reporting Create Drill-Through Reports Add Editable Components to Reports Configure Dynamic Sizing and Positioning Export and Print Reports Email Subscription IBM Apptio Report Migration Assistant Guide
- Manage Users and Permissions User Management Create and Manage Users Assign Roles to Users Configure Custom Roles Access Control Decision Guide: Choosing the Right Access Control Set Report Permissions by Role Implement Row-Level Security for User Access Configure Editable Table Permissions
- Integrate and Extend API Integration How-To: Authenticate with the API How-To: Upload Data via API Uploader Service API How-To: Download Data via API How-To: Handle API Errors Quick Reference Scripting How-To Guide: Write ApptioScript Formulas How-To Guide: Use Common Script Patterns
- IBM Apptio Report Studio (New) Release Notes Recent Releases Previous Releases Getting Started New Report Studio Overview How the New Report Studio Works A Guide to New Report Studio’s Navigation User Roles & Permissions Quick Start Create Your First Report Create Your First Report Collection Core Concepts Custom Formulas Drill Navigation Working with Reports Report Lifecycle Report Canvas Theme Engine Labels Components Components Overview Slicer Hierarchical Slicer Column Picker Quick Pivot HTML Group Tabs Tab Visibility Rules Button Component Visualizations Visualizations Overview KPI Table Table Column Overflow Menu Renaming Columns in Table Hiding Intermediate Dimensions Show Values Tree View Export a Table to Excel Editable Table Bar Charts Column Charts Line Charts Pie Charts Column + Line (Overlay) Charts Heatmaps Bubble Charts Report Viewer Report Viewer Overview Export Report to PDF Email Report Saved Views Admin Control for New Report Viewer Access Configuration and Customization Steps to Enable Modernized OOTB (NX) Reports in Client Instance Troubleshooting & FAQs

## Concepts and Architecture

- TBM Fundementals Introduction to Technology Business Management The TBM Taxonomy Common TBM Use Cases Cost Allocation Methodologies TBM Maturity Model
- Data Architecture Data Architecture Data Flow Overview Tables and Table Types Transform Tables Editable Tables How Editable Tables Fit in the Data Flow Published Tables Table Type Decision Matrix Transform Pipeline Concepts Versioning and Time Periods Data Freshness and Validation Data Integration Patterns
- Model Architecture Model Concepts Overview Model Objects and Relationships Metrics: Modeled vs. Calculated The Allocation Engine Allocation Order and Processing Unallocated Costs Model Validation and Tracing
- Security Model Security Architecture Overview Authentication and Identity Role-Based Access Control (RBAC) How RBAC Works Default Roles Custom Roles Permission Inheritance and Effective Permissions Row-Level Security (RLS) How RLS Works RLS Architecture RLS Scope: Where RLS Applies RLS Inheritance and Flow Report and Component Permissions Component-Level Visibility Editable Table Permissions Table Upload Component Permissions How Report Permissions and RLS Interact Security Best Practices Security Design Patterns Security Testing and Validation Security Across the Lifecycle Staging Environment Security Production Environment Security Security and the Check-In/Check-Out Workflow
- Build and Deployment Lifecycle Build & Deployment Lifecycle Understanding the Three Environments Check-Out and Check-In Workflow Build and Calculation Process Promotion Workflow Rollback and Recovery Branches and Hotfixes Integration with Other Workflows What to Learn Next

## Reference

- Data Studio Reference Tables Creating Tables Table Source Options Data Refresh Cycles Table Column Types Transform Steps Adding Transform Steps Complete Transform Step Reference Formulas Quick Reference Published Tables DataLink Connections Data Workspace Interface Table Operations Error Handling Enhanced Excel Parsing
- Model Studio Reference Model Objects Model Object Properties Object Relationships and Dependencies Object Naming Conventions Drivers Driver Configuration Options Driver Data Requirements Driver Validation Rules Deleting a Driver Allocations All Allocation Configuration Options Allocation Order and Precedence Allocation Calculation Behavior Model Metrics Metric Classification Metric Properties Metric Aggregation Rules Custom Metric Creation Model Diagrams Sankey Diagram Concepts Diagram Navigation Diagram Customization Options Export and Sharing Model Reports Model Report Types Visualization Options Report Parameters Common Issues
- Report Studio Reference Report Studio Reference Report Components: Tables Table Structure Configuration Column Configuration Data Display Options Sorting Options Filtering Options Calendar-Based Columns Sparklines and Status Indicators Table Properties Table Behavior Performance Considerations Report Components: Charts Bar Charts Column Charts Line Charts Pie and Donut Charts Trend Charts Waterfall Charts Tree Maps Radar Charts Overlay (Combination) Charts Common Chart Properties Color Configuration Navigation and Drill-Through Chart Interactivity Features Chart Selection Guide Axis Labels and Formatting Legacy Charts vs. Ad Hoc Charts Report Components: Filters and Slicers Filter and Slicer Component Types Data Binding Configuration Filter Behavior Filter Scope Hierarchical and Cascading Filters Time Period Filtering Filter Performance Considerations Common Filter Patterns Troubleshooting Report Components: Navigation Navigation Component Types Drill-Through Configuration Conditional Navigation Hierarchical Slicers for Drill-Down Navigation Styling Navigation Best Practices Report Components - Input Components Input Component Types Data Binding Validation Input Behavior Permissions Common Use Cases Report Components: Editable Tables in Reports Editable Table Configuration Column Editing Options Validation Configuration Row Operations Save Behavior Edit Permissions Styling Editable Tables Editable Table + Report Integration Common Patterns Troubleshooting Report Properties Time Period Configuration Display Settings Active and Preload Settings Master Report Setting Security Settings Print and Export Settings Email Subscription Settings Breakdown and Advanced Display Options Localization Settings Layout Options Screen Size Options Component Positioning Component Sizing Container Components Print Layout Configuration Master Reports Layout Best Practices Master Reports Master Report Concepts Creating Master Reports Master Report Content Inheritance Applying and Removing Master Reports Master Report Best Practices Multi-Level Masters Troubleshooting Master Reports Report Collections Collection Concepts Creating Collections Adding Reports to Collections Collection Navigation Collection Settings Collection Permissions Collection Organization Report Permissions Permission Model Architecture Permission Types Permission Assignment Row-Level Security in Reports Component-Level Permissions Permission Best Practices Troubleshooting Permission Issues
- Formulas and Functions Introduction to formulas and functions Syntax for formulas and functions Data lookup Referencing column names Operators String concatenation Updated eval formulas Functions: Annotated list Functions - Where used matrix Annotated list of functions by type Abs function Annual function Annualize function Average function Bullet function CapFirstLetter function ColumnExists function ConvertCurrencyFromBase ConvertCurrencyToBase CopyTable function Currency function CurrentDate function DateFormat function DateSum function Days function DomainName function DurationOfMonth function DynamicColumn function Elapsed function Eval function EvalWiki function Find function GetGroupbyColumn function GetInfo function GetLastFilterColumn function GetLastFilterValue function GetLastPublishTime function GetNextPublishTime function GetReportName function GetReportPath function GetTimeOffset function Hours function Icon function If function IPLookup function IsNumeric function Key function Large function LargeIf function Left function Len function Lookup function Lookup_Wild functions LookupContains LookupEx function LookupFromEditable LookupFromPath function LookupMetric function LookupObjectTotalAllocated function LookupObjectTotalValue function LookupObjectUnitAllocated function LookupObjectUnitValue function Lower function Max function Mid function Min function Minutes function Mod function Months function Now function NumberFormat function ObjectName function Percentile function Period function PeriodsInHalf function PeriodsInQuarter function PeriodsInYear function Plural function Pluralize function Power function PreviousMonth function PreviousYear function ProjectExists function ProjectName function Quarter function QuarterToDate function Rand function Ratio function Recurring Publish function Replace function ReplaceRegex function Right function Round function Row function RowCount function RowCount_EditableTable function Search function SLN function Small function SmallAcrossTime function SmallIf function Sparkline function Split function SplitEx function StatusIcon function Substitute function Sum function SumIf function SumIfHierarchy function TableInfo function TableMatch function TimePeriod function Trim function Trunc function Undrill function UniqueCount function UniqueValues function Untag function Upper function Use_Map_Grid function Use_Map_Table function Value function YearToDate function

## Administration

- Project Administration Configure multi-currency
- User Management
- Security & Compliance
- Performance & Optimization
- ApptioOne Precision
- Build & Deployment

## Troubleshooting and Support

- Introduction
- Common Issues and Solutions Data Studio Issues Model Studio Issues Report Studio Issues Build and Deployment Issues
- Error Messages Explained Configuration Recommendations Numeric Grouping Recommendations Unused Resource Recommendations
- Diagnostic Tools
- Getting Help
