---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Facturación y vistas centradas en proyectos"
breadcrumb:
  - "Billing"
  - "Temas avanzados"
source_path: "boit/billing/advance-topic/project-centric-billin.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Facturación y vistas centradas en proyectos

Los proyectos suelen representar inversiones en productos, servicios o iniciativas de cambio. Los componentes del proyecto Billing Standard permiten la facturación y la retroalimentación centradas en el proyecto.

Nota: Se aplica únicamente a la norma de facturación.

## Proyecto como consumidor frente a proyecto como dimensión

Dos patrones comunes:

- **Proyecto como consumidor**
  - El proyecto se factura por los servicios que consume (por ejemplo, plataformas, entornos, herramientas compartidas).
  - Útil para realizar un seguimiento del uso de la infraestructura o las plataformas compartidas en los proyectos.
- **Proyecto como dimensión**
  - Los cargos a las unidades de negocio se etiquetan con atributos del proyecto.
  - Útil para comprender cuánto gasta una unidad de negocio en iniciativas específicas.

Opciones de diseño:

- Decida si los proyectos:
  - Recibir cargos directamente.
  - Etiqueta solo el consumo subyacente de mano de obra o servicios.
- Asegúrese de que los ID y los nombres de los proyectos sean estables y coherentes en todos los sistemas (PPM, RR. HH., Finanzas).

## Datos necesarios para las vistas del proyecto

Requisitos mínimos:

- Responsable del proyecto:
  - ID del proyecto, nombre, propietario, tipo y estado del ciclo de vida.
- Asignaciones de proyectos a servicios:
  - Vincular proyectos a servicios, aplicaciones o plataformas utilizadas.
- Mano de obra y otros factores que influyen en los costes:
  - Tiempo, coste o puntos por proyecto, cuando los proyectos determinan la asignación.

Con estos elementos en su lugar, Billing Standard puede:

- Mostrar cargos por proyecto y consumidor.
- Mostrar tarifas unitarias específicas del proyecto para servicios compartidos.
- Informes de soporte como «los 10 proyectos principales por consumo tecnológico»
