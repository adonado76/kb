---
tbm_concept: "Working with Plan Dimensions (los dos tipos de dimensión de plan, y su configuración centralizada por administradores)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - apptio-financial-planning
status: draft
generated_from:
  - kb/02-product-docs/apptio-financial-planning/en/dimensions-plan-dimension-types.md
  - kb/02-product-docs/apptio-financial-planning/en/dimensions-setting-up-recommended.md
  - kb/02-product-docs/apptio-financial-planning/en/dimensions-changing-in-plan.md
last_updated: "2026-07-10"
---
# Working with Plan Dimensions — Cómo IBM Cloudability Financial Planning Aborda Esta Capacidad

## El concepto

Ya vimos en "Configuring Cloudability Financial Planning" que las dimensiones son la pieza central de diseño de cualquier plan (con el límite de 4 dimensiones de Cloudability + 20 dimensiones exclusivas del plan). Este capítulo cubre la gestión administrativa de esas dimensiones: dónde se configuran centralmente y cómo se recomiendan a los usuarios.

## Cómo lo resuelve IBM Cloudability Financial Planning

**Plan Dimension Types — confirmación formal de la distinción de dos tipos ya introducida conceptualmente**, accesible desde Organize → Plan Dimensions:
- **Cloudability Plan Dimension** — usadas para resumir y alinear actuals con las líneas del plan (equivalentes a las dimensiones "de Cloudability" ya vistas, vinculadas directamente a datos reales).
- **Plan-only Plan Dimension** — capturan detalle adicional sobre ajustes (líneas de forecast nuevas o modificadas), desde algo tan simple como un campo de Comentarios hasta algo tan estructurado como una lista de Iniciativas.

**Setting up Recommended Dimensions** — la funcionalidad de administración ya mencionada en Getting Started: Plan Administrators (Cloudability Admin o Cloudability Planning Admin) configuran centralmente qué dimensiones se recomiendan a los usuarios al crear un plan nuevo, apareciendo en el "Dimensions Picker" ya visto en el flujo de Creating Plans.

**Changing Dimensions in a Plan** — la funcionalidad de modificación de dimensiones dentro de un plan ya existente, restringida a Plan Owners (ya mencionada como parte del menú de Plan Actions en el capítulo Working with Plans).

## Por qué importa en una conversación con el cliente

La distinción entre dimensiones de Cloudability (ligadas a actuals) y dimensiones exclusivas del plan (solo contexto cualitativo) es clave para diseñar correctamente qué información captura cada tipo — usar una dimensión Plan-only para algo que en realidad necesita compararse contra gasto real es un error de diseño común que vale la pena prevenir en discovery.

Configurar dimensiones recomendadas centralmente (vía Plan Administrators) es un mecanismo de gobernanza de consistencia importante para clientes con múltiples equipos creando planes de forma independiente — evita que cada equipo invente su propio esquema de dimensiones sin coordinación, dificultando la consolidación posterior.

## Documentos fuente

- Plan Dimension Types — `kb/02-product-docs/apptio-financial-planning/en/dimensions-plan-dimension-types.md`
- Setting up Recommended Dimensions — `kb/02-product-docs/apptio-financial-planning/en/dimensions-setting-up-recommended.md`
- Changing Dimensions in a Plan — `kb/02-product-docs/apptio-financial-planning/en/dimensions-changing-in-plan.md`

*Nota: los dos últimos documentos fuente tienen contenido limitado en la documentación oficial de IBM (más allá del título e imagen de referencia) — este brief refleja fielmente lo disponible. Versión en español/portugués se genera en una siguiente pasada.*
