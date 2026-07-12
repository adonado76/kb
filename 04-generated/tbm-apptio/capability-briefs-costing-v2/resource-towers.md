---
tbm_concept: "Resource Towers (vista funcional del gasto de TI por torre/sub-torre, distinta de Cost Pool)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-costing-standard
status: draft
generated_from:
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/rt-overview.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/rt-reports.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/rt-getstart.md
  - 02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/ctf-ittowers-component.md
last_updated: "2026-07-05"
---
# Resource Towers — Cómo Apptio Costing Standard Aborda Esta Capacidad

## Una distinción de vocabulario TBM que vale la pena fijar temprano

El propio Overview de este módulo establece una distinción conceptual central en toda la práctica TBM/ATUM: **Cost Pools clasifican el costo por qué es** (labor, software, hardware), mientras **Resource Towers clasifican el costo por dónde y cómo soporta el stack tecnológico** (Aplicaciones, Plataformas, Usuario Final, Data Center, Red, etc.). Son dos ejes ortogonales de la misma taxonomía ATUM — no alternativas, sino dimensiones complementarias. Un mismo dólar de gasto tiene tanto un Cost Pool (qué es) como una Resource Tower (dónde vive funcionalmente).

## El concepto

Ver el gasto de TI únicamente por tipo de expensa (cuánto gastamos en labor, cuánto en software) no responde la pregunta que un dueño de servicio realmente necesita: ¿cuánto cuesta funcionalmente operar el Data Center, o la capa de Red, o el soporte a Usuario Final? Sin una vista por torre funcional, es imposible comparar de forma consistente el gasto de un mes a otro a nivel de función tecnológica, ni identificar qué está impulsando el costo dentro de cada una.

## Cómo lo resuelve Apptio Costing Standard

**Cuatro casos de uso estándar**, todos orientados a análisis de variación y asignación de recursos: Monitor Period-over-Period Spend Changes (cambios mes a mes o trimestre a trimestre por torre y sub-torre), Analyze Budget Variance by Tower (comparar actual vs. presupuesto a nivel de torre/sub-torre), Identify Primary Cost Drivers (qué combinación de labor, vendor, activos y otros contribuyentes impulsa el gasto dentro de cada torre), y Support Resource Allocation Decisions (usar la vista por torre para decidir reasignación de recursos).

**Cuatro reportes, cada uno con un ángulo distinto sobre la misma taxonomía:**
- **IT Towers Review** — distribución de gasto por torre/sub-torre, comparación de alto nivel contra presupuesto, y qué aplicaciones tienen mayor consumo año a la fecha por torre.
- **IT Towers Performance** — vista comparativa en el tiempo, indicando si una torre está mejorando su eficiencia o experimentando presión de costo creciente (trimestre contra trimestre).
- **IT Towers Composition** — vista estructural: cómo se compone el costo de cada torre por cost pool (hardware, software, labor) y por proveedor.
- **IT Towers Planning** — vista prospectiva: actual vs. presupuesto vs. forecast, presupuesto remanente y proyección de agotamiento de presupuesto por torre.

**Un componente con tres prerrequisitos opcionales, no solo uno obligatorio.** CTF-IT Towers requiere obligatoriamente CTF-Cost Source, pero además se enriquece — de forma opcional — con CTF-Labor, CTF-Vendor y CTF-Fixed Assets, cada uno habilitando el mapeo de su tipo de costo específico hacia las torres/sub-torres. Esto significa que la calidad de los reportes de Resource Towers depende directamente de cuántos otros módulos ya estén instalados y mapeados — es, en cierto sentido, un módulo "consumidor" que se enriquece con el resto del ecosistema de componentes.

**El mapeo no es automático para todo — requiere trabajo deliberado de asignación.** La taxonomía de torres/sub-torres viene predefinida por ATUM y se carga automáticamente con el proyecto, pero **no todos los costos se asignan automáticamente a una torre** a través de los otros componentes. La organización típicamente debe: mapear centros de costo a torres/sub-torres, definir porcentajes de asignación cuando un centro de costo se relaciona con múltiples torres, y definir lógica de asignación separada para actuals y para presupuesto. Ejemplos concretos documentados: un centro de costo de operaciones de data center se mapea a Data Center → Enterprise Data Center; roles de ingeniero de red se mapean a Network → LAN; proveedores de seguridad gestionada se mapean a Security → Digital Security. Cuando no hay datos suficientes para asignar con precisión, la recomendación explícita del producto es **dejar el costo sin asignar en el objeto Cost Source, en vez de aplicar una asignación incompleta o incorrecta** — un principio de integridad de datos que vale la pena replicar en cualquier conversación de calidad de datos.

## Por qué importa en una conversación con el cliente

La distinción Cost Pool vs. Resource Tower es, junto con el glosario de Getting Started, uno de los conceptos fundacionales que hay que dejar absolutamente claro antes de cualquier conversación de reporting — es común que un cliente nuevo use ambos términos indistintamente, y la confusión se propaga a malinterpretar qué está mirando en cada reporte.

El principio de "no asignar sin datos suficientes, dejar el costo sin asignar en su lugar" es un argumento de credibilidad de datos importante: le dice al cliente que el modelo prefiere ser honesto sobre lo que no sabe, en lugar de forzar una asignación arbitraria que después resulta difícil de defender frente a un dueño de servicio que cuestiona su costo.

La dependencia de Resource Towers con Labor, Vendor y Fixed Assets es un buen argumento de secuenciación de proyecto: cuantos más de esos módulos estén ya instalados y bien mapeados, más rica será la vista de Resource Towers desde el primer día — vale la pena posicionar Resource Towers como un módulo a activar después de tener al menos Labor y Vendor funcionando, no como punto de partida aislado.

## Documentos fuente

- Resource Towers Overview — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/rt-overview.md`
- Resource Towers Reports — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/rt-reports.md`
  - IT Towers Review: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-it-towers-review
  - IT Towers Performance: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-it-towers-performance
  - IT Towers Composition: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-it-towers-composition
  - IT Towers Planning: https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=reports-it-towers-planning
- Resource Tower Getting Started — `02-product-docs/apptio-costing-standard/en/cost-transparency/it-financials/rt-getstart.md`
- CTF - IT Towers component: install and configure — `02-product-docs/apptio-costing-standard/en/cost-transparency/configuration/ctf-ittowers-component.md`

*Nota: las cuatro URLs de reportes son links reales embebidos en el contenido fuente original de IBM.*

*Nota: versión en español/portugués se genera en una siguiente pasada.*