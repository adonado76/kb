---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Integración con otros flujos de trabajo"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Ciclo de vida de la compilación y la implementación"
source_path: "studio/new-uc/concepts-architecture/integration-other-wf.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Integración con otros flujos de trabajo

El ciclo de vida de la compilación se integra con otros flujos de trabajo de TBM Studio. Comprender estas relaciones te ayuda a planificar tu trabajo de forma eficaz.

**Tablas editables y ascenso automático**

Las tablas editables permiten a los usuarios finales introducir datos a través de los informes. Una vez publicados, estos datos pasan por el ciclo de vida de la compilación:

1. El usuario edita los datos de un informe que muestra una tabla editable
2. La función «Publish» escribe los datos editables de la tabla en la tabla de transformación asociada
3. Convertir las actualizaciones de la tabla en objetos del modelo
4. El modelo se vuelve a calcular durante la siguiente compilación de staging o de producción
5. Los informes reflejan las asignaciones actualizadas

Las tablas programadas editables pueden activar automáticamente los cálculos de staging y, si así se ha configurado, pasar automáticamente a Producción. Esto crea un proceso totalmente automatizado desde los datos hasta la producción.

**Normas sobre la actualidad de los datos**

Las reglas de actualización de datos supervisan las modificaciones en las tablas y se integran en el ciclo de vida de la compilación:

- Las reglas detectan cuándo faltan datos esperados o estos están desactualizados
- El sistema envía notificaciones a los administradores
- Los administradores actualizan las tablas y registran los cambios
- El próximo cálculo del modelo incorpora datos actualizados

Los indicadores de actualidad son especialmente importantes durante los procesos de cierre de fin de mes, ya que ayudan a determinar si los resultados obsoletos de los modelos se deben a la falta de actualizaciones de los datos.

**Periodos y versiones**

La configuración del periodo de tiempo activo afecta a las compilaciones en todas las capas:

- **Data Studio :** El filtrado por partición de fecha determina los datos de qué mes se introducen en las transformaciones
- **Model Studio:** Los cálculos se realizan utilizando la versión correspondiente al período activo
- **Informes:** los valores mostrados reflejan los datos del período actual
- **Períodos cerrados:** no se permiten actualizaciones, pero se pueden seguir incluyendo en los informes
