---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Cómo funciona el RLS"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Modelo de seguridad"
  - "Seguridad a nivel de fila (RLS)"
source_path: "studio/new-uc/concepts-architecture/security-model/how-rls-worls.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Cómo funciona el RLS

El proceso RLS sigue una secuencia predecible cada vez que un usuario solicita datos:

1. El usuario abre un informe o consulta una tabla en TBM Studio.
2. El sistema identifica al usuario que ha iniciado sesión mediante su ID de usuario (dirección de correo electrónico).
3. Para cada tabla en la que se haya configurado RLS, el sistema busca el ID del usuario en la(s) tabla(s) de correspondencias correspondiente(s).
4. El sistema determina qué valores de dimensión (como unidades de negocio, centros de coste o centros de datos) puede ver el usuario.
5. El sistema filtra la tabla y muestra únicamente las filas en las que los valores de las dimensiones pertinentes coinciden con los valores permitidos por el usuario.
6. El usuario solo ve los datos autorizados: las agregaciones, los totales y los desgloses reflejan la vista filtrada.

**Tema principal:** [Seguridad a nivel de fila (RLS)](../../../../studio/new-uc/concepts-architecture/security-model/row-level-security.html)
