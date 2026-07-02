---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Resolución de problemas"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes de los informes: tablas editables en los informes"
source_path: "studio/new-uc/reference/report-studio-reference/editable-troubleshoot.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Resolución de problemas

Problemas habituales y soluciones para los componentes de tablas editables.

**Errores habituales al guardar**

|  |  |
| --- | --- |
| **Emitir** | **Solución** |
| Los errores de validación impiden guardar | Revisa las celdas resaltadas, corrige los valores incorrectos y asegúrate de que se rellenen los campos obligatorios |
| La celda está bloqueada por otro usuario | Espera a que el otro usuario guarde o cancele su edición, o ponte en contacto con él para que libere el bloqueo |
| No se pueden publicar los cambios | Asegúrate de tener permiso para publicar filas y acceso a los entornos de desarrollo y de prueba; comprueba si hay errores de validación |
| Los cambios no aparecen en los informes | Comprueba que la publicación se haya completado correctamente; espera a que finalice la compilación o el cálculo; actualiza el informe |
| Los valores del menú desplegable no se cargan | Comprueba la sintaxis de la fórmula «Valores posibles»; verifica que la tabla de origen exista y se haya calculado |
| No se pueden eliminar filas de la tabla enriquecida | No se pueden eliminar las filas procedentes de la transformación de origen; solo se pueden eliminar las filas añadidas por el usuario |

**Consideraciones sobre el rendimiento**

Para tablas grandes editables:

- Active la opción «Suprimir solicitud de datos iniciales» en «Propiedades avanzadas» para cargar los datos bajo demanda
- Utiliza filtros o RLS para limitar el número de filas que se muestran
- Limitar el número de columnas con fórmulas complejas en los menús desplegables
- Considera la posibilidad de utilizar la función de carga de archivos para la introducción masiva de datos (más de 100 filas)

**Tema principal:** [Componentes de los informes: Tablas editables en los informes](../../../../studio/new-uc/reference/report-studio-reference/report-component-editable-components.html)
