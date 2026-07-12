---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Buenas prácticas de seguridad"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Modelo de seguridad"
source_path: "studio/new-uc/concepts-architecture/security-model/security-best-practices.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Buenas prácticas de seguridad

Para garantizar una seguridad eficaz en TBM Studio es necesario planificar cuidadosamente y aplicar de forma coherente los principios de seguridad. En esta sección se ofrecen orientaciones conceptuales y patrones habituales que le ayudarán a diseñar una configuración de seguridad sólida.

## Principio del mínimo privilegio

El principio del privilegio mínimo consiste en conceder a cada usuario el acceso mínimo necesario para desempeñar sus funciones laborales. En TBM Studio, este principio se aplica en todas las capas:

- **Roles:** Asigne el rol con el mínimo de privilegios que satisfaga las necesidades del usuario. Empieza con el nivel «Usuario empresarial» y asciende solo cuando sea necesario.
- **Roles personalizados:** al crear roles personalizados, incluye solo los permisos que el rol realmente necesita. Evita copiar los permisos de administrador «por si acaso»
- **RLS:** Limitar la visibilidad de los datos al ámbito más restringido que sea adecuado para las responsabilidades de cada usuario.
- **Cuentas API:** Crea cuentas de servicio específicas con permisos mínimos para cada integración.
- **Permisos de los informes:** haz que los informes sean visibles para los roles que los necesitan, en lugar de dejar todos los informes accesibles para todo el mundo.

- **[Patrones de diseño de seguridad](../../../../studio/new-uc/concepts-architecture/security-model/security-design-pattern.html)**
- **[Pruebas y validación de seguridad](../../../../studio/new-uc/concepts-architecture/security-model/security-testing.html)**
