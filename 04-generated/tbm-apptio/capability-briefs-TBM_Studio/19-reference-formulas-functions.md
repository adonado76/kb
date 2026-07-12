---
tbm_concept: "Reference: Formulas and Functions — sintaxis del lenguaje de fórmulas de TBM Studio y catálogo de ~120 funciones agrupadas por tipo"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-tbm-studio
status: draft
generated_from:
  - "kb/02-product-docs/apptio-tbm-studio/en/ (123 documentos bajo Reference > Formulas and functions)"
last_updated: "2026-07-07"
---
# Reference: Formulas and Functions — Cómo Apptio TBM Studio Aborda Esta Capacidad

## Nota de alcance

Esta es la categoría más grande de todo el proyecto TBM Studio: **123 documentos**, de los cuales ~120 son páginas de referencia de una sola función. Como con la categoría 18, este brief funciona como **catálogo organizado por tipo de función**, no como narrativa de cada función individual — el detalle exacto de sintaxis y parámetros de cada una vive en su documento fuente correspondiente y debe consultarse ahí directamente al construir una fórmula real.

## El concepto

El motor de fórmulas es el lenguaje de expresión que sustenta las métricas calculadas (ya vistas en Model Architecture), los Custom Formulas del New Report Studio, y buena parte de la lógica de transformación de datos — un "Excel embebido" con funciones propias, algunas específicas del dominio TBM (LookupObjectTotalAllocated, ProjectExists) que no tienen equivalente en hojas de cálculo tradicionales.

## Cómo lo resuelve Apptio TBM Studio

**Fundamentos del lenguaje, documentados antes del catálogo de funciones**: Introduction to formulas and functions, Syntax for formulas and functions, Data lookup (el patrón especial para traer valores numéricos sumados en vez de "{Various}" cuando hay múltiples coincidencias — mencionado explícitamente en la referencia de la función Lookup), Referencing column names, Operators, String concatenation, y Updated Eval Formulas. Dos índices de navegación: **Functions: Annotated list** (listado con descripción) y **Functions - Where used matrix** (dónde se puede usar cada función — no todas aplican en todos los contextos).

**El catálogo de ~120 funciones, agrupado por tipo funcional:**

**Lookup y referencia cruzada (14 funciones)** — el grupo más grande y más específico del dominio TBM: `Lookup`, `Lookup_Wild` (con soporte de expresiones regulares), `LookupContains`, `LookupEx` (crea una fila nueva por cada valor de retorno, en vez de devolver "{Various}"), `Lookup_From_Editable`, `LookupFromPath`, `LookupMetric`, y cuatro funciones específicas de asignación de modelo: `LookupObjectTotalAllocated`, `LookupObjectTotalValue`, `LookupObjectUnitAllocated`, `LookupObjectUnitValue` — estas últimas cuatro solo tienen sentido en el contexto del motor de asignación ya documentado en Model Architecture, permitiendo que una fórmula consulte directamente cuánto se asignó (o el valor unitario) desde/hacia un objeto del modelo específico.

**Fecha y tiempo (20 funciones)** — `Annual`, `Annualize`, `CurrentDate`, `DateFormat`, `DateSum`, `Days`, `DurationOfMonth`, `Elapsed`, `GetTimeOffset`, `Hours`, `Minutes`, `Months`, `Now`, `Period`, `PeriodsInHalf`, `PeriodsInQuarter`, `PeriodsInYear`, `PreviousMonth`, `PreviousYear`, `Quarter`, `QuarterToDate`, `TimePeriod`, `YearToDate` — el soporte extenso de este grupo refleja la naturaleza mes-céntrica de la plataforma ya documentada en Data Architecture.

**Texto y cadenas (16 funciones)** — `CapFirstLetter`, `Find`, `Left`, `Len`, `Lower`, `Mid`, `Plural`, `Pluralize`, `Replace`, `ReplaceRegex`, `Right`, `Search`, `Split`, `SplitEx`, `Substitute`, `Trim`, `Upper`.

**Matemáticas y agregación (18 funciones)** — `Abs`, `Average`, `Large`, `LargeIf`, `Max`, `Min`, `Mod`, `Percentile`, `Power`, `Rand`, `Ratio`, `Round`, `Small`, `SmallAcrossTime`, `SmallIf`, `SLN` (depreciación lineal — Straight-Line, conectando directamente con el concepto de depreciación ya visto en Costing Standard), `Sum`, `SumIf`, `SumIfHierarchy` (agregación respetando estructura jerárquica).

**Consulta de metadata y sistema (16 funciones)** — `ColumnExists`, `DomainName`, `GetGroupbyColumn`, `GetInfo`, `GetLastFilterColumn`, `GetLastFilterValue`, `GetLastPublishTime`, `GetNextPublishTime`, `GetReportName`, `GetReportPath`, `IsNumeric`, `ObjectName`, `ProjectExists`, `ProjectName`, `Row`, `RowCount`, `RowCount_EditableTable()`, `TableInfo`, `TableMatch`, `UniqueCount`, `UniqueValues` — funciones que consultan el estado del sistema/reporte en sí, no solo los datos.

**Formato y visualización (9 funciones)** — `Bullet`, `Icon`, `NumberFormat`, `Sparkline`, `StatusIcon` — generan elementos visuales (íconos de estado, mini-gráficos de tendencia) directamente desde una fórmula, sin necesidad de configuración de componente separada.

**Moneda (2 funciones)** — `ConvertCurrencyFromBase`, `ConvertCurrencyToBase` — soporte de multi-moneda a nivel de fórmula, complementario a la configuración de multi-moneda ya vista en Administration.

**Lógica condicional y control (3 funciones)** — `If`, `Eval` (evaluación dinámica de expresión), `EvalWiki`.

**Operaciones de tabla (4 funciones)** — `CopyTable`, `Undrill`, `Use_Map_Grid`, `Use_Map_Table`.

**Especializadas/otras (8 funciones)** — `DynamicColumn()`, `IPLookup` (resolución de dirección IP — un caso de uso poco común fuera de contextos de red/infraestructura), `Key`, `Recurring Publish`, `Trunc`, `Untag`, `Value`.

## Por qué importa en una conversación con el cliente

Las cuatro funciones `LookupObjectTotal*`/`LookupObjectUnit*` son el puente técnico entre el mundo de fórmulas y el motor de asignación — vale la pena mencionarlas explícitamente a cualquier desarrollador o power user del cliente que necesite construir una métrica calculada que reaccione al resultado de una asignación, en lugar de asumir que solo se puede acceder al modelo vía la interfaz visual.

El grupo de funciones de formato/visualización (Bullet, Icon, Sparkline, StatusIcon) generables directamente desde fórmula es un acelerador de productividad de reporte que vale la pena demostrar en cualquier sesión de diseño — evita depender exclusivamente de componentes de visualización separados para indicadores visuales simples.

La combinación de `SLN` (depreciación lineal) junto a las funciones de fecha ya extensas confirma que TBM Studio puede replicar, a nivel de fórmula, la misma lógica de depreciación de activos ya vista en Costing Standard — relevante para cualquier cliente que necesite modelar TCO de activos directamente en TBM Studio sin depender de Costing Standard para ese cálculo específico.

## Documentos fuente

Los ~120 documentos de función individuales, más 7 documentos de fundamentos del lenguaje, viven en `kb/02-product-docs/apptio-tbm-studio/en/`, bajo la ruta de breadcrumb `Reference > Formulas and functions`. El listado completo de topic-slugs está disponible en `inventory/ibm/apptio/tbm-studio/DOCUMENT_CATALOG.yaml` filtrando por ese breadcrumb.

*Nota: se detectaron 3 documentos en esta categoría cuyo título no se extrajo limpiamente del front-matter (aparecen como "***"), consistente con un problema de parseo ya visto en la base de conocimiento de Costing Standard — requieren confirmación manual contra el archivo fuente si se necesita su contenido específico.*

*Nota: versión en español/portugués se genera en una siguiente pasada. Este brief usa un formato de catálogo condensado, diferente al resto del proyecto, dado el volumen de la categoría (123 documentos) — ver nota de alcance al inicio.*
