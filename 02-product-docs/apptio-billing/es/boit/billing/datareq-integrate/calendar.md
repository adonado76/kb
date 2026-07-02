---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Calendarios y períodos"
breadcrumb:
  - "Billing"
  - "Requisitos e integración de datos"
source_path: "boit/billing/datareq-integrate/calendar.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Calendarios y períodos

La facturación necesita una noción coherente de **los periodos** :

- La mayoría de las implementaciones son **mensuales**, a veces alineadas con el calendario fiscal.
- Cada registro de las tablas de consumo y tarifas debe hacer referencia a:
  - Un identificador de período (por ejemplo, AAAA-MM).
  - Posiblemente una clave del período fiscal si el calendario fiscal de la organización difiere de los meses naturales.

Consideraciones de diseño:

- Decida si la facturación se ajusta estrictamente al **calendario** fiscal, al **mes natural** o a un enfoque híbrido.
- Cuando se produzcan periodos parciales o eventos de transición (por ejemplo, puesta en marcha a mitad de mes), documente cómo se tratan:
  - Períodos divididos.
  - Ajustes puntuales.
  - Tarifas o unidades prorrateadas.

Si Costing ya utiliza un calendario fiscal, reutilice la misma estructura en Facturación para evitar trabajos de conciliación innecesarios.
