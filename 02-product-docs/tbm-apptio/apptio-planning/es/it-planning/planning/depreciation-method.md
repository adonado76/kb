---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Métodos de amortización"
breadcrumb:
  - "Planning"
  - "Planificación de activos"
source_path: "it-planning/planning/depreciation-method.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Métodos de amortización

Apptio La planificación admite múltiples métodos de depreciación para ayudarle a modelar con precisión cómo se imputan los costes de los activos fijos a lo largo del tiempo. La depreciación convierte un gasto de capital ( CapEx ) en un gasto operativo ( OpEx ) a lo largo de la vida útil del activo.

Puede seleccionar uno de los siguientes métodos admitidos:

- [Línea recta](#deprecationmethod__SL)
- [Línea recta por días naturales](#deprecationmethod__slcud)
- [Doble descenso](#deprecationmethod__dd)
- [Saldo decreciente Períodos pares](#deprecationmethod__dbep)
- [Saldo decreciente por días naturales](#deprecationmethod__dbucd)
- [Amortización manual](#deprecationmethod__md)

## Línea recta

Distribuye uniformemente el coste del activo a lo largo de su vida útil.

**Fórmula:**

**Importe de la amortización** = (Precio de compra × (1 - Valor residual)) ÷ Vida útil del activo

**Vida del activo** = Duración en meses

**Valor residual %** = Porcentaje del coste original del activo que se espera que permanezca al final de su vida útil.

**Ejemplo:**

Precio del activo = 40.000

Vida útil = 12 meses

Valor residual %: 0

**Depreciación mensual** = 40,000 × (1 – 0) ÷ 12 = **$3,333**

## Línea recta por días naturales

Aplica la amortización lineal pero distribuye el gasto proporcionalmente en función del número de días naturales de cada mes.

Si la amortización comienza a mediados de mes o abarca meses con días diferentes (por ejemplo, enero frente a febrero), cada mes recibe un importe prorrateado basado en los días reales transcurridos en lugar de una división mensual uniforme.

Este método suele utilizarse cuando la política contable requiere una mayor precisión para períodos parciales.

## Doble descenso

El método de doble amortización decreciente es una técnica de amortización acelerada que registra mayores gastos de amortización durante los primeros años de vida de un activo. Calcula la depreciación multiplicando el valor contable inicial del activo por el doble de la tasa de depreciación lineal. Este método suele utilizarse para activos que se deprecian rápidamente o para reducir la cuota tributaria en los primeros años.

**Fórmula:**

**Importe de la amortización** = 2 × (1 ÷ Vida útil del activo) × Valor contable del período inicial

**Vida del activo** = Duración en meses

**Valor residual %** = Porcentaje del coste original del activo que se espera que permanezca al final de su vida útil. El cálculo del doble saldo decreciente no tiene en cuenta el valor residual en la amortización de cada periodo, sin embargo, si el valor contable va a caer por debajo del valor residual, el último periodo se ajustará para que termine al valor residual.

**Valor contable del período inicial** (calculado mensualmente) = Importe de compra - Amortización acumulada hasta la fecha

**Ejemplo:**

Precio del activo = 40.000

Vida útil = 12 meses

Valor residual % = 0

- **P1** = 2 × (1 ÷ 12) × (40,000 - 0) = **$6,667**

- **P2** = 2 × (1 ÷ 12) × (40,000 - 6,667) = **$5,556**

- **P3** = 2 × (1 ÷ 12) × (40,000 - 6,667 - 5,556) = **$4,955**

- **Etcétera.**

**Importante:** El método decreciente doble recalcula el valor contable inicial **al principio de cada periodo**, no anualmente. Si desea modelar un método tradicional de doble decrecimiento, utilice **en su lugar el Saldo decreciente con una tasa de saldo del 200 %.**

## Saldo decreciente Períodos pares

Método flexible de depreciación acelerada que utiliza una **Tasa de Balance** que usted define (por ejemplo, 150%, 200%).

**Fórmula:**

**Importe de la amortización** = Valor contable del período inicial × [Tasa de equilibrio × ( 1 ÷ Vida útil del activo)]

**Valor contable del período inicial** (calculado anualmente) = Precio de compra - Amortización acumulada hasta la fecha

**Vida del activo** = Duración en meses

**Valor residual %** = Porcentaje del coste original del activo que se espera que permanezca al final de su vida útil. El cálculo del doble saldo decreciente no tiene en cuenta el valor residual en la amortización de cada periodo, sin embargo, si el valor contable va a caer por debajo del valor residual, el último periodo se ajustará para que termine al valor residual.

**Tasa de Saldo %** = La tasa de depreciación del activo.

Si se utiliza Saldo Decreciente con **Tasa de Saldo = 200%**, esto equivale al método Doble Decreciente. Esta es la forma recomendada de modelar el doble declive estándar en Apptio.

**Ejemplo:**

**Precio del activo:** 40.000 dólares

**Vida útil:** 36 meses

**Tasa de saldo %:** 200

**Valor residual %:** 0

- **P1 - P12** = 40.000 × 200% × (1 ÷ 36) = **$2.220 por mes**

- **Año 1 = 26.667**

- **P13 - P24** = (40.000 – 26.667) × 200% × (1 ÷ 36) = **$741 por mes**

- **Año 2 = 8.889**

- **P25 - P36** = (40.000 – 26.667 – 8.889) × 200% × (1 ÷ 36) = **$247 por mes**

- **Año 3 = 2.963**

## Saldo decreciente por días naturales

Este método aplica la fórmula de depreciación de saldo decreciente para calcular la depreciación total del año, pero luego distribuye esa depreciación entre los periodos proporcionalmente en función del número de días naturales de cada mes.

Mantiene el patrón de depreciación acelerada (mayor gasto al principio de la vida del activo), al tiempo que mejora la precisión del periodo ponderando cada mes según su número real de días.

## Amortización manual

Permite a los usuarios introducir directamente los importes de depreciación para cada período, en lugar de depender de los métodos calculados por el sistema. Esto proporciona una flexibilidad total para definir exactamente cómo deben distribuirse los costes a lo largo de los periodos.
