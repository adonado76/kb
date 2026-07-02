---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Utilizar las preferencias de compromiso para crear un caso de negocio"
breadcrumb:
  - "Cloudability Premium"
  - "Optimizar"
  - "Guía para la gestión de compromisos"
source_path: "product/using_commitment_preferences_to_build_a_business_case.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Utilizar las preferencias de compromiso para crear un caso de negocio

## Configuración de los filtros de uso de recomendaciones (solo para GCP )

Para configurar tu organización, ve a **Configuración** y selecciona **Preferencias de compromiso**. Aquí podrás configurar hasta 10 dimensiones de Cloudability para aplicar a tu uso. Seleccione las dimensiones de sus etiquetas y etiquetas configuradas, asignaciones comerciales o grupos de cuentas.

Para obtener el mejor rendimiento, elija dimensiones que proporcionen un nivel moderado de variabilidad, como unidades de negocio o nombres de aplicaciones. Las dimensiones que presentan una gran variabilidad, como el nombre del recurso, provocarán una degradación significativa del rendimiento. Si una dimensión configurada no está disponible, es probable que se deba a una variabilidad excesiva.

Cualquier cambio en tus preferencias se implementará en el siguiente ciclo de procesamiento. Espera hasta 24 horas para que los cambios surtan efecto y estén disponibles en la página de recomendaciones de CUD.

Las dimensiones se comprueban periódicamente para detectar variaciones y se añadirán o eliminarán de la lista de dimensiones disponibles. Si una dimensión se vuelve demasiado variable, se eliminará y ya no estará disponible en su conjunto de datos.

**Tema principal:** [Guía para la gestión de compromisos](../product/guide_to_commitment_management.html)
