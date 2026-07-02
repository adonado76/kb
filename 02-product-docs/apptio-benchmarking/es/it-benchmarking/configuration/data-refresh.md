---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "es"
doc_type: "it-benchmarking"
title: "Actualización y mantenimiento de datos"
breadcrumb:
  - "Benchmarking"
  - "Guía de configuración"
source_path: "it-benchmarking/configuration/data-refresh.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Actualización y mantenimiento de datos

La configuración no es algo que se hace una sola vez. Necesitas un patrón de actualización.

**Actualiza la cadencia de tus datos**  
. Patrón común:

- **Anualmente (después de actualizar los datos de referencia, al final del segundo trimestre natural).**
  - Validar la configuración básica de Benchmarking para el último año fiscal completo.
  - Validar el conjunto completo de comparaciones de la industria, TI OpEx, es e infraestructura.
  - Alinear con la planificación o el cierre financiero.
- **Trimestralmente**
  - Comprueba aleatoriamente las métricas clave para detectar saltos extraños.
  - Si está integrado, comprueba que el modelo de tu proyecto de cálculo de costes no tiene asignaciones rotas y coincide con la versión de TBM en Interactive Benchmarking.

**Gestión de los cambios en el modelo**  
 TBM Cuando usted

- Añadir o renombrar torres de recursos.
- Introducir nuevos grupos de costes.
- Cambiar significativamente la lógica de asignación.

  
Entonces

- Revisar los mapeos de benchmarking y actualizarlos cuando sea necesario.
- Vuelva a ejecutar un pequeño conjunto de vistas de referencia estándar para confirmar que los resultados siguen siendo plausibles.
- Documentar que se ha producido un cambio estructural para que cualquiera que analice las tendencias sepa dónde se ha producido la ruptura.

Si te saltas este paso, verás saltos inexplicables y pasarás semanas intentando recordar qué ha cambiado.
