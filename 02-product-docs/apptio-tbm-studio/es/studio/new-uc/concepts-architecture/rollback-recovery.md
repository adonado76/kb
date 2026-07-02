---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Revertido y recuperación"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Ciclo de vida de la compilación y la implementación"
source_path: "studio/new-uc/concepts-architecture/rollback-recovery.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Revertido y recuperación

A veces es necesario revertir los cambios; tal vez una configuración provoque problemas de rendimiento o el contenido se haya publicado antes de tiempo. TBM Studio ofrece funciones de reversión para estas situaciones.

**Cuándo utilizar la función de reversión**

Considera utilizar la función de reversión cuando:

- Una configuración archivada está provocando problemas de rendimiento
- El contenido se publicó en el entorno de producción antes de tiempo
- Debes volver rápidamente a un estado en el que sepas que todo funciona correctamente

Aviso:

No se debe recurrir a la reversión a la ligera. Se descartarán todas las registraciones posteriores al punto de reversión. Si hay cambios en esas revisiones que desees conservar, tendrás que volver a implementarlos tras la reversión.

**Cómo funciona la reversión**

Cuando se ejecuta una reversión:

1. Se detienen todos los cálculos en curso del proyecto
2. Se inicia un nuevo cálculo utilizando la configuración del registro seleccionado
3. Se descartan todas las entradas posteriores al punto seleccionado (excepto las operaciones de ramificación)
4. Se ejecuta un cálculo completo de la etapa, lo que puede llevar algún tiempo dependiendo de la complejidad de la configuración

**Ejecutar una reversión**

1. Selecciona cualquier documento en el Explorador de proyectos.
2. En la pestaña «Compilación», selecciona «Historial de entregas».
3. Haz clic con el botón derecho del ratón en la versión a la que deseas revertir y selecciona «Revertir a».
4. Introduce un motivo descriptivo para la reversión y haz clic en «Reversar registro».
5. Una vez finalizada la compilación, actualiza cualquier espacio de trabajo que contenga documentos extraídos seleccionando Inicio > Actualizar espacio de trabajo.

Sugerencia:

Si el contenido se ha implementado en el entorno de producción antes de tiempo, plantéate utilizar una rama de correcciones en lugar de revertir los cambios. Una revisión puede ser más rápida y no descarta las versiones intermedias.
