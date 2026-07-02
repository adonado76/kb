---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Enfoque de transición"
breadcrumb:
  - "Billing"
  - "Manual de puesta en marcha"
source_path: "boit/billing/go-live/gl-cutover.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Enfoque de transición

El cambio es el paso controlado de «estamos probando» a «estamos utilizando la facturación como fuente de verdad»

## Decisiones comunes sobre el cambio

Decidir y documentar:

- Primer **periodo de facturación oficial** en producción.
- Tanto si eres:
  - Comenzar la facturación desde cero, o
  - Sustitución de un proceso manual o heredado anterior a mitad de año.
- Si usted:
  - Vuelva a publicar períodos anteriores para el historial, o
  - Empieza de cero a partir del periodo de puesta en marcha.

## Notas específicas sobre elementos esenciales

Nota: **Se aplica únicamente a Billing Essentials.**

Para lo esencial sobre facturación:

- El cambio está directamente relacionado con la promoción del proyecto Costing Essentials.
- Cuando promocionas la compilación de ensayo a producción:
  - Estás promocionando conjuntamente el contenido de Costing y Billing Essentials.
- Las acciones de puesta en marcha suelen incluir:
  - Promoción de la compilación validada a producción.
  - Ejecución de los modelos de Running Billing Essentials en producción durante el primer periodo oficial.
  - Hacer visible la **recopilación de informes de facturación** para el público objetivo.

## Notas específicas de la norma

Aviso: Se aplica únicamente a la norma de facturación.

Para la norma de facturación:

- El cambio implica ambos:
  - Promoción de la creación del proyecto de estándar de costes que contiene la configuración del estándar de facturación.
  - Habilitar y exponer el **punto final de facturación** con las colecciones de informes correctas.

Pasos típicos:

1. Bloquee la fase de ensayo y promueva la compilación probada a producción.
2. Confirme que el **punto final de facturación** muestra las recopilaciones de informes acordadas (servicios, nube, aplicaciones, proyectos, variaciones, diarios, etc.).
3. Pida a uno o dos usuarios piloto (por ejemplo, un propietario de servicio y un representante financiero) que inicien sesión en el punto final de facturación y confirmen lo siguiente:
   - La navegación funciona.
   - Los filtros y los desgloses funcionan según lo esperado.
