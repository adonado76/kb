---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "ProjectName función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/projectname.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# ProjectName función

**Se aplica a** : TBM Studio 12.0 y posteriores

Devuelve el nombre del proyecto actual.

La función ProjectName puede combinarse con la función DOMAINNAME para proporcionar un nombre completo: nombre de dominio:nombre del proyecto. Por ejemplo: acme.com:ABCPRoject. Además, ProjectName puede utilizarse con la función LOOKUPFROMPATH como parte del argumento "path".

## Dónde utilizarlo

Esta función puede utilizarse en:

- Conjuntos de datos
- Métricas calculadas e informes con columnas de métricas
- Columnas de fórmulas en tablas de informes
- Texto dinámico

## Sintaxis

`ProjectName( )`

## Tipo de retorno

Texto

Consulte también:

- [DomainName](domainname.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupFromPath](lookupfrompath.htm "(se abre en una pestaña o una ventana nueva)")
- [ProjectExists](project-exists-function.htm "(se abre en una pestaña o una ventana nueva)")
