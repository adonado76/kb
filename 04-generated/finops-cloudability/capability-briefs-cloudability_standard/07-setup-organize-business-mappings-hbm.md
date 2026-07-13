---
tbm_concept: "Business Mappings (motor de reglas para crear Business Dimensions vía statements) y Hierarchical Business Mappings (jerarquías de rollup a escala)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - apptio-cloudability-standard
status: draft
generated_from:
  - kb/02-product-docs/apptio-cloudability-standard/en/spend-business-mapping.md
  - kb/02-product-docs/apptio-cloudability-standard/en/mapping-organize-data-using-hierarchical-business-mappings.md
  - kb/02-product-docs/apptio-cloudability-standard/en/point-cloudability-structure-business-mapping.md
last_updated: "2026-07-13"
---
# Setup — Organize - Business Mappings & Hierarchical Business Mappings — Cómo IBM Cloudability Standard Aborda Esta Capacidad

## El concepto

A diferencia de los tags nativos del proveedor (que reflejan lo que alguien decidió etiquetar en el momento de crear el recurso), Business Mappings evalúa la metadata de facturación e ingesta contra reglas definidas por el cliente y asigna cada línea de costo a una categoría de negocio — sin depender de que el recurso tenga un tag correcto o siquiera un tag. Es el motor que traduce "esto es un `AWS EC2` en `us-east-1`" a "esto es gasto de `Compute` del `Continente: United States`".

## Cómo lo resuelve IBM Cloudability Standard

**Unidad fundamental: la Mapping Rule, un payload JSON con tres elementos.** Cada regla tiene un `name` (la etiqueta que tomará la Business Dimension o Business Metric resultante en todos los reportes de Cloudability), una secuencia de `statements` para probar distintas condiciones de match, y un `defaultValue` que solo se aplica cuando ningún statement logra un match — ejemplos típicos de defaultValue documentados son "Unallocated", "Non Compliant" o "Not Applicable", elegidos deliberadamente según el propósito de la dimensión.

**Cada statement combina un `matchExpression` (la condición) con un `valueExpression` (el valor asignado si la condición es verdadera).** Ejemplo documentado: un statement con `matchExpression: "DIMENSION['region'] STARTS_WITH 'us-'"` y `valueExpression: "'United States'"` — evaluado en secuencia contra cada línea de costo.

**El atributo `kind` distingue si la Mapping Rule define una Business Dimension o una Business Metric** (`BUSINESS_DIMENSION` es uno de los valores documentados) dentro del mismo constructo de Business Mapping — ambos comparten el mismo lenguaje de expresión y estructura de statements.

**`preMatchExpression` — una expresión centralizada/global que se evalúa antes que todos los demás statements.** Es opcional (puede dejarse vacía), y sirve para lógica común que aplicaría a todas las condiciones subsiguientes sin repetirla en cada statement.

**Evaluación en orden con lógica AND y cortocircuito (short-circuit)** — el orden de los statements importa, y la evaluación se detiene en la primera condición que falla, lo que hace que el orden de las reglas sea una decisión de diseño, no solo de organización.

**Límite documentado: máximo 10 Business Dimensions por organización.**

**Hierarchical Business Mappings (HBM) — resuelve el problema de mantener jerarquías de rollup sin duplicar mapeos.** En vez de crear Business Mappings independientes para cada nivel de una jerarquía (Team → Department → Group) y mantener manualmente la relación entre ellos, un HBM define la relación de rollup completa vía un **mapping file en CSV**: la columna más a la izquierda es la dimensión base (o una Business Mapping ya existente), y cada columna subsiguiente define un nivel padre adicional — patrón documentado en herramientas de actualización bulk como `Application,L2,L3` (ej. `App-A,Department-X,Team-1`). Se pueden agregar hasta **4 capas adicionales** sobre la dimensión base, y el nombre de la jerarquía se convierte en el nodo raíz de su View jerárquica correspondiente. Las Hierarchical Business Dimensions se pueden renombrar directamente desde la interfaz sin reconstruir la jerarquía completa.

**Gestión centralizada y controles de permiso de tres niveles**, unificados entre Business Dimensions, Hierarchical Dimensions y Business Metrics: **Admin** (acceso completo para crear, editar y eliminar), **Edit** (crear y modificar las métricas/mapeos propios), y **View** (solo lectura — sin ver siquiera los botones de acción Edit/Delete/Create en la interfaz).

**Export/Import de definiciones vía JSON**, permitiendo respaldo o compartición de la configuración completa de una Business Mapping fuera de la interfaz.

**API programática vía Business Mappings End Point**, con documentación dedicada para la estructura de una Business Mapping, el lenguaje de expresión, cómo interactúan múltiples reglas entre sí, y templates reutilizables.

## Por qué importa en una conversación con el cliente

**RETOS QUE RESUELVE:** cuando la taxonomía de negocio de un cliente no coincide 1:1 con lo que expone el proveedor de nube (regiones, servicios, cuentas), Business Mappings permite construir esa traducción de forma declarativa y auditable en vez de depender de tagging manual. HBM específicamente resuelve el dolor de mantener jerarquías de reporte (Team → Department → Group) que cambian con el tiempo — sin este mecanismo, cada reorganización de negocio obligaría a reconstruir mapeos independientes nivel por nivel.

**VALOR DIFERENCIAL:** la evaluación de statements con cortocircuito es un detalle técnico que cambia cómo se debe diseñar el orden de las reglas — vale la pena explicarlo explícitamente en cualquier taller de diseño de taxonomía para evitar mapeos que "funcionan pero en el orden equivocado". El límite de 10 Business Dimensions es una restricción de diseño a anticipar: si el cliente ya visualiza más de 10 categorías de negocio distintas, la conversación correcta es sobre consolidación o resolución vía HBM, no sobre pedir más dimensiones planas. El modelo de permisos de tres niveles (Admin/Edit/View) es relevante para clientes con gobernanza descentralizada, donde distintos equipos necesitan crear sus propias métricas sin poder alterar las de otros.

## Documentos fuente

- Business Mapping — `kb/02-product-docs/apptio-cloudability-standard/en/spend-business-mapping.md`
- Organize Data Using Hierarchical Business Mappings — `kb/02-product-docs/apptio-cloudability-standard/en/mapping-organize-data-using-hierarchical-business-mappings.md`
- Structure of a Business Mapping (API) — `kb/02-product-docs/apptio-cloudability-standard/en/point-cloudability-structure-business-mapping.md`
- Fuente oficial: https://www.ibm.com/docs/en/cloudability-commercial/cloudability-standard/saas?topic=spend-cloudability-business-mapping

*Nota: versión en español/portugués se genera en una siguiente pasada.*
