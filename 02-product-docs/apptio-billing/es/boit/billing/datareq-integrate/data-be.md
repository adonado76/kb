---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Requisitos de datos para Billing Essentials"
breadcrumb:
  - "Billing"
  - "Requisitos e integración de datos"
source_path: "boit/billing/datareq-integrate/data-be.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Requisitos de datos para Billing Essentials

Nota: Se aplica solo a Billing Essentials.

Billing Essentials utiliza un conjunto específico de tablas y conjuntos de datos para ejecutar un proceso de facturación « PxQ ». Los nombres y las estructuras exactas de las tablas pueden variar según la versión de la plantilla, pero el patrón es coherente.

Familias de mesas típicas:

- **Biblioteca de soluciones/ofertas**
  - Una lista de ofertas facturables (servicios, productos o paquetes).
  - Campos comunes:
    - Proporcionar identificación y nombre.
    - Unidad de medida.
    - Indicador o estado activo.
    - Indicadores para señalar si la oferta es facturable, solo visible o interna.
- **Consumo de pienso**
  - Unidades consumidas por la oferta y el consumidor durante un período determinado.
  - Campos comunes:
    - Identificación del consumidor.
    - Ofrecer el ID (o una clave que se corresponda con él).
    - Periodo (mes, trimestre, etc.).
    - Unidades consumidas.
    - Atributos opcionales como entorno, región o segmento de centro de costes.
- **Tablas de tarifas y precios**
  - Tarifas por oferta y período.
  - Campos comunes:
    - Ofrecer identificación.
    - Periodo o fecha de entrada en vigor.
    - Importe de la tasa.
    - Tipo de tarifa (por ejemplo, estándar, con descuento, promocional).
- **Tablas maestras de facturación / salida**
  - Resultados de la carga y cualquier salida lista para su publicación en una revista.
  - Campos comunes:
    - Identificación del consumidor.
    - Ofrecer identificación.
    - Punto.
    - Unidades, tarifa y cargo total.
    - Campos opcionales del segmento GL para exportaciones de diario.

Patrones de integración para Billing Essentials:

- Los piensos para consumo suelen proceder de:
  - Sistemas de gestión de tickets o ITSM.
  - Sistemas de identidad/acceso (para recuentos de usuarios).
  - Herramientas de supervisión o medición.
  - Hojas de cálculo o archivos de CSV cuando no existe ningún sistema de registro.
- Los datos suelen cargarse mediante:
  - Procesos ETL de TBM Studio.
  - Datalink u otras herramientas de integración.
  - Carga de tablas para entradas estructuradas de CSV cuando la organización de TI no tiene acceso a Studio.

Si un consumidor o una oferta en el feed de consumo no coincide con las tablas maestras, los cargos relacionados pueden desaparecer o aparecer en vistas de excepción. Planificar el control de calidad básico de los datos en torno a estas uniones.
