---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Edit the Company Profile"
breadcrumb: []
source_path: "planning/edit-company-profile.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Edit the Company Profile

The tasks below can only be performed by users assigned to the Admin or Budget Process Owner
roles. For additional information on roles, see Frontdoor permissions and roles.

The Company Profile page allows Admin and Budget Process Owner users to customize the display and
enable features in the application.

1. On the Apptio planning menu, select the Settings button (![](../../resources/images/it%20planning_images/icon_gear.png)), then select Company
   Profile.
2. Enter or edit the information on the Company Profile page, then select Save and
   Exit.

The Company Profile page includes two groups of preferences:

- [Settings](#EdittheCompanyProfile__Settings) - Configure your calendar, currency, permissions, and
  notification settings.
- [Enable Capabilities](#EdittheCompanyProfile__EnableCapabilities) - Configure resources, projects,
  or service features.

## Settings

| Option | Description |
| --- | --- |
| Fiscal Calendar | This option is defined during the setup. Once defined, the it cannot be changed.  Planning applications support custom fiscal calendars, such as the 4-5-4 calendar. To use a custom fiscal calendar, your Apptio customer success manager must set up a new tenant with this capability. You cannot convert an existing tenant from a standard calendar to a custom fiscal calendar.  For more information, see [Enable custom calendars](custom-calendars.htm "(Opens in a new tab or window)"). |
| Currency | Select the currency used by your company. |
| Enable Multi Currency | Select this option to show features for multiple currency support.  For more information, see [Multiple currency support](support-multiple-currencies.htm "(Opens in a new tab or window)"). |
| Show ISO Currency Codes instead of Symbols | Select this option to show currency values with a three-letter ISO currency code instead of a currency symbol.  For more information, see [Multiple currency support.](support-multiple-currencies.htm "(Opens in a new tab or window)") |
| Enforce View Permissions | Select this option if you want Cost Object Owners to view only their Cost Objects, as defined in Cost Object Permissions reference data.  Cost Object Owners are users other than Admins and Budget Process Owners.  For more information, see [Manage Cost Object Permissions reference data](manage-cost-object.htm "(Opens in a new tab or window)").  If this option is not selected, Cost Object Owners can view all other Cost Objects.  Budget Process Owners and Admins can always view all plans regardless of plan state (New, Open or Final). Cost Object Owners can view plans in an Open or Final state.  New Plans  • On (option checked) - Cost Object Owners cannot see new plans.  • Off (option cleared) - Cost Object Owners cannot see new plans.  Open or Final plans  • On (option checked) - Cost Object Owners can only see the Cost Objects they are assigned to as defined in Cost Object Permissions reference data.  • Off (option cleared) - Cost Object Owners can view all Cost Objects in all Open or Final plans. |
| Send Email Notifications for Planning Process Events | Select this option to let Apptio send email notifications for planning process events, such as when a plan is opened, submitted, or returned. This setting has no effect on in-product notifications. Clear this option to test budget and forecast processing using actual Cost Center Owner assignments without generating email notifications. |
| Enable Dashboard and Variance Drivers | Select this option to let Budget Process Owners and Admins see the IT Executive Dashboard view, and to provide all users with access to the Variance Analysis page.  For more information, see [Analyze budget variance](analyze-budget-variance.htm "(Opens in a new tab or window)"). |
| Enable New Expenses Page Experience (Beta) | Select this option to enable the New Expenses view. This feature is available only for customers who are not using PFP or SDP. For more information, see [Enable Apex Line Item Table](enable-apex-line-item-table.htm "(Opens in a new tab or window)")[.](analyze-labor-headcount.htm "(Opens in a new tab or window)") |
| Disable Base Compensation Warning | Select this option to disable the base compensation warning. |
| Disable Group Cost Object Plan Submit | Select this option to hide the Submit Changes option in the Planning > Expenses and Planning > Status pages. |
| Disable Update Reference Data Restrictions | Select this option to remove restrictions on updating reference data within an open plan. Note that these updates can lead to data loss.  For more information, see [Update Reference Data in an Open Plan](update-data-open-plan.htm "(Opens in a new tab or window)"). |
| Enable Integrated Investment Planning | Select this option to enable the Integrated Investment Planning feature and over-allocation feature in Labor Activity tab.  You can only enable Integrated Investment Planning if you don't have Project Financial Planning or Service Demand Planning enabled.  For more information about Integrated Investment Planning feature, see [Get started with the Integrated Investment Planning](iip/gs-integrated-investment-planning.htm "(Opens in a new tab or window)"). |
| Enable Automated Data Management Integration | Select this option to enable the Automated Data Management integration with Cost Transparency. For more information, see [Automated Data Management](adm/adm_overview.htm "(Opens in a new tab or window)"). |
| Upgrade Day | Select the day of the week on which you want to receive product upgrades. |

## Enable Capabilities

The Enable Capabilities group contains multiple collections of settings that vary depending on
the Apptio modules licensed to your organization.

Planning Foundation
:   | Option | Description |
    | --- | --- |
    | Labor Headcount | Select this option to show, clear or hide the labor headcount features.  For more information, see [Labor planning](labor-planning.htm "(Opens in a new tab or window)"). |
    | Headcount Summarization Method | Select how total headcount appears on the Headcount tab of the Summary page KPIs. |
    | Default Labor Start Date | This option lets you specify a default start date to use for new hires. |
    | Labor Summarization | Select this option to show the Summary Options section. In the Summary Options section, select which labor attributes will be displayed on Summary pages.  Selecting fewer options may improve performance when loading Summary pages.  For more information, see [Labor Summarization](labor-summarization.htm "(Opens in a new tab or window)").  Clearing this option may improve performance when viewing line-item tables. |
    | Enable Streamlined Labor Planning Experience | This option simplifies how labor resources and effort (project activity) are shown for projects and departments:  • On the Expenses page, Labor tab, the Existing and Planned sub-tabs are removed. That information is consolidated on the Labor tab, Resources sub-tab in the Existing Labor column.  • On the Expenses page, the Summary tab consolidates the information previously found on the Ledger page.  • If you also enable Labor Activity Planning, other view changes are made to the Ledger and Labor pages (see [Early Access feature: Labor Activity Planning)](labor-activity-planning.htm "(Opens in a new tab or window)").  • If you enabled Project Financial Planning, select Enable Streamlined Labor Planning Experience to include debit and credit lines to the Expense Summary view.  • If you enable Investment Planning, labor resources are shown in a simplified way.  • On Expenses > Labor, the Existing and Planned sub-tabs are removed.  • On the Labor tab. you can show the Is Existing column to view the information previously available in the Existing and Planned sub-tabs.  For more information, see Manage Project Configuration reference data. |
    | Variable Compensation Adjustment | Note: This option will also enable the 'Enable New Expenses Page Experience' setting, since variable compensation adjustment is supported only in New View.  Select this checkbox to enable the variable compensation adjustment in Labor Planning.  For more information, see [Setting up variable labor compensation](https://help.apptio.com/en-us/it-planning/planning/plan-labor-compensation.htm "(Opens in a new tab or window)"). |
    |  |  |
    | Labor Activity | NOTICE: Labor Activity checkbox will be visible under Company Profile only if “Enable Integrated Investment Planning” checkbox is enabled. Disabling Integrated Investment Planning feature will automatically hide the Labor Activity checkbox from the company profile and hide Labor Activity tab on the Expenses page. Select/unselect this checkbox to enable/disable the [Labor Activity](iip/enable-disable-labor-activity.htm "(Opens in a new tab or window)") tab on the Expenses page.  Select this option to allow or prevent overallocation.  For more information about Integrated Investment Planning feature, see [Get started with the Integrated Investment Planning](iip/gs-integrated-investment-planning.htm "(Opens in a new tab or window)"). |
    | Contracts | This option lets you show or hide contract planning features.  For more information, see [Manage contracts](manage-contracts.htm "(Opens in a new tab or window)"). |
    | Auto-Update Contract Total | With the Contracts option selected you can select the Auto-Update Contract Total option which automatically updates your contract total. |
    | Include Value-Added Tax (VAT) | Select this option if you need to account for Value-Added Tax (VAT) values. When enabled, the Apptio planning applications will add a VAT Rates table in reference data and will generate VAT values in OpEx and CapEx line items for contracts.  For more information, see [Manage Contract reference data](manage-contract-configuration.htm "(Opens in a new tab or window)"). NOTICE Once VAT is enabled in a Company Profile, it cannot be disabled. |
    | Assets | Select this option to show or hide asset planning features.  For more information, see [Manage assets](manage-assets.htm "(Opens in a new tab or window)"). |
    | Summarize financial actuals down to the following dimensions and/or attributes | Select the dimensions and attributes to be used to summarize general ledger actuals to align with a forecast plan's items.  For more information, see [Create a budget plan or forecast.](create-budget-plan.htm "(Opens in a new tab or window)") |

Labor Effort Planning
:   | Option | Description |
    | --- | --- |
    | Labor Units of Measure | Select how you want to measure labor; hours, sprints, or phases.  Labor units of measure are for display purposes only. |
    | Labor Units Per Month | Enter the number of units of the defined measurement in a single month. |
    | Generate costs in actual periods (when actual volumes are entered or imported) | Select this option to enable actual cost for labor volumes to be calculated like planned cost (Rate x Volume). To avoid double counting, clear this option if you include these costs when managing spend.  For more information, see [Import and publish actuals](import-publish-actuals.htm "(Opens in a new tab or window)"). |
    | Enable Labor Activity Planning (EA) | If you have enabled Project Financial Planning, select this option to also enable the Labor Activity Planning Early Access (EA) features.  For more information, see [Early Access feature: Labor Activity Planning](labor-activity-planning.htm "(Opens in a new tab or window)").  Note that enabling Labor Activity Planning also enables Streamlined Labor Planning Experience. |

Project Financial Planning
:   | Option | Description |
    | --- | --- |
    | Projects | Select this option to enable functionality provided by the Project Financial Planning module. This option is available if Project Financial Planning is licensed. |
    | Show Project Labor Tab | Select this option to show the project labor tab. |
    | Investment Planning | Select this option to enable investment planning functionality in Project Financial Planning.  Enabling Invest ment Planning can slow down system performance. For strategies to mitigate slower system performance, see [Best practices: Investment planning in Project Financial Planning](pfp/bp-investment-planning.htm "(Opens in a new tab or window)"). |
    | Enable Project Auto-Scoring | Select this option to enable an automatic calculation of the score value per project.  For more information, see [Add projects and initiatives to your portfolio](pfp/add-projects-initiatives.htm "(Opens in a new tab or window)") and [Project Configuration reference data](pfp/manage-project-configuration.htm "(Opens in a new tab or window)") [pfp/manage-project-configuration.htm](pfp/manage-project-configuration.htm "(Opens in a new tab or window)"). |
    | Interest Rate (%) | Enter the default value used in return on investment (ROI) calculations. |
    | Estimated Internal Labor Rate (USD per Labor Unit) | Enter your default internal labor rate.  You can override this rate when you add a project. |
    | Estimated External Labor Rate (USD per Labor Unit) | Enter your default external labor rate.  You can override this rate when you add a project. |
    | Project Prefix | Enter a project prefix. |

Service Demand Planning
:   | Option | Description |
    | --- | --- |
    | Services | Select this option to enable functionality provided by Service Demand Planning. This option is available if Service Demand Planning is licensed. |
    | Pricing Model | Choose how to price your service out of one of the following:  • Dynamic - Calculates the unit price based on the service's cost composition and demand.  • Tiered - Applies a price adjustment based on two areas, allowing users to specify the prices directly rather than using a surcharge-based approach.  Use Tiered pricing to define Internal and External prices.  • Region-Based - Applies a price adjustment to your base unit price that differs based upon the location of the service consumer. |
    | Base Price Label | Determine the default price group for Tiered pricing.  For more information, see [Service reference data](sdp/manage-service-reference.htm "(Opens in a new tab or window)").  Enter Internal to determine external groups in reference data. |
    | Generate costs in actual periods (when actual volumes are entered or imported) | Select this option to enable actual cost for service volumes to be calculated like planned cost (rate x volume). To avoid double counting, clear this option if you include these costs in Spend Management.  For more information, see [Import and publish actuals](import-publish-actuals.htm "(Opens in a new tab or window)"). |
