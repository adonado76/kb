---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Descripción general de la arquitectura de seguridad"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Modelo de seguridad"
source_path: "studio/new-uc/concepts-architecture/security-model/security-architecture.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Descripción general de la arquitectura de seguridad

TBM Studio ofrece un modelo de seguridad de varios niveles que controla quién puede acceder al sistema, qué acciones puede realizar y qué datos puede ver. Comprender estas capas —y cómo interactúan entre sí— es fundamental para diseñar una configuración de seguridad que proteja los datos financieros confidenciales y, al mismo tiempo, permita a las personas autorizadas realizar su trabajo de forma eficaz.

## Niveles de seguridad

La arquitectura de seguridad de TBM Studio funciona en tres niveles distintos. Cada capa responde a una pregunta diferente y utiliza un mecanismo distinto para aplicar el control de acceso.

|  |  |  |  |
| --- | --- | --- | --- |
| **Capa** | **Pregunta respondida** | **Mecanismo** | **Ámbito** |
| 1. Autenticación | ¿Quién eres? | Nombre de usuario/contraseña, SSO, claves API | En todo el dominio |
| 2. Autorización (RBAC) | ¿Qué puede hacer? | Roles y permisos asignados a los usuarios | A nivel de proyecto y a nivel de informe |
| 3. Seguridad de los datos (RLS) | ¿Qué datos puedes ver? | Filtros de seguridad a nivel de fila en las tablas | A nivel de tabla, fluye a los informes |

Estas capas interactúan entre sí como anillos concéntricos. La autenticación es el primer paso: determina si puedes acceder a TBM Studio. La autorización es el eslabón central: determina qué funciones, informes y acciones están a tu disposición. La seguridad de los datos es el anillo más interno: filtra las filas de datos que puedes ver en los informes y las tablas a los que tienes acceso.

## Ámbito de seguridad

La seguridad en TBM Studio se aplica en varios niveles, desde el más amplio (dominio) hasta el más detallado (filas de datos individuales).

- **Seguridad a nivel de dominio:** las políticas de contraseñas, la gestión de sesiones y la configuración de autenticación se aplican a todos los usuarios de todos los proyectos de un dominio. Se configura a través del cuadro de diálogo «Seguridad del dominio» en la pestaña «Proyecto».
- **Seguridad a nivel de proyecto:** los usuarios y las funciones se definen a nivel de proyecto. El rol de un usuario en un proyecto puede diferir de su rol en otro proyecto dentro del mismo dominio.
- **Seguridad a nivel de informe:** los permisos de los informes controlan qué roles pueden ver o editar informes específicos. El acceso a las colecciones de informes también se puede restringir en función del rol.
- **Seguridad a nivel de componentes:** los componentes individuales de los informes (tablas, gráficos, grupos) se pueden configurar para que se muestren u oculten en función del rol actual del usuario.
- **Seguridad a nivel de datos (RLS):** los filtros de seguridad a nivel de fila restringen las filas de datos que un usuario puede ver, independientemente del informe que esté consultando. RLS funciona con tablas de « Data Studio », objetos de modelo, tablas editables e informes.

Nota: **Cómo interactúan las capas**

El usuario debe pasar por todas las capas pertinentes para ver los datos. Por ejemplo, un usuario empresarial con un rol que le otorga acceso a un informe de costes seguirá viendo únicamente las filas de datos permitidas por su configuración de RLS. Si su función no incluye el informe, no lo verán en absoluto, independientemente de si RLS hubiera permitido el acceso a los datos.

## Marco de decisiones de seguridad

Al planificar tu configuración de seguridad, ten en cuenta estas preguntas en el orden siguiente:

1. ¿Quién necesita acceso a TBM Studio? → Configura las cuentas de usuario y la autenticación.
2. ¿Qué debería poder hacer cada persona? → Asignar roles con los permisos adecuados.
3. ¿Qué informes debe ver cada persona? → Configura los permisos de los informes según el rol.
4. ¿Deberían ver datos diferentes distintas personas en el mismo informe? → Implemente la seguridad a nivel de fila.
5. ¿Deberían variar los diseños de los informes según el rol? → Utiliza la configuración de visibilidad de los componentes
