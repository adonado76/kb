---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Resumen de dependencias"
breadcrumb:
  - "Billing"
  - "Administración y operaciones"
  - "Arquitectura de soluciones y dependencias"
source_path: "boit/billing/sol-arch-depend/depend-summary.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Resumen de dependencias

La siguiente tabla resume las dependencias clave para cada edición.

|  |  |  |
| --- | --- | --- |
| **Área** | **Fundamentos de facturación** | **Norma de facturación** |
| **Requisito de cálculo de costes** | Proyecto «Fundamentos del cálculo de costes» implementado | Proyecto de estándar de costes implementado |
| **Plantilla de componentes** | Versión 200 | Versión 120 y anteriores |
| **Componentes de facturación** | Facturación: cobro, facturación: informe de cobros | Múltiples componentes (Fundación, Unidades, Aplicaciones, Nube, etc.) |
| **Punto final** | Sin punto final de facturación independiente; utiliza Costing Essentials | Punto final de facturación separado además del estándar de costes |
| **Punto de entrada frontal** | Fundamentos de cálculo de costes front-end, recopilación de informes de facturación | Aplicación/punto final dedicado al estándar de facturación |
| **Dependencia de TBM Studio** | El mismo proyecto que Costing Essentials | Mismo proyecto que el estándar de costes |

Esta vista de arquitectura y dependencias debe comprobarse antes de realizar cualquier tarea de configuración o resolución de problemas. Si falta alguno de los requisitos previos o no se cumple correctamente, el comportamiento de facturación en las secciones posteriores de la guía no coincidirá con lo descrito.
