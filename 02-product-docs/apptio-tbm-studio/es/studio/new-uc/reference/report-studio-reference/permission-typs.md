---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Tipos de permisos"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Permisos del informe"
source_path: "studio/new-uc/reference/report-studio-reference/permission-typs.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Tipos de permisos

**Ver permisos**

Los permisos de visualización determinan qué roles pueden ver un informe al navegar por el Explorador de proyectos o las Colecciones de informes.

**Configuración de los permisos de visualización:**

1. Echa un vistazo al informe
2. En la pestaña Informe, en el grupo Avanzadas, haz clic en Permisos
3. Seleccione los roles que deben tener acceso para ver el informe
4. Elige una de las siguientes opciones:

**Todos** : todos los usuarios con acceso al proyecto pueden ver el informe

**Roles seleccionados** : Solo los usuarios asignados a roles específicos pueden ver el informe

**Funcionalidades del visor:**

- Accede al informe y visualízalo
- Utiliza segmentadores y filtros para explorar los datos
- Exportar los datos del informe (si los permisos de exportación lo permiten)
- Imprimir informes o generar archivos PDF
- Suscríbete a las notificaciones por correo electrónico (si están configuradas)

**Restricciones de solo lectura:**

Los usuarios con roles de solo lectura no pueden:

- Ver o modificar la configuración del informe
- Modificar la configuración o el diseño de un componente
- Modificar los permisos del informe
- Crear tablas o gráficos personalizados (a menos que se le haya asignado el rol de analista)

**Permisos de edición**

Los permisos de edición suelen gestionarse a través de roles a nivel de proyecto, en lugar de mediante la configuración de cada informe. Los usuarios que puedan editar informes deben cumplir los siguientes requisitos:

- Un rol que incluye permisos para crear contenido
- La posibilidad de descargar documentos del proyecto

**Funciones del editor:**

1. Ver y modificar el diseño del informe
2. Añadir, eliminar o configurar componentes de informes
3. Modificar la configuración de tablas y gráficos
4. Modificar las propiedades y la configuración del informe
5. Guarda y confirma los cambios

**Permiso para editar informes personales**

Un permiso específico denominado «Editar informes personales» permite a los usuarios crear informes que solo ellos pueden ver. Este permiso:

- Se le asigna el rol de analista de forma predeterminada
- Se puede asignar a cualquier rol personalizado
- Permite crear informes personales sin afectar a otros usuarios
- Crea informes que no aparecen en las colecciones de otros usuarios

**Permisos de administrador**

Las funciones de administración de informes están vinculadas al rol «Admin» (o a roles personalizados con permisos equivalentes). Los administradores pueden:

- Configurar permisos a nivel de informe
- Gestionar la pertenencia a grupos de recopilación de informes
- Eliminar informes personalizados (los informes predeterminados no se pueden eliminar)
- Desactivar los informes para evitar el cálculo
- Ocultar informes de las colecciones de informes
- Gestionar las suscripciones por correo electrónico de otros usuarios
- Configurar la visibilidad de los componentes según el rol

**Medidas administrativas disponibles:**

|  |  |  |
| --- | --- | --- |
| **Acción** | **Ubicación** | **Notas** |
| Configurar permisos de informes | Pestaña «Informes» → Permisos | Es necesario pasar por caja |
| Añadir a la colección | Pestaña «Informes» → «Asignar a una colección» | Es necesario pasar por caja |
| Suprimir informe | Pestaña Inicio → Eliminar | Solo informes personalizados |
| Desactivar informe | Pestaña «Informe» → Casilla de verificación «Borrar activo» | Impide el cálculo |
| Ocultar de la colección | Pestaña «Proyecto» → Colecciones de informes | Mostrar/ocultar |

**Permisos de ejecución (suscripciones por correo electrónico)**

La ejecución de informes a través de suscripciones por correo electrónico programadas requiere permisos específicos:

|  |  |
| --- | --- |
| **Permiso** | **Prestación** |
| **EmailSubscriptionsCreate** | Crear suscripciones por correo electrónico para uno mismo y para otras personas |
| **EmailSubscriptionsFilteredCreate** | Crear suscripciones con parámetros de filtro |

**Limitaciones de la suscripción:**

- Los destinatarios de los correos electrónicos deben pertenecer a dominios autorizados para el entorno del cliente
- La seguridad a nivel de fila (RLS) no es compatible con las suscripciones por correo electrónico
- Por defecto, solo los administradores de TBM pueden ver la opción de suscripción por correo electrónico

**Tema principal:** [Permisos de informes](../../../../studio/new-uc/reference/report-studio-reference/report-permissions.html)
