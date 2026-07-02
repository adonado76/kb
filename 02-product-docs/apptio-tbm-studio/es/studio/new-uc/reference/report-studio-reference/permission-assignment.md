---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Asignación de permisos"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Permisos del informe"
source_path: "studio/new-uc/reference/report-studio-reference/permission-assignment.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Asignación de permisos

**Permisos basados en roles**

En TBM Studio, los permisos se asignan principalmente a través de roles. A cada usuario se le asignan uno o varios roles que determinan su nivel de acceso.

**Roles predeterminados del sistema:**

|  |  |  |
| --- | --- | --- |
| **Rol** | **Descripción** | **Funcionalidades de generación de informes** |
| **Administrador** | Acceso completo al sistema | Crear, editar, eliminar y configurar todos los informes |
| **Usuario avanzado** | Configuración avanzada | Crear y editar informes |
| **Analista** | Informar sobre el consumo con opciones de personalización | Ver informes, crear informes personalizados, añadir tablas y gráficos personalizados |
| **Solo visualización** | Solo informar del consumo | Ver y filtrar informes |

**Asignación de permisos a roles:**

1. En la pestaña «Informe», haz clic en «Permisos»
2. Seleccionar roles seleccionados
3. Haz clic en el menú desplegable «Seleccionar roles»
4. Selecciona los roles que deben tener acceso
5. Haz clic en «Aceptar» y revisa el informe

Consejo: Cuando restrinjas un informe a roles específicos, asegúrate de que todos los usuarios que necesiten acceso estén asignados al menos a uno de los roles seleccionados.

**Herencia de permisos**

**Heredar de un proyecto**

Los informes heredan el acceso básico de la configuración a nivel de proyecto:

- Los usuarios deben tener acceso al proyecto para poder ver cualquier informe de dicho proyecto
- Las asignaciones de roles a nivel de proyecto determinan quién puede acceder al proyecto
- Los informes pueden restringir aún más (pero no ampliar) el acceso más allá de los permisos del proyecto

**Anular la configuración frente a heredarla**

Los permisos a nivel de informe tienen prioridad sobre la configuración a nivel de colección. El permiso efectivo es la combinación más restrictiva:

|  |  |  |
| --- | --- | --- |
| **Configuración de la colección** | **Configuración del informe** | **Acceso efectivo** |
| Todo el mundo | Todo el mundo | Todo el mundo |
| Todo el mundo | Solo para analistas | Solo para analistas |
| Solo administradores | Todo el mundo | Solo administradores |
| Analistas, administradores | Solo administradores | Solo administradores |

**Tema principal:** [Permisos de informes](../../../../studio/new-uc/reference/report-studio-reference/report-permissions.html)
