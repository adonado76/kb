---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Relación entre facturación y costes"
breadcrumb:
  - "Billing"
  - "Administración y operaciones"
  - "Arquitectura de soluciones y dependencias"
source_path: "boit/billing/sol-arch-depend/sol-arch-intro.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Relación entre facturación y costes

En esta sección se explica cómo se empaqueta la facturación, cómo se relaciona con el cálculo de costes y qué debe existir antes de que se pueda utilizar el contenido de facturación.

## Relación entre facturación y costes

La facturación no es una aplicación independiente. Es un conjunto de **componentes, modelos, tablas e informes** que se instalan en un proyecto de cálculo de costes existente y se muestran a los usuarios a través de la interfaz.

A alto nivel:

1. Los datos fluyen hacia Costing desde los sistemas fuente.
2. El cálculo de costes asigna y normaliza los costes.
3. Los componentes de facturación se añaden a un proyecto de cálculo de costes y:
   - Defina las ofertas, unidades y tarifas facturables.
   - Consumir resultados de cálculo de costes y datos de consumo.
   - Generar documentos de facturación, como facturas, informes detallados y diarios.

Puntos clave:

- La facturación **depende de** que el proyecto de cálculo de costes se haya implementado y sea estable.
- La facturación utiliza los **mismos entornos** y **el mismo motor de modelado** que el cálculo de costes.
