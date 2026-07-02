---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Permisos de informes y componentes"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Modelo de seguridad"
source_path: "studio/new-uc/concepts-architecture/security-model/report-component-permission.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Permisos de informes y componentes

Mientras que los roles controlan el acceso general y el RLS controla la visibilidad de los datos, los permisos de informes y componentes proporcionan un nivel adicional de control sobre la experiencia del usuario en Report Studio. Estos permisos determinan qué informes puede ver un usuario y qué componentes de un informe son visibles para los distintos roles.

## Permisos del informe

Los permisos de los informes determinan quién puede ver y quién puede editar cada informe. A partir de TBM Studio 12.7, los permisos de los informes se gestionan a través de una interfaz optimizada, en lugar de crear copias de los informes por separado para cada rol.

**Modelo de permisos de informes**

Al crear un informe, debes seleccionar quién puede verlo. Las opciones son las siguientes:

- **Todos los usuarios:** El informe es visible para cualquier persona que tenga acceso al proyecto.
- **Roles específicos:** Solo los usuarios asignados a los roles seleccionados pueden ver el informe.
- **Solo para uso personal:** el informe solo es visible para su autor. Requiere el permiso «Editar informes personales» (asignado por defecto al rol de analista).

Los permisos de los informes se configuran a través del cuadro de diálogo «Permisos», al que se accede desde la pestaña «Proyecto», en el grupo «Avanzado».

**Colecciones de informes y permisos**

Agrupa los informes relacionados para facilitar la navegación. Los administradores pueden configurar los permisos de los roles para las colecciones, controlando qué roles de usuario pueden acceder a los informes dentro de cada colección. Solo los administradores pueden crear colecciones de informes, y únicamente en el proyecto «Costing Standard». Una vez creadas, las colecciones están disponibles en todo el proyecto.

- **[Visibilidad a nivel de componente](../../../../studio/new-uc/concepts-architecture/security-model/component-level-visibility.html)**
- **[Permisos de las tablas editables](../../../../studio/new-uc/concepts-architecture/security-model/editable-table-permissions.html)**
- **[Permisos del componente de carga de tablas](../../../../studio/new-uc/concepts-architecture/security-model/table-upload-component-permissions.html)**
- **[Cómo interactúan los permisos de los informes y RLS](../../../../studio/new-uc/concepts-architecture/security-model/report-permission-rls-interact.html)**
