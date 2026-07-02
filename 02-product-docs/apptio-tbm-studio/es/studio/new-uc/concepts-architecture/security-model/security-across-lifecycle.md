---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Seguridad a lo largo de todo el ciclo de vida"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Modelo de seguridad"
source_path: "studio/new-uc/concepts-architecture/security-model/security-across-lifecycle.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Seguridad a lo largo de todo el ciclo de vida

El ciclo de vida de compilación e implementación de TBM Studio (Desarrollo → Entorno de pruebas → Producción) plantea consideraciones de seguridad adicionales. Las propias configuraciones de seguridad están sujetas al flujo de trabajo de registro y retirada, y deben trasladarse de un entorno a otro al igual que los datos y los modelos.

## Seguridad del entorno de desarrollo

El entorno de desarrollo es donde se crean y modifican los modelos, los informes y las configuraciones de seguridad.

- **Acceso:** Requiere el permiso « AccessDev ». Normalmente se concede a los roles de administrador y usuario avanzado.
- **Permisos de edición:** los usuarios deben desproteger los objetos antes de editarlos. El registro bloquea el objeto para que otros usuarios no puedan editarlo al mismo tiempo.
- **Cambios de seguridad:** las tablas de asignación de RLS, las configuraciones de filtro y las definiciones de roles pueden modificarse en el entorno de desarrollo.
- **Pruebas:** Utiliza filtros de vista previa y la suplantación de identidad en el entorno de desarrollo para validar las configuraciones de seguridad antes de implementarlas.

- **[Seguridad del entorno de pruebas](../../../../studio/new-uc/concepts-architecture/security-model/staging-env-sagfety.html)**
- **[Seguridad del entorno de producción](../../../../studio/new-uc/concepts-architecture/security-model/prod-env-security.html)**
- **[La seguridad y el proceso de registro de entrada y salida](../../../../studio/new-uc/concepts-architecture/security-model/security-checkin.html)**
