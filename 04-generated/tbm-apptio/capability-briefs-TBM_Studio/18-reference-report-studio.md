---
concept: "Reference: Report Studio — catálogo exhaustivo de referencia técnica para todos los componentes, propiedades, layout, master reports, colecciones y permisos del Report Studio clásico"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-tbm-studio
status: draft
generated_from:
  - "kb/02-product-docs/apptio-tbm-studio/en/ (107 documentos de referencia bajo Reference > Report Studio Reference)"
last_updated: "2026-07-07"
---
# Reference: Report Studio — Cómo Apptio TBM Studio Aborda Esta Capacidad

## Nota de alcance

Esta categoría contiene **107 documentos** — el mayor volumen de todo el proyecto TBM Studio junto con Formulas and Functions. Es la referencia técnica exhaustiva del Report Studio clásico (distinto del New Report Studio, ya cubierto narrativamente en las categorías 8-10). Dado que ya documentamos narrativamente los conceptos centrales de reporte en la categoría 5 (How-To: Create Reports), este brief funciona como **catálogo organizado por sub-tema**, apuntando a qué existe y dónde, en lugar de repetir en detalle cada una de las 107 páginas.

## El concepto

Mientras "How-To: Create Reports" enseña el flujo de trabajo, esta categoría es el manual de referencia que un diseñador de reportes experimentado consulta constantemente: cada propiedad configurable, de cada tipo de componente, documentada exhaustivamente.

## Cómo lo resuelve Apptio TBM Studio — catálogo por sub-tema

**Report Components: Tables** (9 páginas) — estructura, columnas, opciones de visualización de dato, ordenamiento, filtrado, columnas basadas en calendario, sparklines e indicadores de estado, propiedades y comportamiento de tabla, y consideraciones de performance.

**Report Components: Charts** (14 páginas) — nueve tipos de gráfico (Bar, Column, Line, Pie/Donut, Trend, **Waterfall**, **Tree Maps**, **Radar**, Overlay/Combination — un catálogo más amplio que el del New Report Studio, que solo cubre seis tipos), más propiedades comunes, configuración de color, navegación/drill-through, interactividad, una **guía de selección de tipo de gráfico**, formato de ejes, y — un documento particularmente relevante para cualquier plan de migración — **"Legacy Charts vs. Ad Hoc Charts"**, comparando explícitamente el modelo antiguo de gráficos contra el modelo más flexible actual.

**Report Components: Filters and Slicers** (9 páginas) — tipos de componente, configuración de data binding, comportamiento y alcance de filtro, **filtros jerárquicos y en cascada**, filtrado de período de tiempo, consideraciones de performance, patrones comunes, y troubleshooting dedicado.

**Report Components: Navigation** (6 páginas) — tipos de componente de navegación, configuración de drill-through, **navegación condicional**, slicers jerárquicos para drill-down, estilo de navegación, y mejores prácticas.

**Report Components - Input Components** (6 páginas) — tipos de componente de entrada, data binding, validación, comportamiento, permisos, y casos de uso comunes — la capa de captura de datos embebida en reportes, en su versión de referencia técnica completa.

**Report Components: Editable Tables in Reports** (10 páginas) — configuración, opciones de edición de columna, configuración de validación, operaciones de fila, comportamiento de guardado, permisos de edición, estilo, integración editable table + reporte, patrones comunes, y troubleshooting — la documentación de referencia completa de la capacidad ya introducida narrativamente en la categoría 5.

**Report Properties** (9 páginas) — configuración de período de tiempo, ajustes de visualización, **configuración de Active y Preload** (comportamiento de pre-cálculo del reporte), configuración de Master Report, ajustes de seguridad, impresión/exportación, suscripción por correo, opciones avanzadas de desglose, y **configuración de localización**.

**Layout Options** (7 páginas) — opciones de tamaño de pantalla, posicionamiento y dimensionamiento de componentes, componentes contenedores, configuración de layout de impresión, y mejores prácticas de layout.

**Master Reports** (8 páginas) — conceptos, creación, contenido del master report, **herencia**, aplicar/remover master reports, mejores prácticas, **Multi-Level Masters** (un master aplicado sobre otro master, un nivel de sofisticación de plantilla no mencionado en el resumen narrativo de la categoría 5), y troubleshooting dedicado.

**Report Collections** (7 páginas) — conceptos, creación, agregar reportes, navegación de colección, configuración, permisos, y organización.

**Report Permissions** (7 páginas) — la referencia técnica completa del modelo de permisos: arquitectura del modelo de permisos, tipos de permiso, asignación, **row-level security específicamente en el contexto de reportes**, permisos a nivel de componente, mejores prácticas, y troubleshooting de problemas de permisos.

## Por qué importa en una conversación con el cliente

"Legacy Charts vs. Ad Hoc Charts" es el documento correcto a consultar antes de cualquier conversación sobre modernizar reportes existentes — confirma qué gráficos antiguos pueden convertirse al modelo más flexible actual y cuáles requieren reconstrucción.

El catálogo de nueve tipos de gráfico del Report Studio clásico (vs. seis en el New Report Studio) es un dato concreto a tener presente en cualquier conversación de migración: Waterfall, Tree Maps y Radar Charts **no tienen equivalente documentado todavía en la interfaz nueva** según lo revisado en las categorías 8-10 — vale la pena confirmar esto explícitamente con el equipo de producto antes de prometer una migración 1:1 completa a un cliente que use estos tipos de gráfico específicos.

Multi-Level Masters es una capacidad de gobernanza de marca more sofisticada que vale la pena mencionar a cualquier cliente con múltiples líneas de negocio que necesiten una identidad visual compartida pero con variaciones — un master general de la organización, con masters secundarios específicos por línea de negocio aplicados encima.

## Documentos fuente

Los 107 documentos de esta categoría viven en `kb/02-product-docs/apptio-tbm-studio/en/`, bajo la ruta de breadcrumb `Reference > Report Studio Reference`. Dado el volumen, se listan aquí por sub-tema (ver secciones arriba) en lugar de archivo por archivo; el listado completo de topic-slugs está disponible en `inventory/ibm/apptio/tbm-studio/DOCUMENT_CATALOG.yaml` filtrando por ese breadcrumb.

*Nota: versión en español/portugués se genera en una siguiente pasada. Este brief usa un formato de catálogo condensado, diferente al resto del proyecto, dado el volumen de la categoría (107 documentos) — ver nota de alcance al inicio.*
