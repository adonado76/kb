---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Contracargo con diarios"
breadcrumb:
  - "Billing"
  - "Administración y operaciones"
source_path: "boit/billing/admin-ops/ao-chargeback-journal.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Contracargo con diarios

**Cuándo utilizarlo**

- El departamento financiero quiere tratar los ingresos por facturación como ingresos y gastos internos.
- Las entradas de devoluciones se contabilizan en el libro mayor.

**Forma**

- La misma estructura básica que el showback, más una asignación estable a los segmentos GL o Finanzas.
- Control de calidad mensual más riguroso en torno a los totales y la publicación de las revistas.

**Elementos clave**

- Tabla de salida de facturación ampliada con:
  - Campos de la cuenta GL.
  - Centro de costes y otros segmentos financieros.
  - Cualquier tipo de documento o campos de referencia requeridos por Finanzas.
- Informes de diarios adaptados al formato de Finanzas.

**Informes típicos**

- Informes de facturación para conversaciones con consumidores.
- Informe de exportación del diario con detalles a nivel de cuenta.
- Informe de conciliación:
  - Total de facturación frente a total del diario frente a coste recuperable.

**Notas de implementación**

- Alinea las estructuras de consumidores y segmentos con Finanzas desde el primer día.
- Trate los cambios en las tarifas y los cambios en la asignación como eventos regulados, con historial de cambios.
