---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "pt-br"
doc_type: "studio"
title: "Fórmulas de avaliação atualizadas"
breadcrumb:
  - "TBM Studio"
  - "Referência"
  - "Fórmulas e funções"
source_path: "studio/formulas-and-functions/updated-eval-formulas.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Fórmulas de avaliação atualizadas

## No relatório Business Unit Review

**BU Run** updated from Cost+CapEx-eval("If(IsComponentInstalled(""Projects"" ),Optional(Project Investments,0 ),Optional(App Dev,0 ))") **para**

Cost+CapEx-If(IsComponentInstalled("Projects" ),Optional(Project Investments,0 ),Optional(App Dev,0 ))

**Investimentos da BU** atualizados de eval("If( IsComponentInstalled(""Projects"" ),Optional(Project Investments,0 ),Optional(App Dev,0 ))") **para**

If( IsComponentInstalled("Projects" ),Optional(Project Investments,0 ),Optional(App Dev,0 ))

**% Custos diretos de BU** atualizados **de** eval("If( IsComponentInstalled(""Business Services""),LookupObjectUnitValue(Service Allocations Direct,Cost,Business Unit Allocation Master Data.Business Unit,Service Allocations Direct Master Data.Business Unit)/LookupObjectUnitValue(Business Unit Allocation,Cost,Business Unit Allocation Master Data.Business Unit,Business Unit Allocation Master Data.Business Unit),LookupObjectUnitValue(Applications,Cost,Business Unit Allocation Master Data.Business Unit,Applications Master Data.Business Unit ID)/LookupObjectUnitValue(Business Unit Allocation,Cost,Business Unit Allocation Master Data.Business Unit,Business Unit Allocation Master Data.Business Unit))") **para**

If( IsComponentInstalled("Business Services"),LookupObjectUnitValue(Service Allocations Direct,Cost,Business Unit Allocation Master Data.Business Unit,Service Allocations Direct Master Data.Business Unit)/LookupObjectUnitValue(Business Unit Allocation,Cost,Business Unit Allocation Master Data.Business Unit,Business Unit Allocation Master Data.Business Unit),LookupObjectUnitValue(Applications,Cost,Business Unit Allocation Master Data.Business Unit,Applications Master Data.Business Unit ID)/LookupObjectUnitValue(Business Unit Allocation,Cost,Business Unit Allocation Master Data.Business Unit,Business Unit Allocation Master Data.Business Unit))

**% Custos Indiretos da BU** atualizados **de** eval("If( IsComponentInstalled(""Business Services""),( LookupObjectUnitValue(Business Unit Allocation,Cost,Business Unit Allocation Master Data.Business Unit,Business Unit Allocation Master Data.Business Unit)- LookupObjectUnitValue(Service Allocations Direct,Cost,Business Unit Allocation Master Data.Business Unit,Service Allocations Direct Master Data.Business Unit))/LookupObjectUnitValue(Business Unit Allocation,Cost,Business Unit Allocation Master Data.Business Unit,Business Unit Allocation Master Data.Business Unit),( LookupObjectUnitValue(Business Unit Allocation,Cost,Business Unit Allocation Master Data.Business Unit,Business Unit Allocation Master Data.Business Unit)- LookupObjectUnitValue(Applications,Cost,Business Unit Allocation Master Data.Business Unit,Applications Master Data.Business Unit ID))/LookupObjectUnitValue(Business Unit Allocation,Cost,Business Unit Allocation Master Data.Business Unit,Business Unit Allocation Master Data.Business Unit)") **para**

If( IsComponentInstalled("Business Services"),( LookupObjectUnitValue(Business Unit Allocation,Cost,Business Unit Allocation Master Data.Business Unit,Business Unit Allocation Master Data.Business Unit)- LookupObjectUnitValue(Service Allocations Direct,Cost,Business Unit Allocation Master Data.Business Unit,Service Allocations Direct Master Data.Business Unit))/LookupObjectUnitValue(Business Unit Allocation,Cost,Business Unit Allocation Master Data.Business Unit,Business Unit Allocation Master Data.Business Unit),( LookupObjectUnitValue(Business Unit Allocation,Cost,Business Unit Allocation Master Data.Business Unit,Business Unit Allocation Master Data.Business Unit)- LookupObjectUnitValue(Applications,Cost,Business Unit Allocation Master Data.Business Unit,Applications Master Data.Business Unit ID))/LookupObjectUnitValue(Business Unit Allocation,Cost,Business Unit Allocation Master Data.Business Unit,Business Unit Allocation Master Data.Business Unit))

## Em Serviços - Relatório de detalhes do grupo

**% de alteração no acumulado do ano** atualizada **de** (Custo - Avaliação( ""TimePeriod(Cost,"&GetInfo("project.fyMonthIndex","DomainName( ):ProjectName( )")&")"))/Avaliação( ""TimePeriod(Cost,"&GetInfo("project.fyMonthIndex","DomainName( ):ProjectName( )")&")") **para** (Custo - TimePeriod(Cost,GetInfo("project.fyMonthIndex")\*-1))/TimePeriod(Cost,GetInfo("project .fyMonthIndex" )\*-1)

## Em IT Towers - relatório detalhado

**Alteração da quantidade no acumulado do ano** atualizada **de** (IT Resource Tower Quantity - Eval( ""TimePeriod(IT Resource Tower Quantity,-"&GetInfo("project.fyMonthIndex","DomainName( ):ProjectName( )")&")"))/EVAL( ""TimePeriod(IT Resource Tower Quantity,-"&GetInfo("project.fyMonthIndex","DomainName( ):ProjectName( )")&")") **para**

(Quantidade da torre de recursos de TI - TimePeriod(IT Quantidade da torre de recursos ,GetInfo("project.fyMonthIndex")\*-1))/TimePeriod(IT Quantidade da torre de recursos ,GetInfo("project.fyMonthIndex" )\*-1)

**Mudança de custo unitário no acumulado do ano** atualizada **de** (IT Resource Tower Average Unit Cost-EVAL( ""TimePeriod(IT Resource Tower Average Unit Cost,-"&GetInfo("project.fyMonthIndex","DomainName( ):ProjectName( )")&")") )/EVAL( ""TimePeriod(IT Resource Tower Average Unit Cost,-"&GetInfo("project.fyMonthIndex","DomainName( ):ProjectName( )")&")") **para**

(Custo médio unitário da torre de recursos de TI - TimePeriod(IT Custo médio unitário da torre de recursos ,GetInfo("project.fyMonthIndex")\*-1))/TimePeriod(IT Custo médio unitário da torre de recursos ,GetInfo("project.fyMonthIndex" )\*-1)

## Em CT Quality - Relatório resumido de alocação

**Custo total** atualizado **de** eval( ""LookUpObjectTotalValue("&From Object&",Cost)") para sumif(From Object,From Object,Value)

Instalado? a fórmula é atualizada de eval( ""IsComponentInstalled("""&Component Name&""")") **para** IsComponentInstalled(Component Name)

## Em Relatório resumido de nuvem pública e privada

**Custo FY Baseline** atualizado **a partir de** IF(EVAL( ""TimePeriod(Cost,-"&GetInfo("project.fyMonthIndex","DomainName( ):ProjectName( )")&")")="", "N/A",(EVAL( ""TimePeriod(Cost,-"&GetInfo("project.fyMonthIndex","DomainName( ):ProjectName( )")&")")))

**to** if( TimePeriod(Cost,GetInfo("project.fyMonthIndex" )\*1)="", "N/A",TimePeriod(Cost,GetInfo("project.fyMonthIndex" )\*-1))

**Contagem da linha de base do ano fiscal** atualizada **a partir de** IF(EVAL( "TimePeriod(Cloud Mestre do provedor de serviços Data.Usage Qty,-"&GetInfo("project .fyMonthIndex","DomainName( ):ProjectName( )")&")")="","N/A",NumberFormat(EVAL("TimePeriod(Cloud Mestre do provedor de serviços Data.Usage Qty,-"&GetInfo("project .fyMonthIndex","DomainName( ):ProjectName( )")&")")))

**to** if( TimePeriod(Cloud Mestre do provedor de serviços Data.Usage Qty,GetInfo("project .fyMonthIndex")\*-1)="","N/A",TimePeriod(Cloud Mestre do provedor de serviços Data.Usage Qty,GetInfo("project .fyMonthIndex" )\*-1))

## No relatório Vendor Insight

**Notify Date** updated **from** DateFormat(value(eval(Days(Contracts Master Data.End Date) - eval(Contracts Master Data.Contract Notify Days))\*24\*60\*60), "yyyy-M-d")

**to** DateFormat((Days(Contracts Master Data.End Date) - Contracts Master Data.Contract Notify Days)\*24\*60\*60, "yyyy-M-d")

## Em resumo - Torres de infraestrutura

**Linha de base do custo FY** atualizada **de** IF(EVAL( ""TimePeriod(Cost,-"&GetInfo("project.fyMonthIndex","DomainName( ):ProjectName( )")&")")="", "N/A",(EVAL( ""TimePeriod(Cost,-"&GetInfo("project.fyMonthIndex","DomainName( ):ProjectName( )")&")")) **para**

if( TimePeriod(Cost,GetInfo("project.fyMonthIndex")\*-1)="","N/A",TimePeriod(Cost,GetInfo("project .fyMonthIndex" )\*-1))

Contagem da linha de base do ano fiscal atualizada de IF(EVAL( "TimePeriod(Servers Master Data.Server Hours,-"&GetInfo("project .fyMonthIndex","DomainName( ):ProjectName( )")&")")="","N/A",NumberFormat(EVAL("TimePeriod(Servers Master Data.Server Hours,-"&GetInfo("project .fyMonthIndex","DomainName( ):ProjectName( )")&")")) para

if( TimePeriod(Servers Mestre Data.Server Hours,GetInfo("project .fyMonthIndex")\*-1)="","N/A",TimePeriod(Servers Mestre Data.Server Hours,GetInfo("project .fyMonthIndex" )\*-1))

## No relatório de instâncias reservadas

**Dias até a expiração** atualizados **a partir de** if(eval("Days(Reserved Instances Master Data.Expiration Day)-Days(Dateformat(Now(),""yyyy-MM-ddd"")")")>0 AND eval("Days(Reserved Instances Master Data.Expiration Day)-Days(Dateformat(Now(),""yyyy-MM-ddd""))")<=Reserved Instances Master Data.Expiration Notification AND UPPER(Reserved Instances Master Data.State )="ACTIVE",eval("Days(Reserved Instances Master Data.Expiration Day)-Days(Dateformat(Now(),""yyyy-MM-dd"")")"),0) **to**

if(Trunc(Days(Reserved Instances Master Data.Expiration Day)-Days(Dateformat(Now(), "yyyy-MM-dd")))>0 AND Trunc(Days(Reserved Instances Master Data.Expiration Day)-Days(Dateformat(Now(), "yyyy-MM-dd")))<=Reserved Instances Master Data.Expiration Notification AND UPPER(Reserved Instances Master Data.State )="ACTIVE",Trunc(Days(Reserved Instances Master Data.Expiration Day)-Days(Dateformat(Now(), "yyyy-MM-dd"))),0)

**Dias após o vencimento** atualizados de if(eval("Days(Dateformat(Now(),""yyyy-MM-dd""))-Days(Reserved Instances Master Data.Expiration Day)")>0 AND eval("Days(Dateformat(Now(),""yyyy-MM-dd""))-Days(Reserved Instances Master Data.Expiration Day)")<=Reserved Instances Master Data.Expiration Notification AND UPPER(Reserved Instances Master Data.Is Modified)!="MODIFIED",eval("Days(Dateformat(Now(),""yyyy-MM-ddd""))-Days(Reserved Instances Master Data.Expiration Day)"),0) **to**

if(Trunc(Days(Dateformat(Now(), "yyyy-MM-dd"))-Days(Reserved Instances Master Data.Expiration Day))>0 AND Trunc(Days(Dateformat(Now(), "yyyy-MM-dd"))-Days(Reserved Instances Master Data.Expiration Day))<=Reserved Instances Master Data.Expiration Notification AND UPPER(Reserved Instances Master Data.Is Modified)!="MODIFIED",Trunc(Days(Dateformat(Now(), "yyyy-MM-dd"))-Days(Reserved Instances Master Data.Expiration Day)),0)

## No relatório Qualidade da marcação

**Cloud Invoice Cost of Blank Tags Reference** atualizado **de** if(eval(" {Cloud Service Provider Master Data.Completeness\_Application} + {Cloud Service Provider Master Data.Completeness\_Project} + {Cloud Service Provider Master Data.Completeness\_Environment} + {Cloud Service Provider Master Data.Completeness\_Cost Center} + {Cloud Service Provider Master Data.Completeness\_Purpose} + {Cloud Service Provider Master Data.Completeness\_System Owner} " )>=1,Cloud Service Provider Master Data.Absolute Cost,0 ) **para**

if(Trunc( {Cloud Service Provider Master Data.Completeness\_Application} + {Cloud Service Provider Master Data.Completeness\_Project} + {Cloud Service Provider Master Data.Completeness\_Environment} + {Cloud Service Provider Master Data.Completeness\_Cost Center} + {Cloud Service Provider Master Data.Completeness\_Purpose} + {Cloud Service Provider Master Data.Completeness\_System Owner})>=1,Cloud Service Provider Master Data.Absolute Cost,0 )

**Cloud Invoice Cost of Invalid Tags Reference** updated **from** if(eval(" {Cloud Service Provider Master Data.Validity\_Application} + {Cloud Service Provider Master Data.Validity\_Project} + {Cloud Service Provider Master Data.Validity\_Environment} + {Cloud Service Provider Master Data.Validity\_Cost Center} + {Cloud Service Provider Master Data.Validity\_Purpose} + {Cloud Service Provider Master Data.Validity\_System Owner} " )>=1,Cloud Service Provider Master Data.Absolute Cost,0 ) **to**

if(Trunc( {Cloud Service Provider Master Data.Validity\_Application} + {Cloud Service Provider Master Data.Validity\_Project} + {Cloud Service Provider Master Data.Validity\_Environment} + {Cloud Service Provider Master Data.Validity\_Cost Center} + {Cloud Service Provider Master Data.Validity\_Purpose} + {Cloud Service Provider Master Data.Validity\_System Owner})>=1,Cloud Service Provider Master Data.Absolute Cost,0 )

## No relatório de mapeamento do Marketplace

**Custo de mapeamentos inválidos** atualizado **de** if(eval("Invalid Service Category Count+Invalid Service Name Count+Invalid Service Type Count+Invalid Subtower Count+Invalid Tower Count+Invalid Unit Count" )>=1,Cloud Invoice,0 ) **para**

if(Trunc(Invalid Service Category Count+Invalid Service Name Count+Invalid Service Type Count+Invalid Subtower Count+Invalid Tower Count+Invalid Unit Count)>=1,Cloud Invoice,0 )

## No relatório Aplicativos novos e desativados

**% de alteração na contagem YoY** atualizada **de** (Contagem de aplicativos-EVAL( ""TimePeriod(Application Count,-"&GetInfo("project .fyMonthIndex","DomainName( ):ProjectName( )")&")") )/EVAL( ""TimePeriod(Application Count,-"&GetInfo("project .fyMonthIndex","DomainName( ):ProjectName( )")&")")

to (Contagem de aplicativos - TimePeriod(Application Count,GetInfo("project .fyMonthIndex")\*-1))/TimePeriod(Application Count,GetInfo("project .fyMonthIndex" )\*-1)
