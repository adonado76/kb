---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Problemas de compilación e implementación"
breadcrumb:
  - "TBM Studio"
  - "Solución de problemas y asistencia técnica"
  - "Problemas habituales y soluciones"
source_path: "studio/new-uc/ts-support/bd-issues.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Problemas de compilación e implementación

## La compilación se ha quedado bloqueada en el estado «Pendiente» o «Calculando»

Si las compilaciones parecen haberse atascado, comprueba primero la cola de cálculo para conocer el estado actual. Las múltiples entregas pueden provocar atascos en la compilación, y los cambios importantes en la configuración pueden requerir mucho tiempo de cálculo.

**Soluciones:**

- Marca la casilla «Cola de cálculo» (Compilación > Cola de cálculo) para consultar el estado de todos los entornos
- Espera a que se complete el proceso o coordina las actualizaciones con los miembros del equipo para agrupar los cambios
- Cancela la compilación si es necesario ( v12.3.1+ ); los cambios pendientes se incluirán en la próxima compilación

## No se puede implementar en el entorno de producción

**Soluciones:**

- Comprueba que el cálculo de la etapa haya finalizado: la promoción solo es posible una vez que se hayan completado todos los cálculos de la etapa
- Comprueba el estado de bloqueo del entorno; si Stage está bloqueado, coordínate con los demás usuarios
- Revisión de los errores de bloqueo en el panel «Errores»
