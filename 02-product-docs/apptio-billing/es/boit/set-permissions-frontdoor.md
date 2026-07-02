---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Establecer permisos de usuario de Billing Standard en Frontdoor"
breadcrumb: []
source_path: "boit/set-permissions-frontdoor.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Establecer permisos de usuario de Billing Standard en Frontdoor

Billing Standard en TBM Studio 12 los usuarios la Consola de Administración Frontdoor para la gestión de usuarios. Para más información, consulte Acerca de Frontdoor, la página Apptio Access
Administration .

Para realizar las siguientes acciones, los usuarios de Billing Standard necesitan los siguientes permisos Frontdoor:

- **ViewDataQualityAndMonthlyProcessReports** - Permite al usuario acceder a la Colección de Calidad de Facturación.
- **ViewBusinessRelationshipReports** - Permite al usuario acceder a todo EXCEPTO a la colección Calidad de Facturación.
- **ManageAndSendInvoices** - Permite al usuario configurar y enviar facturas por correo electrónico.
- **ViewServiceProviderReports** - Permite al usuario acceder a la colección de informes de proveedores de servicios de TI.
- **ViewBusinessUserReports** - Permite al usuario acceder a la colección de informes de Cargos por Servicio.

Los siguientes roles listos para usar proporcionan acceso a la aplicación Billing Standard , pero restringen el acceso a TBM Studio:

- **Consumidor Empresarial** - Proporciona acceso a la recopilación de informes sobre Cargas de Servicio y Transparencia de Costes.
- **Propietario de Negocio** - Proporciona acceso para ver todo Billing Standard , con la excepción de Calidad de Datos y Distribución de Facturas.
- **Service Manager** - Proporciona acceso a las colecciones de informes de proveedores de servicios de TI y cargos por servicios en Billing Standard .
