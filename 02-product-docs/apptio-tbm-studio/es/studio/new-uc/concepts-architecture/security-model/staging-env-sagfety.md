---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Seguridad del entorno de pruebas"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Modelo de seguridad"
  - "Seguridad a lo largo de todo el ciclo de vida"
source_path: "studio/new-uc/concepts-architecture/security-model/staging-env-sagfety.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Seguridad del entorno de pruebas

El entorno de prueba actúa como filtro de validación entre el desarrollo y la producción.

- **Acceso:** Requiere el permiso « AccessStg ». Normalmente se concede a los roles de administrador y usuario avanzado.
- **Objetivo:** Comprobar que las configuraciones de seguridad funcionan correctamente con datos reales antes de implementarlas en producción.
- **Pruebas:** Realice cálculos de simulación y compruebe que los filtros RLS producen los resultados esperados. Utiliza la suplantación de identidad para realizar pruebas como usuarios concretos.

**Tema principal:** [La seguridad a lo largo del ciclo de vida](../../../../studio/new-uc/concepts-architecture/security-model/security-across-lifecycle.html)
