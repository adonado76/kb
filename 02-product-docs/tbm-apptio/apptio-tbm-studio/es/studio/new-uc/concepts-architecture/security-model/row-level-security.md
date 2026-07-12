---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Seguridad a nivel de fila (RLS)"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Modelo de seguridad"
source_path: "studio/new-uc/concepts-architecture/security-model/row-level-security.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Seguridad a nivel de fila (RLS)

La seguridad a nivel de fila (RLS) es el mecanismo de seguridad a nivel de datos de TBM Studio. Mientras que los roles y los permisos controlan a qué funciones e informes puede acceder un usuario, RLS controla qué filas de datos puede ver un usuario dentro de esos informes y tablas. RLS garantiza que los usuarios solo vean los datos relevantes para su ámbito organizativo, incluso cuando acceden a los mismos informes.

## ¿Qué es la seguridad a nivel de fila?

RLS funciona filtrando los datos en función de la identidad del usuario que ha iniciado sesión. Cuando un usuario abre un informe o consulta una tabla, el sistema comprueba la configuración de RLS para determinar qué filas está autorizado a ver ese usuario concreto. Las filas que no están asociadas al usuario actual se ocultan.

**Por qué es importante el síndrome de piernas inquietas**

- **Datos multitenant:** cuando varias unidades de negocio comparten la misma instancia de TBM Studio, RLS garantiza que cada unidad de negocio solo vea sus propios datos.
- **Límites organizativos:** Los responsables pueden tener restringido el acceso a los datos de costes de su propio departamento o región, mientras que los directivos ven datos agregados de toda la organización.
- **Cumplimiento normativo:** RLS ayuda a aplicar las políticas de acceso a los datos que puedan exigirse en virtud de la gobernanza interna o de normativas externas.

Nota:

**RLS frente a los permisos de los informes**

Los permisos RLS y de informe son complementarios, no alternativos. Los permisos de los informes determinan si un usuario puede acceder a un informe. RLS controla qué datos aparecen en los informes a los que el usuario tiene acceso. Por lo general, se necesitan ambas cosas: permisos de informe para organizar la experiencia del usuario y RLS para garantizar el cumplimiento de los límites de acceso a los datos.

- **[Cómo funciona el RLS](../../../../studio/new-uc/concepts-architecture/security-model/how-rls-worls.html)**
- **[RLS Arquitectura](../../../../studio/new-uc/concepts-architecture/security-model/rls-arch.html)**
- **[Ámbito de aplicación del RLS: en qué casos se aplica el RLS](../../../../studio/new-uc/concepts-architecture/security-model/rls-scope.html)**
- **[Herencia y flujo en RLS](../../../../studio/new-uc/concepts-architecture/security-model/rls-inheritance.html)**
