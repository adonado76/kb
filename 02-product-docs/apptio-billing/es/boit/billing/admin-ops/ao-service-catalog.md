---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Diseño centrado en el catálogo de servicios"
breadcrumb:
  - "Billing"
  - "Administración y operaciones"
source_path: "boit/billing/admin-ops/ao-service-catalog.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Diseño centrado en el catálogo de servicios

**Cuándo utilizarlo**

- La organización tecnológica tiene un catálogo de servicios o una cartera de productos que desea facturar.
- Las conversaciones principales se centran en el servicio o el producto, no en el servidor o la aplicación.

**Forma**

- El catálogo de servicios o productos es el principal objeto de facturación.
- Los dominios (infraestructura, nube, aplicaciones) introducen los costes y volúmenes en los servicios dentro de Costing.
- La facturación se centra en las unidades de nivel de servicio, las tarifas y los cargos.

**Elementos clave**

- Catálogo de servicios estable con una propiedad clara.
- Tablas de correspondencias:
  - Objetos de infraestructura → servicios.
  - Aplicaciones → servicios.
  - Cuentas/etiquetas en la nube → servicios.
- Facturación:
  - Consumo a nivel de servicio.
  - Tarifas por nivel de servicio.
  - El dominio opcional vuelve a los informes.

**Informes típicos**

- Vistas de facturas centradas en el servicio: una fila por servicio por consumidor.
- Rentabilidad del servicio o perspectivas de margen en las que es relevante la relación entre precio y coste.
- Desgloses de dominio opcionales (por ejemplo, «qué compone el coste de este servicio»).

**Notas de implementación**

- Esfuérzate en el diseño para conseguir unas definiciones de servicio adecuadas. La facturación será mucho más fácil.
- Trate los servicios como el «lenguaje» utilizado con las partes interesadas del negocio y utilice los dominios para respaldar el análisis interno.
