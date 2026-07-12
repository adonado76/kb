---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Permisos de las tablas editables"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Modelo de seguridad"
  - "Permisos de informes y componentes"
source_path: "studio/new-uc/concepts-architecture/security-model/editable-table-permissions.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Permisos de las tablas editables

Las tablas editables de los informes cuentan con su propio sistema de permisos detallado que controla las acciones a nivel de fila:

|  |  |  |
| --- | --- | --- |
| **Permiso** | **Controles** | **Valor predeterminado** |
| Permiso para añadir filas | ¿Qué roles pueden añadir nuevas filas a la tabla? | Todo el mundo |
| Permiso para duplicar filas | ¿Qué roles pueden duplicar filas? | Todo el mundo |
| Permiso para eliminar filas | ¿Qué roles pueden eliminar filas individuales? | Todo el mundo |
| Permiso para publicar filas | ¿Qué roles pueden publicar las modificaciones en las transformaciones? | Todo el mundo |
| Permiso para editar fila | ¿Qué roles pueden modificar las filas existentes? | Todo el mundo |
| Permiso de descarga | ¿Qué roles pueden descargar los datos de la tabla? | Todo el mundo |
| Permiso para subir archivos | ¿Qué roles pueden cargar datos en la tabla? | Todo el mundo |
| Permiso para mostrar el historial | ¿Qué roles pueden ver el historial de cambios? | Todo el mundo |
| Permiso para eliminar todas las filas | ¿Qué roles pueden eliminar todas las filas de una sola vez? | Administrador y socio |

Cada permiso se puede configurar como «Todos» o «Roles seleccionados», lo que permite un control preciso de los flujos de trabajo de introducción de datos.

**Tema principal:** [Permisos de informes y componentes](../../../../studio/new-uc/concepts-architecture/security-model/report-component-permission.html)
