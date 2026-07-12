---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Permisos de la colección"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Colecciones de informes"
source_path: "studio/new-uc/reference/report-studio-reference/collection-permissions.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Permisos de la colección

**Descripción general del modelo de permisos**

TBM Studio admite permisos tanto a nivel de colección como a nivel de informe individual. Es fundamental comprender cómo interactúan estos permisos para proteger adecuadamente tus informes.

|  |  |
| --- | --- |
| **Nivel de permiso** | **Descripción** |
| A nivel de colección | Determina qué roles pueden ver y acceder a la colección en su conjunto. Los usuarios que no tengan acceso a una colección no la verán en el menú de navegación. |
| A nivel de informe | Determina qué roles pueden ver informes específicos dentro de una colección. Es posible que un usuario tenga acceso a una colección, pero no a todos los informes que contiene. |
| A nivel de componente | Controla la visibilidad de componentes específicos (tablas, gráficos, grupos) dentro de un informe en función del rol del usuario. |

**Herencia de permisos**

Cuando un usuario intenta acceder a un informe de una colección, TBM Studio evalúa los permisos en el siguiente orden:

- **Acceso a la colección:** El usuario debe tener acceso a la colección para poder verla en el menú de navegación
- **Acceso al informe:** el usuario debe tener permiso para ver el informe en cuestión
- **Visibilidad de los componentes:** los componentes individuales pueden ocultarse o mostrarse en función del rol

Los permisos a nivel de informe no se heredan automáticamente de los permisos a nivel de colección. Debes configurar ambos si deseas restringir el acceso en varios niveles.

**Configuración de los permisos de la colección**

Los permisos de las colecciones se configuran a través del cuadro de diálogo «Gestionar colecciones de informes». Los administradores pueden especificar qué roles tienen acceso para ver los informes dentro de cada colección.

Para obtener información detallada sobre cómo configurar los permisos de *los* informes, consulte la sección «Trabajar con permisos de informes» en la documentación de TBM Studio.

**Visibilidad de los componentes por rol**

En los casos en los que los distintos roles necesiten ver diferentes componentes dentro del mismo informe, puede utilizar grupos de informes con visibilidad basada en roles. Esto te permite crear un único informe que muestre contenidos diferentes según el rol de cada usuario.

- Añade un grupo de informes por rol que contenga los componentes visibles para ese rol
- Configura cada grupo para que solo sea visible para un rol
- Organiza los grupos en la superficie de informes de manera que el rol del usuario determine qué grupo ve

Nota: Si un usuario tiene dos roles, cada uno con su propio grupo visible, verá los componentes del rol cuyo grupo se encuentre en la parte superior de la pila.

**Tema principal:** [Colecciones de informes](../../../../studio/new-uc/reference/report-studio-reference/report-collection.html)
