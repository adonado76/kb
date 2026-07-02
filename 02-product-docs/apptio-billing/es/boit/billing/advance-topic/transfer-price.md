---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Precios de transferencia y opiniones de las entidades jurídicas"
breadcrumb:
  - "Billing"
  - "Temas avanzados"
source_path: "boit/billing/advance-topic/transfer-price.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Precios de transferencia y opiniones de las entidades jurídicas

Los precios de transferencia y las opiniones a nivel de entidad jurídica cobran importancia cuando los costes tecnológicos traspasan las fronteras legales o fiscales.

Nota: Se aplica únicamente a la norma de facturación.

## Modelización de entidades jurídicas

Elementos mínimos:

- Entidad jurídica principal:
  - Identificación de la entidad, nombre, país, atributos fiscales.
- Asignaciones desde:
  - De consumidores a personas jurídicas.
  - Servicios o infraestructura a personas jurídicas cuando sea necesario.

## Flujos entre empresas

Requisitos comunes:

- Identificar los cargos que representan flujos entre empresas:
  - De una entidad jurídica a otra.
- Representa los flujos de una forma que los equipos financieros y fiscales puedan usar:
  - Separar las líneas de ingresos internos y gastos internos.
  - Utilice las cuentas y los marcadores fiscales adecuados.

Elementos típicos de configuración:

- Tablas de mapeo para definir relaciones de origen y destino entre entidades.
- Reglas en los modelos de facturación para:
  - Dividir o reclasificar los cargos en líneas entre empresas.
  - Etiquétalos con los atributos adecuados.

El objetivo es hacer que los precios de transferencia sean transparentes y rastreables hasta las mismas definiciones de tarifas unitarias y servicios que se utilizan en otros lugares, no mantener un proceso independiente y opaco.
