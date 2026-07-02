---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Cómo funciona el RBAC"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Modelo de seguridad"
  - "Control de acceso basado en roles (RBAC)"
source_path: "studio/new-uc/concepts-architecture/security-model/how-rbac-work.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Cómo funciona el RBAC

El modelo RBAC consta de tres componentes que funcionan conjuntamente:

1. **Los permisos** definen capacidades específicas (como “EditModels,”, “ViewReports,” o “UploadData” ).
2. **Los roles** agrupan los permisos en conjuntos coherentes que se corresponden con las funciones del puesto (como «Administrador», «Usuario avanzado» o «Usuario empresarial»).
3. **A los usuarios** se les asignan uno o varios roles. Los permisos efectivos de un usuario son la combinación de todos los permisos de los roles que se le han asignado.

Este enfoque presenta ventajas significativas con respecto a la asignación directa de permisos a los usuarios: una auditoría más sencilla, patrones de acceso coherentes, una incorporación simplificada (basta con asignar un rol en lugar de configurar decenas de permisos individuales) y actualizaciones más rápidas cuando cambian las necesidades de la organización.

**Tema principal:** [Control de acceso basado en roles (RBAC)](../../../../studio/new-uc/concepts-architecture/security-model/role-based-access.html)
