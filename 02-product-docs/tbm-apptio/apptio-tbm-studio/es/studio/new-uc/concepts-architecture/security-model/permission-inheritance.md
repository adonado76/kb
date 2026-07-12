---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Herencia de permisos y permisos efectivos"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Modelo de seguridad"
  - "Control de acceso basado en roles (RBAC)"
source_path: "studio/new-uc/concepts-architecture/security-model/permission-inheritance.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Herencia de permisos y permisos efectivos

Cuando a un usuario se le asignan varios roles, sus permisos efectivos son la suma de todos los permisos de todos los roles. No existe ningún mecanismo que permita a un rol revocar un permiso concedido por otro rol; los permisos son puramente acumulativos.

**Ejemplo:** Si al usuario A se le asignan tanto el rol «Visor de informes» (con ViewObjectReports ) como el rol «Cargador de datos» (con AccessDev y UploadData ), el usuario A podrá tanto ver informes como cargar datos.

Cuando un usuario cambia de rol a través de la configuración de su perfil («Mi cuenta»), debe actualizar el navegador para que el nuevo rol surta efecto. El rol activo determina las capacidades actuales del usuario e influye en los componentes que se muestran en los informes.

**Tema principal:** [Control de acceso basado en roles (RBAC)](../../../../studio/new-uc/concepts-architecture/security-model/role-based-access.html)
