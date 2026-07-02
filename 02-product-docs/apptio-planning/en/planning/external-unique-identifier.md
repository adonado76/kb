---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "External Unique Identifier"
breadcrumb: []
source_path: "planning/external-unique-identifier.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# External Unique Identifier

## Background

Budget planners want to refresh various types of expense data in a plan with the updated data
coming from the sources data systems. E.g., the labor headcount data in a plan can be updated on a
regular interval using the actual labor headcount from the HR tools such as Workday, Oracle, ADP
etc. To achieve it, customers bring the data from these source systems into ApptioOne TBM Studio,
run the data transforms on the source data and create a dataset that can then be imported into a
Labor Plan in the ApptioOne Planning. Using Replace All Data option for the
data import to update the plan labor data might lead to losing some of the labor lines that are
available only in the plan but not in the source HR systems e.g., headcount plan created for some
planned investment in future, role-based labor headcount projections for the future years etc. The
preferred approach in such a case it to use Update Data option. However,
there is challenge to execute it, because there is no common unique identifier between the existing
labor data in the plan and the updated data coming from the source HR systems, that can be used as a
key to match the lines between two systems. Both Apptio and source data systems will have the unique
data identifier within their own boundaries. For example, Apptio creates Line Item Code as unique
identifier for each expense line and the source HR system might be maintaining Employee Id as a
unique identifier for the labor data. But for the data update to work seamlessly between the two
systems, we need a common unique identifier.

External Code feature solves this need. By enabling External Code feature users will be able to
define unique external code for each expense line that can be used as a key attribute to update the
existing plan data.

## How to enable External Code feature?

To enable the External Code feature,

1. Navigate to Company Profile > Settings.
2. Enable the checkbox against Enable External Code
3. Click on Save and Exit

   ![](../../resources/images/it%20planning_images/eui-5.png)

## What is the user interface changes after enabling the feature?

1. A new column External Code gets added on Labor, Contracts, Assets, Other
   and Labor Activity tab. The column is hidden by default, but user can show it on the expenses
   view.

   ![](../../resources/images/it%20planning_images/eui-4.png)
2. Summary tab shows two new columns Source External Code and
   External Code.

   ![](../../resources/images/it%20planning_images/eui-3.png)
3. User can rename the External Code column name using Configuration >
   Schema.

   ![](../../resources/images/it%20planning_images/eui-2.png)
4. It is also possible to make External Code column mandatory for data
   entry.

## User Permissions Required

- Edit access on External Code column is available to only those users, that have
  canEditExternalCode frontdoor permission.
- Admin user role already has canEditExternalCode permission. For other
  user roles, this permission needs to be added as per your requirements.

Customers may want to restrict users from editing external code or adding new lines with external
code value which is not true unique identifier as per their source data systems. So, the permissions
to add/edit should be restricted in that case. The way to achieve it is by setting up above
mentioned permissions.

## How does it works?

1. Users having edit permission can enter values in the external code column from the UI or they
   can also import values into external code column using a .csv file import into expenses page.
2. There is validation built to ensure no two lines of same expense type should have the same
   external code in the given plan.
3. Duplicating a row, ignores the External Code value.
4. Existing external code values get copied over to the new plan when the new plan is created using
   Plan Baseline from existing plan.

## External Codes in the Event Log

External Codes can be tracked in the Change history in the Event Log. If a line item has a
External Code, it is displayed in the event’s Details column.

![](../../resources/images/it%20planning_images/eui-1.png)

## Source External Code

The Source External Code is a code that points to where the line item came from. Planning only
assigns a Source External Code if a line item has been created from another source. For example,
generated financial (depreciation and amortization) lines in the Summary tab originating from the
contract and asset lines.

If you have [enabled Labor Summarization](https://help.apptio.com/en-us/it-planning/planning/edit-company-profile.htm#EnableCapabilities "(Opens in a new tab or window)"), then the Source External Code may
display "varies" for line items originating from the Labor tab. This is because due to summarization
a single line in the Summary tab might be representing multiple source lines in the labor tab, so it
is not possible to map the source external code in the Summary tab to a specific external code in
the labor tab.

For more information on labor summarization, see [Labor Summarization](labor-summarization.htm "(Opens in a new tab or window)").

## How does it work when there is both Line Item Code and External Code on the line items in the imported file?

When importing data from a file, user can select either Replace All Data option or Update Data
option. Please find below designed behavior for both the use cases.

Replace All Data – If this option is selected when importing the data, all
the existing lines in the selected expenses tab is deleted and the data from the .csv file is
imported. This option doesn’t check lines in the plan against lines in the .csv file for either
matching line item code or matching external code.

Update Data – File upload using this option evaluates the line item match
between plan and the uploaded file for both line item code and external code. Examples below will be
easier to understand the update functionality. Consider existing data in the plan as below. For
simplicity only Line Item Code, External Code and Vendor columns are considered.

Upload Case #1
:   Line Item Code takes precedence over the External Code if both are present. If missing Line Item
    Code, External Code is used for update.

    Existing Data

    | Line Item Code | External Code | Vendor |
    | --- | --- | --- |
    | F-1 | E003 | vendor1 |
    | F-2 | E005 | vendor2 |
    | F-3 | E007 | vendor3 |
    | F-4 | E009 | vendor4 |

    Data for Upload

    | Line Item Code | External Code | Vendor |
    | --- | --- | --- |
    | F-1 | E003 | vendor5 |
    |  | E005 | vendor6 |
    | F-3 | E007 | vendor7 |

    Upload Result

    | Line Item Code | External Code | Vendor |
    | --- | --- | --- |
    | F-1 | E003 | vendor5 |
    | F-2 | E005 | vendor6 |
    | F-3 | E007 | vendor7 |
    | F-4 | E009 | vendor4 |

Upload Case #2
:   In case Line-Item Code is a match between existing lines and imported lines but External Code is
    different, the operation is treated as an update to the External Code.

    Existing Data

    | Line Item Code | External Code | Vendor |
    | --- | --- | --- |
    | F-1 | E003 | vendor1 |
    | F-2 | E005 | vendor2 |
    | F-3 | E007 | vendor3 |

    Data for Upload

    | Line Item Code | External Code | Vendor |
    | --- | --- | --- |
    | F-2 | E008 | vendor7 |
    | F-3 |  | vendor3 |

    Upload Result

    | Line Item Code | External Code | Vendor |
    | --- | --- | --- |
    | F-1 | E003 | vendor1 |
    | F-2 | E008 | vendor7 |
    | F-3 |  | vendor3 |

Upload Case #3
:   Update External Code that already exists.

    Existing Data

    | Line Item Code | External Code | Vendor |
    | --- | --- | --- |
    | F-1 | E003 | vendor1 |
    | F-2 | E005 | vendor2 |
    | F-3 | E007 | vendor3 |

    Data for Upload

    | Line Item Code | External Code | Vendor |
    | --- | --- | --- |
    | F-4 | E007 | d5 |

    Upload Result

    Upload is cancelled with "Duplicate Value" error.

Upload Case #4
:   Update with invalid Line Item Code but valid External Code.

    Existing Data

    | Line Item Code | External Code | Vendor |
    | --- | --- | --- |
    | F-1 | E003 | vendor1 |
    | F-2 | E005 | vendor2 |
    | F-3 | E007 | vendor3 |

    Data for Upload

    | Line Item Code | External Code | Vendor |
    | --- | --- | --- |
    | LM-XY-10 | E007 | vendor9 |

    Upload Result

    | Line Item Code | External Code | Vendor |
    | --- | --- | --- |
    | F-1 | E003 | vendor1 |
    | F-2 | E005 | vendor2 |
    | F-3 | E007 | vendor9 |

Upload Case #5
:   Upload creates new line items, no lines to update.

    Existing Data

    | Line Item Code | External Code | Vendor |
    | --- | --- | --- |
    | F-1 | E003 | vendor1 |
    | F-2 | E005 | vendor2 |
    | F-3 | E007 | vendor3 |

    Data for Upload

    | Line Item Code | External Code | Vendor |
    | --- | --- | --- |
    |  | E011 | vendor5 |

    Upload Result

    | Line Item Code | External Code | Vendor |
    | --- | --- | --- |
    | F-1 | E003 | vendor1 |
    | F-2 | E005 | vendor2 |
    | F-3 | E007 | vendor3 |
    | F-4 | E011 | vendor5 |

Upload Case #6
:   Duplicate External Code within the upload data.

    Existing Data

    | Line Item Code | External Code | Vendor |
    | --- | --- | --- |
    | F-1 | E003 | vendor1 |
    | F-2 | E005 | vendor2 |
    | F-3 | E007 | vendor3 |

    Data for Upload

    | Line Item Code | External Code | Vendor |
    | --- | --- | --- |
    |  | E011 | d5 |
    | F-5 | E011 | d6 |

    Upload Result

    Upload is cancelled with "Duplicate Value" error.

## Is it difficult to use External Code feature, especially after reviewing the upload validations mentioned above?

No. We recommend users to follow approach mentioned below to avoid any unexpected changes.

1. Always use Update Data option when importing the data, unless it is
   absolutely necessary to use Replace All Data option.
2. If you are refreshing the existing plan data with the data from external source systems that do
   not know the Line Item Codes. We recommend to leave the Line Item Code values blank in your import,
   so that the uploads will be done only based on the External Code values.
   1. If your uploaded data if there are any new lines, those will get added. Apptio will generate new
      line item codes for the new lines and the external code provided by you will be also present on
      these lines after the import.
   2. If there are edits to lines that are already present in the plan, those lines will be matched
      using External Code only and the changes will be applied.
   3. However, if there are any deletes in your refreshed data, we recommend you to do those deletes
      either from the UI or using .csv upload in the individual cost objects, since the Update Data
      operation is not going to perform delete.
