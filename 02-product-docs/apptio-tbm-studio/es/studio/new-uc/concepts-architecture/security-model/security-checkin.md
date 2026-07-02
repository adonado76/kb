---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "La seguridad y el proceso de registro de entrada y salida"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Modelo de seguridad"
  - "Seguridad a lo largo de todo el ciclo de vida"
source_path: "studio/new-uc/concepts-architecture/security-model/security-checkin.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# La seguridad y el proceso de registro de entrada y salida

Los objetos relacionados con la seguridad (como las configuraciones de RLS, los permisos de los informes y los ajustes de visibilidad de los componentes basados en roles) siguen el mismo flujo de trabajo de registro y retirada que el resto de objetos de TBM Studio. Esto significa:

- Debes desproteger una tabla para añadir o modificar su nivel de seguridad RLS.
- Al consultar la tabla modificada se activa un recálculo que aplica las nuevas reglas de RLS.
- Los demás usuarios solo verán la configuración de seguridad actualizada una vez que haya finalizado el cálculo.
- Las tablas de mapeo de RLS del proyecto Row-Level Security también siguen el patrón de extracción/registro.

Nota:

**Buenas prácticas: gestión de cambios de seguridad**

Trata los cambios de seguridad con el mismo rigor que los cambios en los modelos. Documenta qué se ha modificado y por qué, realiza pruebas exhaustivas en los entornos de desarrollo y de prueba antes de pasar a producción, y comprueba los resultados tras la implementación. Una regla RLS mal configurada puede tanto exponer datos confidenciales como ocultar datos que los usuarios necesitan para realizar su trabajo.

**Conceptos relacionados:** Para obtener una explicación detallada del ciclo de vida de la compilación y la implementación, [consul](../build-deployment.html) te «Ciclo de vida de la compilación y la implementación». Para obtener instrucciones detalladas sobre cómo gestionar usuarios y configurar la seguridad, consulte las secciones « 3.4 : Gestión de usuarios y permisos» y «[Gestión de usuarios](../../admin/user-management.html) y [seguridad y cumplimiento](../../admin/sec-comp.html) ».

**Tema principal:** [La seguridad a lo largo del ciclo de vida](../../../../studio/new-uc/concepts-architecture/security-model/security-across-lifecycle.html)
