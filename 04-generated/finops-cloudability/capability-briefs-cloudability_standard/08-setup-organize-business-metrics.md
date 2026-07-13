---
tbm_concept: "Business Metrics (métricas evaluadas al momento de la ingesta, que aumentan la data de facturación con data propia del cliente)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - apptio-cloudability-standard
status: draft
generated_from:
  - kb/02-product-docs/apptio-cloudability-standard/en/mapping-business-metrics-in-cloudability.md
last_updated: "2026-07-13"
---
# Setup — Organize - Business Metrics — Cómo IBM Cloudability Standard Aborda Esta Capacidad

## El concepto

Business Metrics es una extensión de Business Mappings enfocada no en categorizar (Business Dimensions) sino en **cuantificar** — permite a los equipos de FinOps aumentar la data de facturación nativa con data propia del negocio (ej. número de transacciones, usuarios activos, unidades producidas) para poder calcular métricas de unit economics que ningún proveedor de nube expone por sí solo.

## Cómo lo resuelve IBM Cloudability Standard

**Se evalúan al momento de la ingesta**, aplicándose fila por fila igual que una Business Dimension — comparten el mismo motor de reglas (`statements`, `matchExpression`/`valueExpression`, `kind` para distinguir el tipo de resultado) que Business Mappings, pero el resultado es un valor numérico en vez de una categoría de texto.

**Interfaz dedicada, unificada con Business Mappings.** Business Metrics se gestiona desde una pestaña propia junto a Business Mappings en la UI (lanzamiento de interfaz de gestión dedicada, evolucionando desde una fase beta previa).

**Límite documentado: hasta 5 Business Metrics por cuenta.**

**Casos de uso explícitos: cálculo de ahorros ("Calculate Savings") y otras mediciones custom** — formulas para tipos de ahorro u otras métricas que se combinan con la data de costo/uso ya existente.

**Gestión programática completa vía API**, documentada bajo el mismo Business Mappings End Point que Business Dimensions — para equipos que prefieren gestionar reglas de forma automatizada en vez de manualmente en la interfaz.

**Compatibilidad con Cost Sharing en cualquier moneda.** Las reglas de reparto de costo (Cost Sharing) ahora pueden asignarse sobre cualquier Business Metric denominada en moneda (currency) presente en el entorno del cliente — excluyendo Business Metrics no monetarias — lo que permite asignación de costo compartido más precisa en contextos distintos al costo bruto de nube.

## Por qué importa en una conversación con el cliente

**RETOS QUE RESUELVE:** cuando un cliente pregunta "¿cuánto nos cuesta cada transacción/usuario/pedido?" y esa data de volumen de negocio no vive en ningún sistema de facturación de nube, Business Metrics es el mecanismo para inyectar esa data propia y calcularla junto con el costo — sin esto, la conversación de unit economics quedaría atrapada en spreadsheets externos desconectados de los reportes de Cloudability.

**VALOR DIFERENCIAL:** el límite de 5 Business Metrics por cuenta es una restricción de diseño concreta a anticipar — si el cliente tiene más de 5 métricas de negocio candidatas, la conversación de priorización debe darse temprano en el discovery. La distinción entre Business Metrics (ingesta, por fila, con límite bajo de 5) y Calculated Metrics (consulta, sobre agregado, ver brief separado) es la pregunta técnica clave antes de recomendar cuál usar para un KPI específico — confundirlas lleva a modelar la métrica equivocada desde el inicio.

## Documentos fuente

- Business Metrics in Cloudability — `kb/02-product-docs/apptio-cloudability-standard/en/mapping-business-metrics-in-cloudability.md`
- Fuente oficial: https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=mapping-business-metrics-in-cloudability

*Nota: versión en español/portugués se genera en una siguiente pasada.*
