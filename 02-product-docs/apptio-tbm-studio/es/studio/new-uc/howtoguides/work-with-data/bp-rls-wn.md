---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Buenas prácticas para la seguridad a nivel de fila"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Trabajar con datos"
  - "Seguridad de datos"
source_path: "studio/new-uc/howtoguides/work-with-data/bp-rls-wn.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Buenas prácticas para la seguridad a nivel de fila

## Planificación de tu estrategia de RLS

- **Empiece por definir unos requisitos claros:** documente quién necesita acceso a qué datos antes de implementar el RLS. Esto evita tener que volver a realizar el trabajo y garantiza una seguridad uniforme en todas las tablas.
- **Utiliza nombres de tablas significativos:** asigna a las tablas nombres descriptivos (por ejemplo, «Acceso a la unidad de negocio - Usuarios estándar», «Acceso regional - Directivos») para que los demás puedan entender su finalidad.
- **Ten en cuenta el crecimiento futuro:** utiliza un modelo de tabla de «acceso completo» en lugar de enumerar todos los valores para los usuarios avanzados. De este modo, añadir nuevas unidades de negocio o centros de coste no requiere actualizar múltiples registros de usuario.

**Consejos para la implementación**

- **Aplica la política RLS de forma coherente:** si proteges la tabla «Cost Source», protege también las tablas relacionadas, como «IT Resource Towers», para evitar la filtración de datos a través de desgloses o informes relacionados.
- **Realice pruebas exhaustivas:** utilice el filtro de vista previa y las funciones de suplantación de identidad para comprobar que RLS funciona según lo previsto para los distintos tipos de usuarios antes de implementarlo en producción.
- **Documenta tu configuración:** lleva un registro de las tablas que tienen RLS, a qué tablas de mapeo hacen referencia y las reglas de negocio que implementan.

**Aspectos a tener en cuenta en el mantenimiento**

- **Establecer procesos de actualización:** crear procedimientos para añadir o eliminar usuarios y modificar los permisos de acceso. Considere la posibilidad de automatizar el proceso con DataLink para grandes organizaciones.
- **Realice auditorías periódicas:** revise periódicamente las tablas de correspondencias para asegurarse de que reflejan la estructura organizativa actual y los requisitos de acceso.
- **Coordinarse con RR. HH. y TI:** Adaptar las actualizaciones del RLS a la incorporación y salida de empleados, así como a los cambios organizativos.

## Cómo funciona RLS en TBM Studio

Comprender cómo se comporta el RLS en distintos contextos te ayuda a implementar una seguridad integral:

**RLS en tablas de transformación**

- RLS filtra los datos en el momento de la recuperación, por lo que las filas no autorizadas nunca llegan al usuario.
- Cada tabla requiere su propio paso de RLS; la seguridad no se hereda de las tablas relacionadas.

**RLS en tablas editables**

- RLS limita las filas que los usuarios pueden ver y editar en las tablas editables.
- Cuando se publica una tabla editable, las filas ocultas (aquellas que el usuario no puede ver) se conservan; no se sobrescriben ni se eliminan.
- Esto es fundamental en los casos en que los responsables distribuidos actualizan los datos de sus propios centros de coste.

**RLS en los informes**

- Los informes solo muestran las filas que el usuario está autorizado a ver según las reglas de RLS.
- Las agregaciones (totales, medias) reflejan únicamente los datos filtrados por el usuario.
- En los informes generales del modelo, cada nivel refleja su propia configuración de RLS; es posible que los valores no cuadren entre los distintos niveles si se aplica RLS de forma diferente a las distintas tablas.

**RLS con asignaciones de modelos**

- El RLS no influye en el cálculo de las asignaciones. El modelo procesa todos los datos independientemente de la configuración de seguridad.
- Los usuarios solo ven los costes asignados a las unidades de negocio o centros de coste a los que tienen acceso, aunque dichos costes procedan de otras áreas.

## ¿Qué viene ahora?

- [Modelo de seguridad](../../concepts-architecture/studio-model/security-architecture.html) : comprender la arquitectura conceptual de la seguridad en TBM Studio, incluyendo la autenticación, la autorización y cómo se integra RLS en el marco de seguridad general.
- Sección 6.3: Seguridad y cumplimiento normativo: obtenga información sobre la configuración de seguridad a nivel de administrador, los registros de auditoría, las consideraciones de cumplimiento normativo y las mejores prácticas de seguridad empresarial.
- [Crear informes](../create-reports/report-basic.html) : descubre cómo elaborar informes que aprovechen RLS para ofrecer vistas personalizadas a distintos grupos de usuarios.
- [Introducción manual de datos](manual-data-entry.html) : descubre las tablas editables y cómo RLS permite la gestión distribuida de datos.

**Tema principal:** [Seguridad de los datos](../../../../studio/new-uc/howtoguides/work-with-data/data-security.html)
