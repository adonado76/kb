---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Solución de problemas relacionados con los permisos"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Permisos del informe"
source_path: "studio/new-uc/reference/report-studio-reference/troubleshoot-permission-issues.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Solución de problemas relacionados con los permisos

**Problemas habituales con los permisos**

|  |  |  |
| --- | --- | --- |
| **Problema** | **Causa probable** | **Solución** |
| El informe no se ve | Asignación incorrecta de roles | Añadir un rol a los permisos de informe |
| Componentes vacíos del informe | Filtrado RLS | Añadir usuario a las tablas de asignación de RLS |
| No se puede finalizar la compra | Ya lo he visto | Espera a otro usuario o ponte en contacto con el administrador |
| Faltan componentes | Visibilidad de los componentes | Comprueba que el rol esté incluido en la configuración de visibilidad |
| No se puede exportar | Permisos de exportación | Comprueba los permisos de exportación a nivel de rol |
| No se puede suscribir | Falta un permiso | Conceder permiso a EmailSubscriptionsCreate |

**Lista de comprobación para la verificación de permisos**

Antes de publicar los informes en el entorno de producción, comprueba lo siguiente:

- Permisos de informe configurados para los roles correspondientes
- Las tablas de asignación de RLS incluyen a todos los usuarios necesarios
- Se han comprobado los ajustes de visibilidad de los componentes para cada rol
- El informe aparece en la(s) colección(es) correcta(s)
- El informe está activo y se está procesando
- Suscripciones por correo electrónico configuradas correctamente (si procede)
- Se han probado las funciones de exportación e impresión

**Tema principal:** [Permisos de informes](../../../../studio/new-uc/reference/report-studio-reference/report-permissions.html)
