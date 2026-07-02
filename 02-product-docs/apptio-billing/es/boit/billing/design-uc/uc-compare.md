---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Compare el plan, los datos reales y el precio de un servicio clave"
breadcrumb:
  - "Billing"
  - "Patrones de diseño y casos de uso"
source_path: "boit/billing/design-uc/uc-compare.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Compare el plan, los datos reales y el precio de un servicio clave

Nota: **Principalmente estándar de facturación; se puede adaptar con Essentials si se modelan los datos del plan.**

**Problema**

Desea comprender si un servicio clave está recuperando menos o más de lo previsto en relación con el plan y el coste.

**Entradas**

- Coste real por servicio (de Costing)
- Plan o presupuesto por servicio (a partir de herramientas de planificación o tablas)
- Precio por unidad del servicio
- Unidades y cargos reales de facturación

**Pasos**

1. Confirme **que los datos del plan** se han cargado y se ajustan a la estructura de servicios y consumidores utilizada en Facturación.
2. Abrir un **informe de Plan vs Real vs Precio** :
   - Filtrar por servicio y períodos relevantes (por ejemplo, año hasta la fecha).
3. Para cada período, revise:
   - Coste del plan por unidad.
   - Coste real por unidad.
   - Precio por unidad.
   - Columnas de varianza:
     - Real frente a previsto.
     - Precio frente a coste.
4. Identificar patrones:
   - Recuperación persistente insuficiente (precio < coste).
   - Recuperación persistente (precio > coste).
   - Grandes oscilaciones debido al cambio de volumen.
5. Resuma los hallazgos y las posibles medidas:
   - Ajustar las tarifas.
   - Ajuste los factores de coste o las asignaciones en el cálculo de costes.
   - Revisar el diseño del servicio o los patrones de consumo.

**Informes clave**

- Informe sobre el plan de nivel de servicio frente al real frente al precio
- Informe de variación a nivel de consumidor para el mismo servicio
- Vista de tendencia de la tarifa unitaria para el servicio
