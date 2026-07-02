---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Patrones de acceso para la norma de facturación"
breadcrumb:
  - "Billing"
  - "cómo empezar"
  - "Roles y permisos de usuario"
source_path: "boit/billing/getting-started/access-patterns-bs.html"
images:
  - "resources/images/boit_images/apbs.png"
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Patrones de acceso para la norma de facturación

Billing Standard introduce un punto final de facturación independiente, además del proyecto de cálculo de costes. El acceso debe tener en cuenta ambos aspectos.

Nota: Se aplica únicamente a la norma de facturación.

**Patrones típicos:**

- **Administradores y analistas**
  - Tenga acceso frontal al punto final del estándar de facturación y a las colecciones de informes pertinentes.
  - Haga que TBM Studio tenga acceso al proyecto Costing Standard donde están instalados los componentes de “BoIT”.
  - Coordínese con los equipos de seguridad para garantizar que los usuarios adecuados vean los informes de facturación y los dominios correctos.
- **Propietarios de servicios o productos, altos directivos, partes interesadas y consumidores.**
  - Acceda a Billing Standard a través del punto final dedicado en el front-end.
  - Ver solo las colecciones de informes y las vistas relevantes para sus responsabilidades y ámbito de actuación.
  - Puede tener un control de acceso más detallado para áreas sensibles como los precios de transferencia o la presentación de informes de entidades jurídicas.

## Puntos clave:

- El acceso a los informes y paneles de control estándar de facturación se controla a nivel de punto final y dentro de las colecciones de informes.
- El acceso a TBM Studio sigue centrado en las funciones de configuración; la mayoría de las funciones empresariales permanecen solo en el front-end.

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/apbs.png)

Fig. n.º: Página de inicio de Frontdoor con el punto final «Billing Standard» resaltado
