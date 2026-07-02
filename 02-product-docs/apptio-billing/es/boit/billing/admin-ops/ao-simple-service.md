---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Showback de servicio simple"
breadcrumb:
  - "Billing"
  - "Administración y operaciones"
source_path: "boit/billing/admin-ops/ao-simple-service.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Showback de servicio simple

**Cuándo utilizarlo**

- Primera implementación de facturación en la que la prioridad es la transparencia, no los ingresos internos.
- Las partes interesadas quieren saber «quién consume qué» y «cuánto costaría» sin publicar diarios.

**Forma**

- Un catálogo disciplinado y relativamente pequeño de servicios o productos.
- Unidades y tarifas mantenidas en un pequeño número de tablas.
- Los mapas de consumo se asignan directamente a los servicios y consumidores.
- Diarios disponibles, pero no utilizados para publicar.

**Elementos clave**

- Tabla de ofrendas: nombres y unidades de servicio claros.
- Tabla de consumo: consumidor × servicio × período × unidades.
- Tabla de tarifas: una tarifa por servicio por período.
- Resultados de facturación: se utilizan únicamente para facturas y vistas resumidas.

**Informes típicos**

- Resumen del estilo de facturación por consumidor y servicio.
- Vistas de tendencias que muestran los cargos a lo largo del tiempo.
- Informes de control de calidad para mapeos faltantes y valores atípicos.

**Notas de implementación**

- Mantenga las unidades y las tarifas sencillas y fáciles de explicar.
- No se complique demasiado con el modelado de dominios para un patrón de showback puro; céntrese en la claridad.
