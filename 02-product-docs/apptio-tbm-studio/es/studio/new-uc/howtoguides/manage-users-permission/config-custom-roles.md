---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Configurar roles personalizados"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Gestionar usuarios y permisos"
  - "Gestión de usuarios"
source_path: "studio/new-uc/howtoguides/manage-users-permission/config-custom-roles.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configurar roles personalizados

**Objetivo:** Crear roles personalizados con combinaciones específicas de permisos para satisfacer las necesidades particulares de la organización.

**Cuándo utilizarlo:** cuando los roles predeterminados no ofrecen la combinación exacta de permisos que necesitan tus usuarios, o cuando necesitas un control más preciso sobre funciones específicas.

**Tiempo estimado:** entre 15 y 30 minutos por papel

**Requisitos previos**

- Se requiere tener el rol de administrador.
- Conocer con claridad los permisos necesarios para el grupo de usuarios destinatario.
- Documentación de los requisitos de control de acceso de su organización.

## Cuándo crear roles personalizados

Considera la posibilidad de crear un rol personalizado cuando:

- Los usuarios necesitan un subconjunto de los permisos de usuario avanzado, pero no acceso completo.
- Necesitas cuentas exclusivas para la API con permisos limitados para la automatización.
- Cada equipo necesita un nivel de acceso a los informes diferente.
- Debes restringir el acceso a entornos específicos (Desarrollo, Prueba, Producción).
- Los requisitos de cumplimiento exigen la separación de funciones.

## Pasos

1. **Gestión de roles de acceso.** En la Administración de acceso mejorado, vaya a la sección «**Roles y permisos** ».
2. **Crea un nuevo rol.** Haz clic en **«Añadir personalizado» ( RoleName ) en el rol.** Introduce un nombre y una descripción que indiquen la finalidad del rol (por ejemplo, «Cargador de datos», «Visor de informes - Finanzas», «Integración de API»).
3. **Selecciona los permisos.** Selecciona los permisos específicos que debe tener este rol. Entre las categorías de permisos más comunes se incluyen:

   |  |  |
   | --- | --- |
   | **Categoría de permisos** | **Ejemplos** |
   | **Acceso al medio ambiente** | AccessDev, AccessStg, AccessProd |
   | **Operaciones con datos** | UploadData, DrillDown, ViewAllData |
   | **Informes** | ViewMetricReports, ViewObjectReports, ViewTransformReports, ViewReportsSavedForEveryone, Editar informes personales |
   | **Exportar** | CanExportExcel, CanExportPDF (permite la descarga de datos) |
4. **Guarda el rol.** Haz clic en **«Guardar»** para crear el rol personalizado.
5. **Prueba el papel.** Asigna el rol a un usuario de prueba y comprueba que los permisos funcionan según lo previsto antes de implementarlo para el resto de usuarios.

## Ejemplos de roles personalizados

***Ejemplo 1: Función de cargador de datos***

Para usuarios que solo necesitan cargar archivos de datos, pero no necesitan crear modelos ni consultar todos los informes.

- AccessDev
- UploadData

***Ejemplo 2: Visor de informes financieros***

Para los miembros del equipo financiero que necesitan acceder a los informes de producción, pero no tienen capacidad para configurarlos.

- AccessProd
- ViewMetricReports
- ViewObjectReports
- CanExportEcel

***Ejemplo 3: Cuenta de integración de API***

Para procesos automatizados que cargan y descargan datos a través de una API.

- AccessDev
- UploadData
- CanExportExcel

## Errores habituales

- **Exceso de permisos:** añadir demasiados permisos va en contra del objetivo de una función personalizada. Empieza con lo mínimo y ve añadiendo permisos según sea necesario.
- **Faltan permisos dependientes:** algunos permisos necesitan otros para funcionar. Realiza pruebas exhaustivas para asegurarte de que la función opera según lo previsto.
- **Permisos de «carga» duplicados:** ten en cuenta que « "UploadData" » y «Upload Data» son permisos distintos. Incluye ambos para disponer de todas las funciones de carga.
- **No documentar los roles personalizados:** documenta siempre para qué sirve cada rol personalizado y qué permisos incluye.

## ¿Qué viene ahora?

Una vez configurados los usuarios y los roles, es posible que desee:

- **Configura los permisos de los informes** para controlar a qué informes puede acceder cada rol. Véase «[Control de acceso](access-control-intro.html) ».
- **Implemente la seguridad a nivel de fila** para restringir la visibilidad de los datos en función de la identidad del usuario. Véase «[Control de acceso](access-control-intro.html) ».
- **Configura la integración de SSO** para la autenticación empresarial. Consulte [la sección «Gestión de usuarios»](../../admin/user-management.html) para obtener información detallada.
- **Supervise la actividad de los usuarios** mediante los informes de uso de Apptio. Consulte «[Gestión de usuarios](../../admin/user-management.html) ».

**Tema principal:** [Gestión de usuarios](../../../../studio/new-uc/howtoguides/manage-users-permission/manage-up-intro.html)
