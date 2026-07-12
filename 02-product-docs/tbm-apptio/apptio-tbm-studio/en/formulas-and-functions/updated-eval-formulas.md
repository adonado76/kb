---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Updated Eval Formulas"
breadcrumb: []
source_path: "formulas-and-functions/updated-eval-formulas.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Updated Eval Formulas

## In Business Unit Review report

BU Run updated from
Cost+CapEx-eval("If(IsComponentInstalled(""Projects""),Optional(Project Investments,0),Optional(App
Dev,0))") to

Cost+CapEx-If(IsComponentInstalled("Projects"),Optional(Project Investments,0),Optional(App
Dev,0))

BU Investments updated from eval("If(IsComponentInstalled(""Projects""),Optional(Project
Investments,0),Optional(App Dev,0))") to

If(IsComponentInstalled("Projects"),Optional(Project Investments,0),Optional(App Dev,0))

% Direct BU Costs updated from eval("If(IsComponentInstalled(""Business
Services""),LookupObjectUnitValue(Service Allocations Direct,Cost,Business Unit Allocation Master
Data.Business Unit,Service Allocations Direct Master Data.Business
Unit)/LookupObjectUnitValue(Business Unit Allocation,Cost,Business Unit Allocation Master
Data.Business Unit,Business Unit Allocation Master Data.Business
Unit),LookupObjectUnitValue(Applications,Cost,Business Unit Allocation Master Data.Business
Unit,Applications Master Data.Business Unit ID)/LookupObjectUnitValue(Business Unit
Allocation,Cost,Business Unit Allocation Master Data.Business Unit,Business Unit Allocation Master
Data.Business Unit))") to

If(IsComponentInstalled("Business Services"),LookupObjectUnitValue(Service Allocations
Direct,Cost,Business Unit Allocation Master Data.Business Unit,Service Allocations Direct Master
Data.Business Unit)/LookupObjectUnitValue(Business Unit Allocation,Cost,Business Unit Allocation
Master Data.Business Unit,Business Unit Allocation Master Data.Business
Unit),LookupObjectUnitValue(Applications,Cost,Business Unit Allocation Master Data.Business
Unit,Applications Master Data.Business Unit ID)/LookupObjectUnitValue(Business Unit
Allocation,Cost,Business Unit Allocation Master Data.Business Unit,Business Unit Allocation Master
Data.Business Unit))

% Indirect BU Costs updated from eval("If(IsComponentInstalled(""Business
Services""),(LookupObjectUnitValue(Business Unit Allocation,Cost,Business Unit Allocation Master
Data.Business Unit,Business Unit Allocation Master Data.Business Unit)-
LookupObjectUnitValue(Service Allocations Direct,Cost,Business Unit Allocation Master Data.Business
Unit,Service Allocations Direct Master Data.Business Unit))/LookupObjectUnitValue(Business Unit
Allocation,Cost,Business Unit Allocation Master Data.Business Unit,Business Unit Allocation Master
Data.Business Unit),(LookupObjectUnitValue(Business Unit Allocation,Cost,Business Unit Allocation
Master Data.Business Unit,Business Unit Allocation Master Data.Business Unit)-
LookupObjectUnitValue(Applications,Cost,Business Unit Allocation Master Data.Business
Unit,Applications Master Data.Business Unit ID))/LookupObjectUnitValue(Business Unit
Allocation,Cost,Business Unit Allocation Master Data.Business Unit,Business Unit Allocation Master
Data.Business Unit))") to

If(IsComponentInstalled("Business Services"),(LookupObjectUnitValue(Business Unit
Allocation,Cost,Business Unit Allocation Master Data.Business Unit,Business Unit Allocation Master
Data.Business Unit)- LookupObjectUnitValue(Service Allocations Direct,Cost,Business Unit Allocation
Master Data.Business Unit,Service Allocations Direct Master Data.Business
Unit))/LookupObjectUnitValue(Business Unit Allocation,Cost,Business Unit Allocation Master
Data.Business Unit,Business Unit Allocation Master Data.Business
Unit),(LookupObjectUnitValue(Business Unit Allocation,Cost,Business Unit Allocation Master
Data.Business Unit,Business Unit Allocation Master Data.Business Unit)-
LookupObjectUnitValue(Applications,Cost,Business Unit Allocation Master Data.Business
Unit,Applications Master Data.Business Unit ID))/LookupObjectUnitValue(Business Unit
Allocation,Cost,Business Unit Allocation Master Data.Business Unit,Business Unit Allocation Master
Data.Business Unit))

## In Services – Group details report

% Change YTD updated from (Cost -
Eval("TimePeriod(Cost,"&GetInfo("project.fyMonthIndex","DomainName():ProjectName()")&")"))/Eval("TimePeriod(Cost,"&GetInfo("project.fyMonthIndex","DomainName():ProjectName()")&")")
to (Cost -
TimePeriod(Cost,GetInfo("project.fyMonthIndex")\*-1))/TimePeriod(Cost,GetInfo("project.fyMonthIndex")\*-1)

## In IT Towers - detail report

Quantity Change YTD updated from (IT Resource Tower Quantity - Eval("TimePeriod(IT
Resource Tower
Quantity,-"&GetInfo("project.fyMonthIndex","DomainName():ProjectName()")&")"))/EVAL("TimePeriod(IT
Resource Tower Quantity,-"&GetInfo("project.fyMonthIndex","DomainName():ProjectName()")&")")
to

(IT Resource Tower Quantity - TimePeriod(IT Resource Tower Quantity
,GetInfo("project.fyMonthIndex")\*-1))/TimePeriod(IT Resource Tower Quantity
,GetInfo("project.fyMonthIndex")\*-1)

Unit Cost Change YTD updated from (IT Resource Tower Average Unit
Cost-EVAL("TimePeriod(IT Resource Tower Average Unit
Cost,-"&GetInfo("project.fyMonthIndex","DomainName():ProjectName()")&")")
)/EVAL("TimePeriod(IT Resource Tower Average Unit
Cost,-"&GetInfo("project.fyMonthIndex","DomainName():ProjectName()")&")") to

(IT Resource Tower Average Unit Cost - TimePeriod(IT Resource Tower Average Unit Cost
,GetInfo("project.fyMonthIndex")\*-1))/TimePeriod(IT Resource Tower Average Unit Cost
,GetInfo("project.fyMonthIndex")\*-1)

## In CT Quality -Allocation summary report

Total Cost updated from eval("LookUpObjectTotalValue("&From
Object&",Cost)") to sumif(From Object,From Object,Value)

Installed? formula is updated from eval("IsComponentInstalled("""&Component Name&""")")
to IsComponentInstalled(Component Name)

## In Public & private cloud summary report

Cost FY Baseline updated from
IF(EVAL("TimePeriod(Cost,-"&GetInfo("project.fyMonthIndex","DomainName():ProjectName()")&")")="","N/A",(EVAL("TimePeriod(Cost,-"&GetInfo("project.fyMonthIndex","DomainName():ProjectName()")&")")))

to if(TimePeriod(Cost,GetInfo("project.fyMonthIndex")\*1)="",
"N/A",TimePeriod(Cost,GetInfo("project.fyMonthIndex")\*-1))

Count FY Baseline updated from IF(EVAL("TimePeriod(Cloud Service Provider Master
Data.Usage
Qty,-"&GetInfo("project.fyMonthIndex","DomainName():ProjectName()")&")")="","N/A",NumberFormat(EVAL("TimePeriod(Cloud
Service Provider Master Data.Usage
Qty,-"&GetInfo("project.fyMonthIndex","DomainName():ProjectName()")&")")))

to if(TimePeriod(Cloud Service Provider Master Data.Usage
Qty,GetInfo("project.fyMonthIndex")\*-1)="","N/A",TimePeriod(Cloud Service Provider Master Data.Usage
Qty,GetInfo("project.fyMonthIndex")\*-1))

## In Vendor Insight report

Notify Date updated from DateFormat(value(eval(Days(Contracts Master Data.End Date)
- eval(Contracts Master Data.Contract Notify Days))\*24\*60\*60),"yyyy-M-d")

to DateFormat((Days(Contracts Master Data.End Date) - Contracts Master Data.Contract
Notify Days)\*24\*60\*60,"yyyy-M-d")

## In Summary – Infrastructure Towers

Cost FY Baseline updated from
IF(EVAL("TimePeriod(Cost,-"&GetInfo("project.fyMonthIndex","DomainName():ProjectName()")&")")="","N/A",(EVAL("TimePeriod(Cost,-"&GetInfo("project.fyMonthIndex","DomainName():ProjectName()")&")")))
to

if(TimePeriod(Cost,GetInfo("project.fyMonthIndex")\*-1)="","N/A",TimePeriod(Cost,GetInfo("project.fyMonthIndex")\*-1))

Count FY Baseline updated from IF(EVAL("TimePeriod(Servers Master Data.Server
Hours,-"&GetInfo("project.fyMonthIndex","DomainName():ProjectName()")&")")="","N/A",NumberFormat(EVAL("TimePeriod(Servers
Master Data.Server
Hours,-"&GetInfo("project.fyMonthIndex","DomainName():ProjectName()")&")"))) to

if(TimePeriod(Servers Master Data.Server
Hours,GetInfo("project.fyMonthIndex")\*-1)="","N/A",TimePeriod(Servers Master Data.Server
Hours,GetInfo("project.fyMonthIndex")\*-1))

## In Reserved Instances report

Days until Expiration updated from if(eval("Days(Reserved Instances Master
Data.Expiration Day)-Days(Dateformat(Now(),""yyyy-MM-dd""))")>0 AND eval("Days(Reserved Instances
Master Data.Expiration Day)-Days(Dateformat(Now(),""yyyy-MM-dd""))")<=Reserved Instances Master
Data.Expiration Notification AND UPPER(Reserved Instances Master
Data.State)="ACTIVE",eval("Days(Reserved Instances Master Data.Expiration
Day)-Days(Dateformat(Now(),""yyyy-MM-dd""))"),0) to

if(Trunc(Days(Reserved Instances Master Data.Expiration
Day)-Days(Dateformat(Now(),"yyyy-MM-dd")))>0 AND Trunc(Days(Reserved Instances Master
Data.Expiration Day)-Days(Dateformat(Now(),"yyyy-MM-dd")))<=Reserved Instances Master
Data.Expiration Notification AND UPPER(Reserved Instances Master
Data.State)="ACTIVE",Trunc(Days(Reserved Instances Master Data.Expiration
Day)-Days(Dateformat(Now(),"yyyy-MM-dd"))),0)

Days Past Expiration updated from
if(eval("Days(Dateformat(Now(),""yyyy-MM-dd""))-Days(Reserved Instances Master Data.Expiration
Day)")>0 AND eval("Days(Dateformat(Now(),""yyyy-MM-dd""))-Days(Reserved Instances Master
Data.Expiration Day)")<=Reserved Instances Master Data.Expiration Notification AND UPPER(Reserved
Instances Master Data.Is
Modified)!="MODIFIED",eval("Days(Dateformat(Now(),""yyyy-MM-dd""))-Days(Reserved Instances Master
Data.Expiration Day)"),0) to

if(Trunc(Days(Dateformat(Now(),"yyyy-MM-dd"))-Days(Reserved Instances Master Data.Expiration
Day))>0 AND Trunc(Days(Dateformat(Now(),"yyyy-MM-dd"))-Days(Reserved Instances Master
Data.Expiration Day))<=Reserved Instances Master Data.Expiration Notification AND UPPER(Reserved
Instances Master Data.Is
Modified)!="MODIFIED",Trunc(Days(Dateformat(Now(),"yyyy-MM-dd"))-Days(Reserved Instances Master
Data.Expiration Day)),0)

## In Tagging Quality report

Cloud Invoice Cost of Blank Tags Reference updated from if(eval("{Cloud Service
Provider Master Data.Completeness\_Application}+{Cloud Service Provider Master
Data.Completeness\_Project}+{Cloud Service Provider Master Data.Completeness\_Environment}+{Cloud
Service Provider Master Data.Completeness\_Cost Center}+{Cloud Service Provider Master
Data.Completeness\_Purpose}+{Cloud Service Provider Master Data.Completeness\_System Owner}")>=1,Cloud
Service Provider Master Data.Absolute Cost,0) to

if(Trunc({Cloud Service Provider Master Data.Completeness\_Application}+{Cloud Service Provider
Master Data.Completeness\_Project}+{Cloud Service Provider Master
Data.Completeness\_Environment}+{Cloud Service Provider Master Data.Completeness\_Cost Center}+{Cloud
Service Provider Master Data.Completeness\_Purpose}+{Cloud Service Provider Master
Data.Completeness\_System Owner})>=1,Cloud Service Provider Master Data.Absolute Cost,0)

Cloud Invoice Cost of Invalid Tags Reference updated from if(eval("{Cloud Service
Provider Master Data.Validity\_Application}+{Cloud Service Provider Master
Data.Validity\_Project}+{Cloud Service Provider Master Data.Validity\_Environment}+{Cloud Service
Provider Master Data.Validity\_Cost Center}+{Cloud Service Provider Master
Data.Validity\_Purpose}+{Cloud Service Provider Master Data.Validity\_System Owner}")>=1,Cloud Service
Provider Master Data.Absolute Cost,0) to

if(Trunc({Cloud Service Provider Master Data.Validity\_Application}+{Cloud Service Provider Master
Data.Validity\_Project}+{Cloud Service Provider Master Data.Validity\_Environment}+{Cloud Service
Provider Master Data.Validity\_Cost Center}+{Cloud Service Provider Master
Data.Validity\_Purpose}+{Cloud Service Provider Master Data.Validity\_System Owner})>=1,Cloud Service
Provider Master Data.Absolute Cost,0)

## In Marketplace Mapping report

Cost of Invalid Mappings updated from if(eval("Invalid Service Category
Count+Invalid Service Name Count+Invalid Service Type Count+Invalid Subtower Count+Invalid Tower
Count+Invalid Unit Count")>=1,Cloud Invoice,0) to

if(Trunc(Invalid Service Category Count+Invalid Service Name Count+Invalid Service Type
Count+Invalid Subtower Count+Invalid Tower Count+Invalid Unit Count)>=1,Cloud Invoice,0)

## In New & Retired Apps report

% Count Change YoY updated from (Application Count-EVAL("TimePeriod(Application
Count,-"&GetInfo("project.fyMonthIndex","DomainName():ProjectName()")&")")
)/EVAL("TimePeriod(Application
Count,-"&GetInfo("project.fyMonthIndex","DomainName():ProjectName()")&")")

to (Application Count - TimePeriod(Application
Count,GetInfo("project.fyMonthIndex")\*-1))/TimePeriod(Application
Count,GetInfo("project.fyMonthIndex")\*-1)
