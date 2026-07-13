---
concept: "Calculated Metrics (métricas evaluadas al momento de la consulta, sobre datos ya agregados, con validación estricta de expresión)"
practice: finops
language: en
doc_type: capability_brief
products_covered:
  - apptio-cloudability-standard
status: draft
generated_from:
  - kb/02-product-docs/apptio-cloudability-standard/en/spend-calculated-metrics.md
last_updated: "2026-07-13"
---
# Setup — Organize - Calculated Metrics — Cómo IBM Cloudability Standard Aborda Esta Capacidad

## El concepto

Calculated Metrics son métricas reutilizables y definidas por el usuario que combinan métricas estándar, Business Metrics, constantes numéricas y operaciones aritméticas básicas — a diferencia de Business Metrics (evaluadas por fila en la ingesta), estas se evalúan **al momento de la consulta**, sobre el resultado ya agregado que se muestra en un Dashboard o Reporte. Esto las hace la herramienta correcta para KPIs de negocio como costo por recurso, costo por clúster, o cualquier ratio que combine dos métricas ya calculadas.

## Cómo lo resuelve IBM Cloudability Standard

**Gestión centralizada dentro del área de producto Business Mappings.** Crear, editar y eliminar Calculated Metrics desde un solo hub central, definiéndolas una vez para reutilizarlas de forma consistente en todos los dashboards y reportes — elimina la necesidad de reconstruir la misma fórmula repetidamente.

**Reglas de validación estrictas y documentadas explícitamente para el campo de expresión:**
- **Nombre**: debe ser único dentro de la organización y no puede coincidir con nombres de métricas base ya existentes.
- **Expresión**: debe usar operadores válidos y nombres de métrica válidos para la organización.
- **Tipo de fuente (Source Type)**: todas las métricas referenciadas en la expresión deben coincidir con el tipo de fuente declarado — **Cost** o **Usage** — no se pueden mezclar métricas de costo con métricas de uso en la misma fórmula.
- **Paréntesis**: deben estar correctamente balanceados en las expresiones.
- **Nombres de métrica**: pueden contener letras, dígitos y guiones bajos.
- **Números decimales**: deben usar punto (`.`) como separador decimal.

**Operaciones aritméticas soportadas**: suma, resta, multiplicación, división, y combinación con constantes numéricas — ejemplos documentados incluyen `unblended_cost * 0.8`, `(unblended_cost + 100) / 2`, y fórmulas que combinan una Business Metric con una métrica de costo estándar como `business_metric9 / total_adjusted_amortized_cost * bytes_transferred`.

**Permisos de tres niveles**: **Admin** (acceso completo — crear, editar, eliminar todas las métricas), **Edit** (crear y modificar solo las métricas propias), **View** (acceso de solo lectura).

**Feature opt-in — no viene activada por defecto.** Si Calculated Metrics no está habilitada para la organización, todas las llamadas de API y el acceso a la interfaz quedan restringidos; hay que contactar al administrador de Cloudability o al Technical Account Manager para activarla.

**Gestión programática completa vía API** (crear, obtener, actualizar, eliminar), documentada bajo el Calculated Metrics End Point dedicado.

## Por qué importa en una conversación con el cliente

**RETOS QUE RESUELVE:** cuando un cliente necesita un KPI que combine múltiples métricas ya existentes (ej. costo efectivo amortizado dividido entre una Business Metric de volumen de negocio) sin recalcular esa fórmula manualmente en cada reporte, Calculated Metrics centraliza la definición una sola vez y la propaga consistentemente — evitando el riesgo de que dos analistas calculen "lo mismo" con fórmulas ligeramente distintas.

**VALOR DIFERENCIAL:** la restricción de que el feature es opt-in (no viene activo por defecto) es un dato operativo importante a confirmar temprano — si el cliente asume que ya tiene acceso y no lo tiene habilitado, hay que anticipar ese paso con su CSM antes de comprometerse a un diseño de métricas. Las reglas de validación de expresión (tipo de fuente consistente, paréntesis balanceados, separador decimal con punto) son la lista de verificación correcta antes de entregarle al cliente una fórmula que fallará en la interfaz por un detalle de sintaxis.

## Documentos fuente

- Calculated Metrics — `kb/02-product-docs/apptio-cloudability-standard/en/spend-calculated-metrics.md`
- Fuente oficial: https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=spend-calculated-metrics

*Nota: versión en español/portugués se genera en una siguiente pasada.*
