---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "DomainName función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/domainname.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# DomainName función

**Se aplica a** : TBM Studio 12.0 y posteriores

La función DomainName puede combinarse con la función ProjectName para proporcionar un nombre completo: nombre de dominio:nombre de proyecto. Por ejemplo: acme.com:ABCPRoject. Además, DomainName puede utilizarse con la función LookUpFromPath como parte del argumento Path.

## Dónde utilizarlo

Esta función puede utilizarse en:

- Conjuntos de datos
- Métricas calculadas e informes con columnas de métricas
- Columnas de fórmulas en tablas de informes
- Texto dinámico

## Sintaxis

```
DomainName
        ( )
```

## Tipo de retorno

Texto

Consulte también:

- [ProjectName](projectname.htm "(se abre en una pestaña o una ventana nueva)")
- [LookupFromPath](lookupfrompath.htm "(se abre en una pestaña o una ventana nueva)")
