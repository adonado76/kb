---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Fórmulas de evaluación actualizadas"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/updated-eval-formulas.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Fórmulas de evaluación actualizadas

## En el informe Business Unit Review

**BU Run** updated from Cost+CapEx-eval("If(IsComponentInstalled(""Projects"" ),Optional(Project Investments,0 ),Optional(App Dev,0 ))") **a**

Cost+CapEx-If(IsComponentInstalled("Projects" ),Opcional(Proyecto Investments,0 ),Opcional(Aplicación Dev,0 ))

**Inversiones BU** actualizadas de eval("If( IsComponentInstalled(""Projects"" ),Optional(Project Investments,0 ),Optional(App Dev,0 ))") **a**

If( IsComponentInstalled("Projects" ),Opcional(Proyecto Investments,0 ),Opcional(Aplicación Dev,0 ))

**% Costes Directos BU** actualizados **de** eval("If( IsComponentInstalled(""Business Services""),LookupObjectUnitValue(Service Asignaciones Directas,Coste,Asignación Unidad de Negocio Master Data.Business Unidad,Servicio Asignaciones Directas Master Data.Business Unit)/LookupObjectUnitValue(Business Asignación Unidad,Coste,Asignación Unidad de Negocio Master Data.Business Unidad,Asignación Unidad de Negocio Master Data.Business Unit),LookupObjectUnitValue(Applications,Cost,Business Asignación Unidad Master Data.Business Unidad,Aplicaciones Master Data.Business Unidad ID)/LookupObjectUnitValue(Business Asignación Unidad,Coste,Asignación Unidad de Negocio Master Data.Business Unidad,Asignación Unidad de Negocio Master Data.Business Unidad))") **a**

If( IsComponentInstalled("Business Services"),LookupObjectUnitValue(Service Asignaciones directas,Coste,Asignación de unidad de negocio Master Data.Business Unidad,Asignaciones directas de servicio Master Data.Business Unit)/LookupObjectUnitValue(Business Asignación de unidad,Coste,Asignación de unidad de negocio Master Data.Business Unidad,Asignación de unidad de negocio Master Data.Business Unit),LookupObjectUnitValue(Applications,Cost,Business Asignación de unidad Master Data.Business Unidad,Aplicaciones Master Data.Business Unidad ID)/LookupObjectUnitValue(Business Asignación de unidad,Coste,Asignación de unidad de negocio Master Data.Business Unidad,Asignación de unidad de negocio Master Data.Business Unidad))

**% Costes indirectos BU** actualizados **de** eval("If( IsComponentInstalled(""Business Services"),( LookupObjectUnitValue(Business Unit Allocation,Cost,Business Unit Allocation Master Data.Business Unit,Business Unit Allocation Master Data.Business Unit)- LookupObjectUnitValue(Service Allocations Direct,Cost,Business Unit Allocation Master Data.Business Unit,Service Allocations Direct Master Data.Business Unit))/LookupObjectUnitValue(Business Unit Allocation,Cost,Business Unit Allocation Master Data.Business Unit,Asignación de unidad de negocio Maestro Data.Business Unidad),( LookupObjectUnitValue(Business Asignación de unidad,Coste,Asignación de unidad de negocio Maestro Data.Business Unidad,Asignación de unidad de negocio Maestro Data.Business Unidad)- LookupObjectUnitValue(Applications,Cost,Business Asignación de unidad Maestro Data.Business Unidad,Aplicaciones Maestro Data.Business Unidad ID))/LookupObjectUnitValue(Business Asignación de unidad,Coste,Asignación de unidad de negocio Maestro Data.Business Unidad,Asignación de unidad de negocio Maestro Data.Business Unidad))") **a**

Si( IsComponentInstalled("Business Servicios"),( LookupObjectUnitValue(Business Unit Allocation,Coste,Business Unit Allocation Master Data.Business Unit,Business Unit Allocation Master Data.Business Unit)- LookupObjectUnitValue(Service Allocations Direct,Coste,Business Unit Allocation Master Data.Business Unit,Service Allocations Direct Master Data.Business Unit))/LookupObjectUnitValue(Business Unit Allocation,Coste,Business Unit Allocation Master Data.Business Unit,Asignación Unidad de Negocio Maestro Data.Business Unidad),( LookupObjectUnitValue(Business Asignación Unidad,Coste,Asignación Unidad de Negocio Maestro Data.Business Unidad,Asignación Unidad de Negocio Maestro Data.Business Unidad)- LookupObjectUnitValue(Applications,Cost,Business Asignación Unidad Maestro Data.Business Unidad,Aplicaciones Maestro Data.Business Unidad ID))/LookupObjectUnitValue(Business Asignación Unidad,Coste,Asignación Unidad de Negocio Maestro Data.Business Unidad,Asignación Unidad de Negocio Maestro Data.Business Unidad))

## En Servicios - Informe detallado del grupo

**% Cambio YTD** actualizado **de** (Coste - Eval( ""TimePeriod(Cost,"&GetInfo("project.fyMonthIndex","DomainName( ):ProjectName( )")&")")/Eval( ""TimePeriod(Cost,"&GetInfo("project.fyMonthIndex","DomainName( ):ProjectName( )")&")") **a** (Coste - TimePeriod(Cost,GetInfo("project.fyMonthIndex")\*-1))/TimePeriod(Cost,GetInfo("project .fyMonthIndex" )\*-1)

## En IT Towers - informe detallado

**Cantidad Cambio YTD** actualizado **de** (Cantidad Torre de Recursos IT - Eval( ""TimePeriod(IT Torre de Recursos Quantity,-"&GetInfo("project.fyMonthIndex","DomainName( ):ProjectName( )")&")"))/EVAL( ""TimePeriod(IT Torre de Recursos Quantity,-"&GetInfo("project.fyMonthIndex","DomainName( ):ProjectName( )")&")") **a**

(Cantidad de torres de recursos TI - TimePeriod(IT Cantidad de torres de recursos ,GetInfo("project.fyMonthIndex")\*-1))/TimePeriod(IT Cantidad de torres de recursos ,GetInfo("project.fyMonthIndex" )\*-1)

**Cambio de coste unitario YTD** actualizado **de** (IT Torre de Recursos Coste unitario medio-EVAL( ""TimePeriod(IT Torre de Recursos Unidad media Cost,-"&GetInfo("project.fyMonthIndex","DomainName( ):ProjectName( )")&")") )/EVAL( ""TimePeriod(IT Torre de Recursos Unidad media Cost,-"&GetInfo("project.fyMonthIndex","DomainName( ):ProjectName( )")&")") **a**

(Coste unitario medio de la torre de recursos TI - TimePeriod(IT Coste unitario medio de la torre de recursos ,GetInfo("project.fyMonthIndex")\*-1))/TimePeriod(IT Coste unitario medio de la torre de recursos ,GetInfo("project.fyMonthIndex" )\*-1)

## En CT Calidad -Informe resumido de asignación

**Coste** total actualizado **de** eval( ""LookUpObjectTotalValue("&From Objeto&",Coste)") a sumif(De Objeto,De Objeto,Valor)

¿Instalado? la fórmula se actualiza de eval( "IsComponentInstalled("""&Component Nombre&"")") **a** IsComponentInstalled(Component Nombre)

## En Informe resumido sobre la nube pública y privada

**Coste FY Base** actualizada **de** IF(EVAL( ""TimePeriod(Cost,-"&GetInfo("project.fyMonthIndex","DomainName( ):ProjectName( )")&")")="", "N/A",(EVAL( "TimePeriod(Cost,-"&GetInfo("project.fyMonthIndex","DomainName( ):ProjectName( )")&")))

**a** if( TimePeriod(Cost,GetInfo("project.fyMonthIndex" )\*1)="", "N/A",TimePeriod(Cost,GetInfo("project.fyMonthIndex" )\*-1))

**Count FY Baseline** updated **from** IF(EVAL( "TimePeriod(Cloud Proveedor de Servicios Maestro Data.Usage Qty,-"&GetInfo("project .fyMonthIndex","DomainName( ):ProjectName( )")&")")="","N/A",NumberFormat(EVAL("TimePeriod(Cloud Proveedor de Servicios Maestro Data.Usage Qty,-"&GetInfo("project .fyMonthIndex","DomainName( ):ProjectName( )")&")))

**a** if( TimePeriod(Cloud Proveedor de Servicios Maestro Data.Usage Qty,GetInfo("project .fyMonthIndex")\*-1)="","N/A",TimePeriod(Cloud Proveedor de Servicios Maestro Data.Usage Qty,GetInfo("project .fyMonthIndex" )\*-1))

## En el informe Vendor Insight

**Fecha de notificación** actualizada **a partir de** DateFormat(value(eval(Days(Contracts Maestro Data.End Fecha) - eval(Contratos Maestro Data.Contract Notificar Días))\*24\*60\*60), "aaaa-M-d")

**a** DateFormat((Days(Contracts Maestro Data.End Fecha) - Contratos Maestro Data.Contract Notificar Días)\*24\*60\*60, "aaaa-M-d")

## En resumen - Torres de infraestructuras

**Coste del ejercicio base** actualizado **de** IF(EVAL( ""TimePeriod(Cost,-"&GetInfo("project.fyMonthIndex","DomainName( ):ProjectName( )")&")")="", "N/A",(EVAL( "TimePeriod(Cost,-"&GetInfo("project.fyMonthIndex","DomainName( ):ProjectName( )")&"))) **a**

if( TimePeriod(Cost,GetInfo("project.fyMonthIndex")\*-1)="","N/A",TimePeriod(Cost,GetInfo("project .fyMonthIndex" )\*-1))

Count FY Baseline updated from IF(EVAL( "TimePeriod(Servers Master Data.Server Hours,-"&GetInfo("project .fyMonthIndex","DomainName( ):ProjectName( )")&")")="","N/A",NumberFormat(EVAL("TimePeriod(Servers Master Data.Server Hours,-"&GetInfo("project .fyMonthIndex","DomainName( ):ProjectName( )")&"))) to

if( TimePeriod(Servers Maestro Data.Server Hours,GetInfo("project .fyMonthIndex")\*-1)="","N/A",TimePeriod(Servers Maestro Data.Server Hours,GetInfo("project .fyMonthIndex" )\*-1))

## En el informe Instancias reservadas

**Días hasta la caducidad** actualizados **a partir de** if(eval("Days(Reserved Instances Master Data.Expiration Day)-Days(Dateformat(Now(),""yyyy-MM-dd""))")>0 AND eval("Days(Reserved Instances Master Data.Expiration Day)-Days(Dateformat(Now(),""yyyy-MM-dd""))")<=Instancias reservadas Maestro Data.Expiration Notificación AND UPPER(Instancias reservadas Maestro Data.State )="ACTIVE",eval("Days(Instancias reservadas Maestro Data.Expiration Day)-Days(Dateformat(Now(),""yyyy-MM-dd"")"),0) **a**

if(Trunc(Días(Maestro instancias reservadas Data.Expiration Día)-Días(Formato fecha(Ahora(), "aaaa-MM-dd")))>0 AND Trunc(Días(Maestro instancias reservadas Data.Expiration Día)-Días(Formato fecha(Ahora(), "aaaa-MM-dd")))<=Instancias reservadas Maestro Data.Expiration Notificación AND UPPER(Instancias reservadas Maestro Data.State )="ACTIVE",Trunc(Days(Instancias reservadas Maestro Data.Expiration Day)-Days(Dateformat(Now(), "aaaa-MM-dd"))),0)

**Días pasados del vencimiento** actualizados de if(eval("Days(Dateformat(Now(),""aaaa-MM-dd""))-Days(Reserved Instances Master Data.Expiration Day)")>0 AND eval("Days(Dateformat(Now(),""aaaa-MM-dd""))-Days(Reserved Instances Master Data.Expiration Day)")<=Reserved Instances Master Data.Expiration Notification AND UPPER(Reserved Instances Master Data.Is Modified)!="MODIFIED",eval("Days(Dateformat(Now(),""aaaa-MM-dd""))-Days(Reserved Instances Master Data.Expiration Day)"),0) **a**

¡if(Trunc(Días(Dateformat(Ahora(), "aaaa-MM-dd"))-Días(Instancias reservadas Maestro Data.Expiration Día))>0 AND Trunc(Días(Dateformat(Ahora(), "aaaa-MM-dd"))-Días(Instancias reservadas Maestro Data.Expiration Día))<=Instancias reservadas Maestro Data.Expiration Notificación AND UPPER(Instancias reservadas Maestro Data.Is Modificado)!="MODIFIED",Trunc(Days(Dateformat(Now(), "aaaa-MM-dd"))-Days(Reserved Instances Master Data.Expiration Day)),0)

## En el informe Calidad del etiquetado

**Factura en nube Coste de etiquetas en blanco Referencia** actualizada **de** if(eval(" {Cloud Service Provider Master Data.Completeness\_Application} + {Cloud Service Provider Master Data.Completeness\_Project} + {Cloud Service Provider Master Data.Completeness\_Environment} + {Cloud Service Provider Master Data.Completeness\_Cost Center} + {Cloud Service Provider Master Data.Completeness\_Purpose} + {Cloud Service Provider Master Data.Completeness\_System Owner} " )>=1,Cloud Proveedor de servicios Maestro Data.Absolute Cost,0 ) **a**

if(Trunc( {Cloud Service Provider Master Data.Completeness\_Application} + {Cloud Service Provider Master Data.Completeness\_Project} + {Cloud Service Provider Master Data.Completeness\_Environment} + {Cloud Service Provider Master Data.Completeness\_Cost Center} + {Cloud Service Provider Master Data.Completeness\_Purpose} + {Cloud Service Provider Master Data.Completeness\_System Owner})>=1,Cloud Proveedor de servicios Maestro Data.Absolute Cost,0 )

**Factura en nube Coste de etiquetas no válidas Referencia** actualizada **de** if(eval(" {Cloud Service Provider Master Data.Validity\_Application} + {Cloud Service Provider Master Data.Validity\_Project} + {Cloud Service Provider Master Data.Validity\_Environment} + {Cloud Service Provider Master Data.Validity\_Cost Center} + {Cloud Service Provider Master Data.Validity\_Purpose} + {Cloud Service Provider Master Data.Validity\_System Owner} " )>=1,Cloud Proveedor de servicios Maestro Data.Absolute Cost,0 ) **a**

if(Trunc( {Cloud Service Provider Master Data.Validity\_Application} + {Cloud Service Provider Master Data.Validity\_Project} + {Cloud Service Provider Master Data.Validity\_Environment} + {Cloud Service Provider Master Data.Validity\_Cost Center} + {Cloud Service Provider Master Data.Validity\_Purpose} + {Cloud Service Provider Master Data.Validity\_System Owner})>=1,Cloud Proveedor de servicios Maestro Data.Absolute Cost,0 )

## En el informe Marketplace Mapping

**Coste de las asignaciones no válidas** actualizado **de** if(eval("Recuento de categorías de servicio no válidas+Cuento de nombres de servicio no válidos+Cuento de tipos de servicio no válidos+Cuento de subtorres no válidas+Cuento de torres no válidas+Cuento de unidades no válidas" )>=1,Cloud Invoice,0 ) **a**

if(Trunc(Recuento de categorías de servicio no válidas+Recuento de nombres de servicio no válidos+Recuento de tipos de servicio no válidos+Recuento de subtorres no válidas+Recuento de torres no válidas+Unidad no válida Count)>=1,Cloud Invoice,0 )

## En el informe Aplicaciones nuevas y retiradas

**% Recuento Cambio YoY** actualizado **desde** (Aplicación Recuento-EVAL( ""TimePeriod(Application Count,-"&GetInfo("project .fyMonthIndex","DomainName( ):ProjectName( )")&")") )/EVAL( ""TimePeriod(Application Count,-"&GetInfo("project .fyMonthIndex","DomainName( ):ProjectName( )")&")")

a (Recuento de solicitudes - TimePeriod(Application Count,GetInfo("project .fyMonthIndex")\*-1))/TimePeriod(Application Count,GetInfo("project .fyMonthIndex" )\*-1)
