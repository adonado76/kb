---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Permisos y tipos de acceso para Billing Standard"
breadcrumb:
  - "Billing"
  - "cómo empezar"
  - "Roles y permisos de usuario"
source_path: "boit/billing/getting-started/perm-access-bs.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Permisos y tipos de acceso para Billing Standard

La siguiente tabla enumera los permisos disponibles específicos de Billing Standard y sus descripciones:

|  |  |
| --- | --- |
| **Nombre del permiso** | **Descripción** |
| ViewDataQualityAndMonthlyProcessReports | Permite al usuario acceder a la Colección de Calidad de Facturación. |
| ViewBusinessRelationshipReports | Permite al usuario acceder a todo EXCEPTO a la colección de calidad de facturación. |
| ManageAndSendInvoices | Permite al usuario configurar y enviar facturas por correo electrónico. |
| ViewServiceProviderReports | Permite al usuario acceder a la recopilación de informes del proveedor de servicios de TI. |
| ViewBusinessUserReports | Permite al usuario acceder a la recopilación de informes de cargos por servicios. |

La facturación se basa en una combinación de acceso front-end y acceso back-end (a través de TBM Studio). No todo el mundo necesita ambas cosas.

## Acceso frontal

**El acceso frontal se utiliza para:**

- Ver e interactuar con informes de facturación (facturas, vistas detalladas, análisis de tarifas unitarias, vistas de variaciones).
- Exportar datos para análisis sin conexión o preparación de diarios.
- Para algunas implementaciones, ajuste las tasas u otros valores de configuración que se exponen intencionadamente a través de tablas editables y mecanismos de carga.

**Patrones de acceso comunes:**

- Los administradores y analistas tienen amplio acceso a las colecciones de informes de facturación.
- Los propietarios de servicios o productos ven las opiniones sobre sus servicios o productos.
- Los consumidores y las partes interesadas ven las partes del catálogo de facturación que se refieren a sus unidades de negocio o centros de coste.

## Acceso al estudio TBM

**El acceso a TBM Studio se utiliza para:**

- Instalar y actualizar los componentes de facturación.
- Ajuste los modelos, métricas, conjuntos de datos y definiciones de tablas de los que depende la facturación.
- Diagnosticar problemas de datos que requieren examinar la lógica ascendente en Costing.

**Patrones típicos:**

- Los administradores, analistas, TAS y socios que diseñan o mantienen la lógica de facturación trabajan en TBM Studio.
- Los propietarios de servicios o productos, los altos directivos y los consumidores no suelen necesitar acceso a TBM Studio.
