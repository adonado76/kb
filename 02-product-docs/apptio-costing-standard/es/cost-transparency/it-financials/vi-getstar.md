---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Información sobre proveedores Introducción"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso financiero"
  - "Proveedor"
source_path: "cost-transparency/it-financials/vi-getstar.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Información sobre proveedores Introducción

Vendor Insights proporciona análisis y apoyo a la toma de decisiones a lo largo de todo el ciclo de vida de la gestión de proveedores, incluyendo la visibilidad del gasto de los proveedores, los controles de las órdenes de compra, el análisis de los contratos y la supervisión de ARC/RRC. Vendor Insights se ofrece a través de componentes modulares que se pueden instalar de forma incremental en función del nivel de información requerido.

Antes de habilitar los informes de Vendor Insights, asegúrese de que los componentes básicos necesarios estén instalados y de que los datos de proveedores, cuentas por pagar y otros datos relacionados estén disponibles y correctamente asignados.

## Requisitos previos

- **CTF – Fuente de costes**
- Proporciona datos financieros reales y presupuestarios fundamentales necesarios para el análisis del gasto de los proveedores.
- **CTF – Proveedor**
- Permite el acceso a los datos maestros de los proveedores y la atribución del gasto a nivel de proveedor.

Los componentes adicionales de Vendor Insights se basan en esta base e introducen capacidades de generación de informes más avanzadas.

**Componentes de información sobre proveedores**

Los componentes de Vendor Insights se instalan de forma incremental, y cada componente habilita un conjunto específico de informes y análisis.

## Información sobre proveedores: Fundación

El componente **Vendor Insights Foundation** proporciona visibilidad del gasto en proveedores principales y capacidades de racionalización. Permite analizar la distribución de proveedores, las tendencias de gasto y la concentración de la cartera.

Capacidades clave habilitadas:

- Información sobre proveedores (panel de control)
- Resumen del proveedor
- Detalles del proveedor
- Gasto por proveedor según tipo de proveedor y grupo de costes
- Análisis de la calidad de los datos entre los datos del proveedor y los datos de cuentas por pagar

Este componente requiere:

- Datos de cuentas por pagar (facturas y detalles de gastos)
- Datos maestros de proveedores (nombres de proveedores, jerarquía, categorización)

## Información sobre proveedores: órdenes de compra (PO)

El componente **PO** de Vendor Insights amplía el análisis de proveedores a la visibilidad y los controles de las órdenes de compra.

Capacidades clave habilitadas:

- PO Burndown
- Gastar sin órdenes de compra
- Detalle de la orden de compra
- Análisis de la relación entre PO y AP

Este componente requiere:

- Datos de la orden de compra
- Datos de mapeo AP-PO

**Nota:** El componente Foundation debe estar completamente instalado y configurado antes de instalar el componente PO.

## Información sobre proveedores: contratos

El componente **Vendor Insights Contracts** permite realizar análisis a nivel de contrato y planificar renovaciones.

Capacidades clave habilitadas:

- Resumen del contrato
- Caducidad del contrato
- Notificación de vencimiento del contrato
- Contrato para aplicaciones
- Detalles del contrato

Este componente requiere:

- Datos maestros del contrato
- Asignación de órdenes de compra a contratos
- Asignación de contratos a aplicaciones
- Datos maestros de la aplicación

**Nota:** El componente PO debe estar instalado antes de habilitar Contratos.

## Información sobre proveedores: ARC/RRC

El componente **ARC/RRC** permite analizar los contratos con proveedores basados en el consumo con cargos adicionales por recursos y créditos reducidos por recursos.

Capacidades clave habilitadas:

- Resumen del ARC RRC
- ARC RRC RU Conciliar
- Análisis del consumo y los precios de las unidades de recursos

Este componente se instala después de Contracts y requiere datos específicos de ARC/RRC sobre contratos y unidades de recursos.

## Fuentes comunes de datos

Vendor Insights suele integrar datos procedentes de sistemas financieros, de compras y de gestión de contratos. Las aplicaciones de origen común incluyen:

- **Cuentas por pagar / Sistemas financieros:** SAP ECC/AP, Oracle Finanzas, NetSuite
- **Sistemas de adquisición:** SAP Ariba, Coupa, Oracle Procurement Cloud
- **Gestión de proveedores y contratos:** ServiceNow Gestión de proveedores: SAP ERP: Oracle

El alcance y la calidad de los datos de origen determinan los atributos disponibles para la generación de informes, tales como nombres de proveedores, categorías, importes de gasto, órdenes de compra, contratos, aplicaciones compatibles y métricas ARC/RRC.

## Conjuntos de datos maestros

Dependiendo de los componentes instalados, Vendor Insights utiliza los siguientes conjuntos de datos maestros:

- **Datos maestros de proveedores** : atributos, jerarquía y categorización de proveedores
- **Datos maestros de cuentas por pagar** : gasto y atribución a nivel de factura
- **Datos maestros de órdenes de compra** : valores, estado y compromisos de las órdenes de compra
- **Datos maestros de contratos** : condiciones contractuales, vencimiento, compromisos
- **Contratos a datos maestros de aplicaciones** : asignación de contratos a aplicaciones compatibles
- **Datos maestros ARC/RRC** : cantidades de unidades de recursos, umbrales y precios

Estos conjuntos de datos deben cargarse y asignarse correctamente para garantizar la precisión de los informes y análisis de proveedores en todos los informes de Vendor Insights.
