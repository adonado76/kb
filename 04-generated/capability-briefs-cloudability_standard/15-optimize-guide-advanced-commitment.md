---
tbm_concept: "Optimize — Guide to Advanced Commitment Functionality (modales de transparencia de KPI, diferencias de facturación entre Savings Plans y Reserved Instances, y el programa Spend CUD de GCP)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - apptio-cloudability-standard
status: draft
generated_from:
  - kb/02-product-docs/apptio-cloudability-standard/en/optimize-guide-advanced-commitment-functionality.md
  - kb/02-product-docs/apptio-cloudability-standard/en/functionality-net-savings-modal.md
  - kb/02-product-docs/apptio-cloudability-standard/en/functionality-coverage-modal.md
  - kb/02-product-docs/apptio-cloudability-standard/en/functionality-understanding-commitments-using-cloudability-native-reporting.md
  - kb/02-product-docs/apptio-cloudability-standard/en/functionality-supplemental-guide-gcps-spend-cud-program.md
  - kb/02-product-docs/apptio-cloudability-standard/en/functionality-advanced-commitment-faq.md
last_updated: "2026-07-09"
---
# Optimize — Guide to Advanced Commitment Functionality — Cómo IBM Cloudability Standard Aborda Esta Capacidad

## El concepto

Confiar en un KPI de ahorro sin entender cómo se calculó es un riesgo real cuando ese número se usa para justificar decisiones de compra multi-año. Este capítulo documenta los mecanismos de transparencia (modales de detalle) que exponen exactamente cómo Cloudability calcula sus métricas de compromiso más importantes, más el detalle técnico de facturación que explica por qué Savings Plans y Reserved Instances necesitan tratamiento distinto en cualquier ejercicio de asignación de costo.

## Cómo lo resuelve IBM Cloudability Standard

**Net Savings Modal — transparencia sobre el KPI más importante del programa de compromisos.** Fórmula explícita: **Savings − Waste = Net Savings**, donde Savings es la diferencia entre el ODE cubierto y el costo del compromiso, y Waste es el valor de compromisos no utilizados. Un histograma diario (barras verdes cuando el ahorro supera el desperdicio, rojas cuando es al revés) permite un diagnóstico visual inmediato: **"todo verde"** indica salud óptima; **"verde con rojo periódico"** sugiere estacionalidad (revisar si conviene un compromiso de gasto más flexible en vez de uno de recurso); **"picos rojos frecuentes"** es la señal explícita de sobrecompra sistemática, ameritando evaluar intercambios/convertibles o reducir el tamaño/plazo de compras futuras.

**Coverage Modal — la descomposición más granular del capítulo, expresada enteramente en términos de ODE (On-Demand Equivalent) para permitir comparación pareja.** Distingue **Resource-based Commitments** (descuento por comprometerse a cierto uso — RI, CUD) de **Spend-based Commitments** (descuento por comprometerse a cierto gasto — Savings Plan, CUD flexible). El desglose de cobertura separa Resource Covered, Spend Covered, y las zonas de solapamiento de elegibilidad (Spend Covered pero también elegible para Resource, y viceversa) — permitiendo identificar oportunidades específicas: alto solapamiento Spend→Resource sugiere convertir demanda hacia compromisos de recurso (normalmente con mayor tasa de descuento); alto "Resource Exclusive Uncovered" señala familias de instancia o regiones específicas sin cobertura de recurso, donde un compromiso de gasto simplemente no aplicaría.

**Understanding Commitments Using Native Reporting — la mecánica de facturación que distingue Savings Plans de RIs, con implicación práctica directa para asignación de costo.** Diferencia central: RIs comprometen a *horas de instancia*; Savings Plans comprometen a *dólares por hora*. En el archivo de facturación detallado (CUR), las horas cubiertas por SP aparecen como líneas On-Demand normales más una línea especial de **Negation** que anula el costo a nivel mensual — lo cual significa que, sin tratamiento especial, cualquier asignación de costo basada en tags o resource ID vería costo On-Demand completo en horas cubiertas por SP, pero costo fuertemente reducido en horas cubiertas por RI — una inconsistencia real de asignación. **La solución que ofrece Cloudability**: la métrica **Cost (List)** elimina completamente el efecto de cualquier descuento por compromiso (comparación predecible); la métrica **Cost (Amortized)** distribuye el costo completo (incluyendo el componente upfront) a nivel de recurso, de forma consistente entre RIs y SPs — la base correcta para cualquier ejercicio de True Cost.

**Supplemental Guide to GCP's Spend CUD Program — un procedimiento operativo puntual**, documentando tres cohortes de clientes según cómo migraron al nuevo programa de CUD de gasto de GCP (forzada, voluntaria comunicada, voluntaria no comunicada), con el proceso exacto de reprocesamiento de datos retroactivo requerido en cada caso.

## Por qué importa en una conversación con el cliente

La fórmula Savings − Waste = Net Savings, junto con el patrón visual de interpretación (verde/rojo), es la herramienta de diagnóstico más directa y visual para explicarle a un stakeholder no técnico si su programa de compromisos está funcionando bien o mal — sin necesidad de explicar la mecánica de facturación subyacente.

La distinción Cost (List) vs. Cost (Amortized) es un detalle crítico a comunicar antes de cualquier ejercicio de chargeback/showback con compromisos activos — sin la métrica Amortized correcta, un equipo que "por casualidad" tiene su uso cubierto por RI en vez de Savings Plan verá un costo asignado artificialmente más bajo, sesgando cualquier comparación de eficiencia entre equipos.

El Coverage Modal, con su desglose de elegibilidad cruzada (Resource vs. Spend), es el material correcto para justificar ante un CFO por qué la estrategia de compromisos de una organización debería usar una mezcla de ambos tipos, no solo uno — con evidencia cuantitativa de dónde exactamente cada tipo cerraría la brecha de cobertura no capturada por el otro.

## Documentos fuente

- Guide to Advanced Commitment Functionality (índice) — `kb/02-product-docs/apptio-cloudability-standard/en/optimize-guide-advanced-commitment-functionality.md`
- Net Savings Modal — `kb/02-product-docs/apptio-cloudability-standard/en/functionality-net-savings-modal.md`
- Coverage Modal — `kb/02-product-docs/apptio-cloudability-standard/en/functionality-coverage-modal.md`
- Understanding Commitments Using Cloudability Native Reporting — `kb/02-product-docs/apptio-cloudability-standard/en/functionality-understanding-commitments-using-cloudability-native-reporting.md`
- Supplemental Guide to GCP's Spend CUD Program — `kb/02-product-docs/apptio-cloudability-standard/en/functionality-supplemental-guide-gcps-spend-cud-program.md`
- Advanced Commitment Functionality FAQ — `kb/02-product-docs/apptio-cloudability-standard/en/functionality-advanced-commitment-faq.md`

*Nota: versión en español/portugués se genera en una siguiente pasada.*
