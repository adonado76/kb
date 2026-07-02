---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Estrategias de retroceso y corrección"
breadcrumb:
  - "Billing"
  - "Manual de puesta en marcha"
source_path: "boit/billing/go-live/gl-falback.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Estrategias de retroceso y corrección

A veces las cosas salen mal. Decida de antemano cómo los corregirá.

## Correcciones dentro del período

Úselo cuando se detecte un problema antes de que se emitan formalmente las facturas o se contabilicen los diarios.

Acciones típicas:

- Corregir datos (por ejemplo, consumo, mapeo, tarifas).
- Vuelva a ejecutar los modelos de facturación pertinentes en Staging y Production.
- Revalidar informes principales y vistas de control de calidad.
- Reexportar diarios si procede.

Intenta evitar repetidas repeticiones parciales durante el mismo periodo; agrupa las correcciones siempre que sea posible.

## Correcciones posteriores a la publicación

Úselo cuando se detecte un problema después de compartir las facturas o publicar los diarios.

Opciones:

- **Solo facturación** (showback):
  - Corrija el modelo y los datos para el próximo período.
  - Documente la corrección y, si es necesario, aplique un ajuste único en la factura del siguiente periodo.
- **Contrapartida** (diarios):
  - Si el error es importante, prepare los asientos de corrección en coordinación con Finanzas.
  - Utilice Facturación para calcular las diferencias:
    - Lo que se facturó.
    - Lo que se debería haber facturado.
    - Diferencia por consumidor y cuenta.

En ambos casos, asegúrese de que se aborde la causa raíz para que el mismo problema no se repita cada mes.
