---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Lista de verificación de preparación previa a la puesta en marcha"
breadcrumb:
  - "Billing"
  - "Manual de puesta en marcha"
source_path: "boit/billing/go-live/gl-checklist.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Lista de verificación de preparación previa a la puesta en marcha

Esto es lo mínimo que debe tener preparado antes incluso de fijar una fecha de puesta en marcha.

**Disponibilidad de datos y modelos**

- Modelo de cálculo de costes:
  - Las asignaciones se mantienen estables durante al menos uno o dos periodos anteriores.
  - No hay problemas críticos abiertos que interrumpan regularmente el funcionamiento.
- Datos de facturación:
  - Se revisa y aprueba el catálogo de servicios/ofertas.
  - El maestro de consumidores está completo para todas las entidades a las que se facturará.
  - Las cubiertas de consumo abarcan todos los servicios y consumidores incluidos en el ámbito de aplicación.
  - Las tablas de tarifas o precios se cargan para el período de puesta en marcha y los siguientes períodos.

**Entorno y preparación para el lanzamiento**

- En desarrollo:
  - Se comprueba todo el trabajo de configuración de facturación.
  - No se dejan experimentos a medias.
- Puesta en escena:
  - Contiene una compilación completa con todos los cambios de facturación incluidos.
  - Construcción de escenario utilizada para el ensayo general.
- Producción:
  - Sin pruebas ni contenido POC que puedan confundir a los usuarios.

**Informes y acceso a la preparación**

- Informes:
  - Informes de facturación básicos identificados para su puesta en marcha (no todos los informes).
  - Los filtros y las indicaciones del informe funcionan según lo previsto.
  - Las opiniones clave se han revisado con las partes interesadas.
- Acceso:
  - Los administradores y analistas pueden acceder al proyecto/punto final correspondiente.
  - Los propietarios de servicios o productos pueden ver los informes que necesitan.
  - El departamento financiero puede acceder a las exportaciones de diarios cuando sea aplicable.
