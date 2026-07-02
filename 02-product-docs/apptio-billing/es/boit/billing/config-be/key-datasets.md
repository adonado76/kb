---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Conjuntos de datos y tablas clave"
breadcrumb:
  - "Billing"
  - "Configuración de los elementos esenciales de facturación (implementación)"
source_path: "boit/billing/config-be/key-datasets.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Conjuntos de datos y tablas clave

Billing Essentials depende de un pequeño número de tablas principales. Los nombres exactos pueden variar según la plantilla, pero los patrones son consistentes.

Categorías típicas:

- **Tabla de ofertas/servicios**
  - Almacena el catálogo de ofertas facturables.
  - Campos comunes:
    - Proporcionar identificación y nombre.
    - Unidad de medida.
    - Indicador activo/inactivo.
    - Indicador facturable (sí/no).
- **Maestro de consumidores**
  - Compartido con Costing o alineado con él.
  - Campos comunes:
    - Identificación y nombre del consumidor.
    - Jerarquía (por ejemplo, unidad de negocio, departamento, centro de costes).
    - Atributos opcionales como región, función o gerente.
- **Tabla de consumo**
  - Mantiene los volúmenes de uso por oferta y consumidor por período.
  - Campos comunes:
    - Punto.
    - Identificación del consumidor.
    - Ofrecer ID (o una clave asignada a él).
    - Unidades consumidas.

- **Tabla de tarifas**
  - Mantiene las tarifas para cada oferta y período.
  - Campos comunes:
    - Ofrecer identificación.
    - Periodo o inicio/fin efectivo.
    - Importe y moneda de la tarifa.
    - Tipo de tarifa opcional (estándar, ajustada, promocional).
- **Salida de facturación / tabla de archivo**
  - Almacena los cargos calculados.
  - Campos comunes:
    - Punto.
    - Identificación del consumidor.
    - Ofrecer identificación.
    - Unidades, tarifa, cargo total.
    - Campos opcionales de mapeo de diarios.
