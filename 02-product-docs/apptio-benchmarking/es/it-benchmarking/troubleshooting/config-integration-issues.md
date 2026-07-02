---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "es"
doc_type: "it-benchmarking"
title: "Problemas de configuración e integración"
breadcrumb:
  - "Benchmarking"
  - "Informes comparativos"
  - "Solución de problemas y preguntas frecuentes"
source_path: "it-benchmarking/troubleshooting/config-integration-issues.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Problemas de configuración e integración

**La evaluación comparativa no refleja los cambios recientes en el cálculo de costes.**

Síntoma  
: Ha actualizado las asignaciones o distribuciones en Costing, pero Benchmarking sigue mostrando la estructura antigua.   
Posibles causas

- La evaluación comparativa apunta a un proyecto de cálculo de costes diferente al que ha actualizado
- Los datos de referencia no se han actualizado desde el cambio
- Has cambiado un modelo o módulo que no está en la fuente de Benchmarking

Qué hay que comprobar

1. Compruebe la configuración de Benchmarking para saber qué proyecto de cálculo de costes se está utilizando.
2. Confirme cuándo se realizó la última actualización de datos.
3. Verifique que el modelo de cálculo de costes que ha modificado realmente está alimentando el conjunto de datos de benchmarking.

Respuesta breve que puede enviar:   
Benchmarking sigue utilizando la vista de costes anterior porque no se ha actualizado desde el proyecto actualizado. Una vez que actualicemos desde el proyecto correcto, las vistas de referencia reflejarán las nuevas asignaciones.

**Después de cambiar la versión de TBM, las métricas parecen inconsistentes.**

Síntoma  
: Cambias la versión de la taxonomía en Benchmarking y, de repente, los informes no coinciden con los de años anteriores.   
Posibles causas

- Las torres de recursos y las subtorres de recursos difieren entre las versiones antiguas y las nuevas
- No todos los costes se han asignado aún a las nuevas estructuras
- Algunas métricas utilizan nuevas agrupaciones que no coinciden con las agrupaciones históricas
- Benchmarking y Costing utilizan versiones diferentes de TBM.

Qué hay que comprobar

1. Compare las definiciones antiguas y nuevas de Torre de recursos / Subtorre.
2. Comprueba si hay costes sin asignar o parcialmente asignados en la nueva versión.
3. Trate el año del cambio de versión como una nueva línea de base, no como una continuación.
4. En Interactive Benchmarking, compruebe que su configuración refleje la misma versión de TBM que su proyecto de cálculo de costes.

Respuesta breve que puede enviar  
: Hemos cambiado a una nueva taxonomía, lo que modifica la forma en que se agrupan las torres y las subtorres. Esto hace que los nuevos resultados no sean directamente comparables con los de años anteriores. Consideraremos el año del cambio como un reinicio de la base de referencia y, cuando sea necesario, reexpresaremos los periodos anteriores en la nueva estructura.
