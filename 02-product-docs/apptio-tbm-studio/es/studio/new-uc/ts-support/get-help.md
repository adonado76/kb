---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Obtención de ayuda"
breadcrumb:
  - "TBM Studio"
  - "Solución de problemas y asistencia técnica"
source_path: "studio/new-uc/ts-support/get-help.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Obtención de ayuda

Si la solución de problemas por tu cuenta no resuelve tu problema, utiliza estos recursos para obtener ayuda adicional.

## Recursos internos

Antes de ponerte en contacto con el servicio de asistencia, consulta el panel de recomendaciones para ver las sugerencias automáticas. Muchos problemas se pueden solucionar automáticamente con los asistentes de resolución de problemas. Utiliza la función de búsqueda de informes para encontrar métricas, etiquetas, dimensiones o componentes en todo el proyecto.

## Cómo ponerse en contacto con el servicio de asistencia

**Cuándo ponerse en contacto con el servicio de asistencia:**

- La solución de problemas por cuenta propia no ha resuelto el problema
- Debes recuperar las configuraciones anteriores
- Se sospecha que se trata de problemas a nivel del sistema
- Necesitas ayuda con operaciones de reversión o de recuperación complejas

**Preparación para ponerse en contacto con el servicio de asistencia: recopile la siguiente información:**

- Texto exacto de cualquier mensaje de error
- Pasos para reproducir el problema
- Entorno (desarrollo, staging o producción)
- Cuando se publicó por primera vez
- Cualquier cambio en la configuración o en los datos realizado recientemente
- Datos de Calc Explorer (si están relacionados con el rendimiento)
- Capturas de pantalla que muestran el problema

## Proceso de escalamiento

|  |  |
| --- | --- |
| **Nivel** | **Acciones** |
| **Nivel 1: Autoservicio** | Utiliza el panel «Recomendaciones», revisa el panel «Errores», comprueba el Explorador de cálculos y consulta la documentación |
| **Nivel 2: Equipo** | Coordinarse con otros usuarios de TBM Studio, consultar con el administrador interno y comprobar si hay problemas conocidos |
| **Nivel 3: Asistencia** | Envía un ticket de asistencia con información detallada e incluye los datos de diagnóstico de Calc Explorer |
| **Nivel 4: CSM** | Para problemas complejos o recurrentes, asesoramiento estratégico sobre la optimización de modelos, solicitudes de nuevas funciones |

## 7.4.4 Deshacer una configuración

Si surge algún problema y necesitas restaurar una configuración anterior, utiliza la función de reversión. Considera la posibilidad de revertir los cambios cuando algo que se ha incorporado al sistema esté causando problemas de rendimiento, se haya implementado algo antes de tiempo o los cambios de configuración hayan afectado al funcionamiento.

Atención: **Consideraciones importantes antes de revertir los cambios**

- Se detendrán todos los cálculos en curso
- Se descartarán todas las registraciones posteriores al punto de reversión
- Será necesario realizar un cálculo de etapa completa
- Si hay otros cálculos del proyecto en ejecución, es posible que la reversión quede en cola

**Procedimiento de reversión:**

- Selecciona el documento en el Explorador de proyectos
- En la pestaña «Compilación», selecciona «Historial de entregas»
- Haz clic con el botón derecho del ratón en la versión a la que deseas revertir y selecciona «Revertir a»
- Introduce un motivo descriptivo para la reversión
- Haz clic en «Reversar registro» y supervisa el estado de la compilación
- Una vez completado, actualiza los espacios de trabajo desde Inicio > Actualizar espacio de trabajo
