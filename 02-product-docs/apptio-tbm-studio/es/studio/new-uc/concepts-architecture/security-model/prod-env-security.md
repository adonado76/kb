---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Seguridad del entorno de producción"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Modelo de seguridad"
  - "Seguridad a lo largo de todo el ciclo de vida"
source_path: "studio/new-uc/concepts-architecture/security-model/prod-env-security.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Seguridad del entorno de producción

El entorno de producción es donde los usuarios de la empresa acceden a los informes y a los datos.

- **Acceso:** Requiere el permiso « AccessProd ». Se concede a todos los roles que necesitan consultar los informes de producción (incluidos los usuarios empresariales).
- **Solo lectura para la mayoría de los usuarios:** los usuarios empresariales y la mayoría de los usuarios avanzados solo deben consultar los informes en el entorno de producción, sin modificar las configuraciones.
- **Gestión del cambio:** los cambios de seguridad deben seguir el flujo de trabajo estándar de implementación: modificar en el entorno de desarrollo, validar en el entorno de prueba e implementar en el entorno de producción.

**Tema principal:** [La seguridad a lo largo del ciclo de vida](../../../../studio/new-uc/concepts-architecture/security-model/security-across-lifecycle.html)
