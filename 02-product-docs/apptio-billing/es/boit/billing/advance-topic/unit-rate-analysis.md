---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Análisis y optimización de la tasa unitaria"
breadcrumb:
  - "Billing"
  - "Temas avanzados"
source_path: "boit/billing/advance-topic/unit-rate-analysis.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Análisis y optimización de la tasa unitaria

Las tarifas unitarias suelen ser el tema central de las conversaciones sobre facturación. Esta subsección se centra en cómo analizarlos y ajustarlos a lo largo del tiempo.

## Análisis de la tasa unitaria básica

Preguntas clave:

- ¿Cuál es la tarifa unitaria para cada oferta de este período?
- ¿Cómo ha cambiado esa tarifa unitaria a lo largo del tiempo?
- ¿Los cambios están motivados por decisiones relacionadas con los costes, el volumen o los precios?

Entradas típicas:

- **unidades**
  - De las tablas de consumo de facturación.
- **Cargos**
  - Desde las tablas de salida de facturación.
- **Coste por unidad**
  - A partir de los resultados de cálculo de costes, cuando estén disponibles.

Patrones básicos de análisis:

- Calcule la tarifa unitaria como Cargo / Unidades para cada oferta y período.
- Comparar la tasa unitaria del período actual con:
  - Período anterior.
  - Mismo período del año pasado.
- Compare la tarifa unitaria con el coste por unidad (si el coste está disponible).

Utilice esta vista para identificar:

- Ofertas con tarifas unitarias en aumento y volúmenes estables o en descenso.
- Ofertas con caídas repentinas en la tarifa unitaria que pueden indicar problemas de configuración de datos o tarifas.

## Comprender los movimientos de las tasas unitarias

Factores comunes que influyen en los cambios en las tarifas unitarias:

- **Cambios de coste**
  - Aumentos de los costes ascendentes en las torres tecnológicas o los proveedores.
  - Cambios en la lógica de asignación en el cálculo de costes.
- **Cambios de volumen**
  - Los costes fijos se distribuyen entre un número significativamente mayor o menor de unidades.
  - Migraciones o jubilaciones puntuales.
- **Cambios en los precios**
  - Decisiones explícitas para cambiar las tarifas, ajustar la recuperación o introducir descuentos.

Patrones de informes útiles:

- Para cada oferta y período:
  - Columnas de unidades, coste por unidad, precio por unidad y variación.
- Gráficos de tendencias:
  - Tasa unitaria a lo largo del tiempo junto con la tendencia del volumen.

Utilice estos patrones para separar los problemas estructurales (cambios en los datos o en el modelo) de las decisiones empresariales conscientes (nueva estrategia de tarifas).

## Palancas de optimización

Cuando las tarifas unitarias parecen incorrectas, las palancas típicas son:

- Mejorar los factores que influyen en los costes y las asignaciones en el cálculo de costes.
- Ajustar el diseño del servicio o la estructura del catálogo.
- Cambiar las tasas o los objetivos de recuperación.
- Reducir los costes subyacentes (por ejemplo, renegociación con proveedores, optimización de la nube).

La facturación refleja el comportamiento de la tarifa unitaria. El trabajo de implementación para optimizarlo se suele realizar en modelos de cálculo de costes, diseños de dominio y decisiones de abastecimiento.
