---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Flujo medioambiental para la norma de facturación"
breadcrumb:
  - "Billing"
  - "Administración y operaciones"
  - "Entornos y gestión de lanzamientos"
source_path: "boit/billing/environ-relnmgmt/env-bs.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Flujo medioambiental para la norma de facturación

La norma de facturación sigue el mismo ciclo de vida medioambiental que el proyecto de la norma de costes subyacente, pero introduce un punto final de facturación independiente para los usuarios finales.

Nota: Se aplica únicamente a la norma de facturación.

Implicaciones:

- Los componentes estándar de facturación se instalan y modifican en el entorno «En desarrollo» del proyecto **estándar de cálculo de costes**.
- Cuando se registran artículos relacionados con la norma de facturación:
  - Se ha creado una nueva versión en desarrollo para el proyecto Costing Standard.
  - Se crea automáticamente una compilación de ensayo correspondiente.

A continuación, se utiliza la puesta en escena para validar:

- Modelos y procesos estándar de facturación (por ejemplo, cálculos de tarifas unitarias, lógica de variación).
- Informes de facturación específicos por dominio (nube, aplicaciones, proyectos, infraestructura, precios de transferencia).
- Escenarios de facturación integral:
  - Cargos por consumidor y dominio.
  - Vistas de tasa unitaria y varianza.
  - Diarios y cualquier exportación posterior.

Comportamiento promocional:

- Cuando la compilación de ensayo se promueve a producción:
  - Se actualiza el entorno de producción **del estándar de cálculo de costes**.
  - **El punto final del estándar** de facturación refleja la nueva lógica y los nuevos informes de facturación, ya que se basa en el mismo contenido del proyecto.

Recomendaciones operativas:

- Trate las versiones estándar de facturación como eventos coordinados:
  - Confirme los cambios en el modelo de estándar de costes y los cambios en el estándar de facturación en la misma compilación.
  - Comunicar a las partes interesadas qué dominios de facturación (por ejemplo, nube, proyectos, precios de transferencia) se ven afectados en cada versión.
- Utiliza Staging como lugar principal para probar ambos:
  - Perspectivas centradas en la tecnología (tarifas unitarias, desgloses por dominio).
  - Vistas centradas en el negocio (facturas, diarios, informes de variaciones).
