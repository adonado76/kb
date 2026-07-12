---
tbm_concept: "IBM Apptio Report Studio (New) — Getting Started, Quick Start, Core Concepts y Working with Reports de la interfaz de reporte moderna"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-tbm-studio
status: draft
generated_from:
  - kb/02-product-docs/apptio-tbm-studio/en/started-new-report-studio-overview.md
  - kb/02-product-docs/apptio-tbm-studio/en/started-how-new-report-studio-works.md
  - kb/02-product-docs/apptio-tbm-studio/en/started-guide-new-report-studios-navigation.md
  - kb/02-product-docs/apptio-tbm-studio/en/started-user-roles-permissions.md
  - kb/02-product-docs/apptio-tbm-studio/en/start-create-your-first-report.md
  - kb/02-product-docs/apptio-tbm-studio/en/start-create-your-first-report-collection.md
  - kb/02-product-docs/apptio-tbm-studio/en/concepts-custom-formulas.md
  - kb/02-product-docs/apptio-tbm-studio/en/concepts-drill-navigation.md
  - kb/02-product-docs/apptio-tbm-studio/en/reports-report-lifecycle.md
  - kb/02-product-docs/apptio-tbm-studio/en/reports-report-canvas.md
  - kb/02-product-docs/apptio-tbm-studio/en/reports-theme-engine.md
  - kb/02-product-docs/apptio-tbm-studio/en/reports-labels.md
last_updated: "2026-07-07"
---
# IBM Apptio Report Studio (New) — Getting Started — Cómo Apptio TBM Studio Aborda Esta Capacidad

## El concepto

TBM Studio opera actualmente con dos experiencias de Report Studio coexistentes — el clásico (ya documentado en categorías 5, 9 y 18 de este proyecto) y el **New Report Studio**, una reconstrucción moderna con componentes configurables, fórmulas mejoradas y un modelo de roles deliberadamente simplificado. Esta categoría cubre su Getting Started, Quick Start y conceptos base.

## Cómo lo resuelve Apptio TBM Studio

**Qué se puede hacer con el New Report Studio** — crear reportes con componentes y visualizaciones configurables, organizarlos en colecciones, interactuar vía filtros y selectores, ver datos en múltiples monedas, y exportar a PDF directamente desde la interfaz nueva (sin necesidad de pasar por el Report Viewer, a diferencia del flujo clásico).

**Modelo de roles deliberadamente simplificado — dos roles, no un espectro granular.** A diferencia del modelo clásico (Admin/Power User/roles personalizados con permisos por capa), el New Report Studio distingue solo **Admin** (crea, edita, duplica y elimina reportes; crea y gestiona colecciones) y **End User** (ve e interactúa con reportes) — una simplificación deliberada de gobernanza, no una limitación por desarrollo incompleto.

**Report Lifecycle — con autosave por defecto, un cambio de comportamiento importante frente al flujo clásico.** Los reportes se crean desde la pestaña "New Reports", abren directamente en el lienzo (canvas), y **el autoguardado está habilitado por defecto** (con opción de guardado manual disponible) — diferente al patrón de check-out/check-in explícito que domina el resto del producto. Exportar/importar la configuración de un reporte captura su definición completa (componentes y visualizaciones), útil para migración, reutilización o estandarización entre ambientes/proyectos.

**Custom Formulas (Formula Dimensions)** — en vez de limitarse a dimensiones predefinidas del esquema subyacente, se puede definir una fórmula personalizada con campos y funciones soportadas, agregarle descripción para contexto, y guardarla como una **dimensión de fórmula reutilizable** que se comporta como cualquier dimensión estándar (agrupable, deslizable, filtrable, visualizable) — disponible en todos los componentes y visualizaciones. El editor de fórmulas incluye autocompletado inteligente con sugerencias de función en tiempo real y firmas de función contextuales.

**Report Canvas / Theme Engine / Labels** — el lienzo de diseño, el motor de temas visuales (para consistencia de marca), y el sistema de etiquetas — la capa de personalización visual de la nueva interfaz.

## Por qué importa en una conversación con el cliente

La simplificación deliberada del modelo de roles (solo Admin/End User) es un buen argumento para clientes que encuentran el modelo de permisos granular del Report Studio clásico excesivamente complejo para su caso de uso — vale la pena posicionar el New Report Studio como la opción más simple de gobernar cuando la necesidad real es "algunos crean, el resto consume", sin capas intermedias.

El autoguardado por defecto es un cambio de comportamiento que vale la pena anticipar explícitamente a cualquier usuario acostumbrado al flujo clásico de check-out/check-in — la ausencia de un paso de "confirmación" explícito antes de que un cambio quede activo puede sorprender a un usuario migrando desde la experiencia clásica.

Custom Formulas con autocompletado inteligente es un argumento de productividad concreto para analistas de negocio que hoy dependen de solicitar cambios de esquema al equipo de modelado — permite exploración flexible sin depender de cambios al modelo de datos subyacente, acelerando directamente el ciclo de autoservicio analítico.

## Documentos fuente

- New Report Studio Overview — `kb/02-product-docs/apptio-tbm-studio/en/started-new-report-studio-overview.md`
- How the New Report Studio Works — `kb/02-product-docs/apptio-tbm-studio/en/started-how-new-report-studio-works.md`
- A Guide to New Report Studio's Navigation — `kb/02-product-docs/apptio-tbm-studio/en/started-guide-new-report-studios-navigation.md`
- User Roles & Permissions — `kb/02-product-docs/apptio-tbm-studio/en/started-user-roles-permissions.md`
- Create Your First Report — `kb/02-product-docs/apptio-tbm-studio/en/start-create-your-first-report.md`
- Create Your First Report Collection — `kb/02-product-docs/apptio-tbm-studio/en/start-create-your-first-report-collection.md`
- Custom Formulas — `kb/02-product-docs/apptio-tbm-studio/en/concepts-custom-formulas.md`
- Drill Navigation — `kb/02-product-docs/apptio-tbm-studio/en/concepts-drill-navigation.md`
- Report Lifecycle — `kb/02-product-docs/apptio-tbm-studio/en/reports-report-lifecycle.md`
- Report Canvas — `kb/02-product-docs/apptio-tbm-studio/en/reports-report-canvas.md`
- Theme Engine — `kb/02-product-docs/apptio-tbm-studio/en/reports-theme-engine.md`
- Labels — `kb/02-product-docs/apptio-tbm-studio/en/reports-labels.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
