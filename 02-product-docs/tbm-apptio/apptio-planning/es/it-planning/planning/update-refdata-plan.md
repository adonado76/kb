---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Actualización de datos de referencia en planes"
breadcrumb:
  - "Planning"
  - "Trabajar con planos"
source_path: "it-planning/planning/update-refdata-plan.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Actualización de datos de referencia en planes

Nota: Solo los usuarios con roles de administrador o propietario del proceso presupuestario pueden realizar estas tareas.

## ¿Qué son los datos de referencia?

Los datos de referencia definen los valores de búsqueda estandarizados para dimensiones como centro de costes, cuenta, departamento, proveedor, proyecto, etc. Estos valores determinan cómo se clasifican, agregan y reportan las partidas del plan.

Más información: [Descripción general de los datos de referencia](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=administration-reference-data-overview "(se abre en una pestaña o una ventana nueva)")

## Actualización de datos de referencia en un plan

Cuando se crea un plan, este utiliza automáticamente la última versión publicada de los datos de referencia disponibles en ese momento. Si los datos de referencia se actualizan posteriormente, los planes existentes no heredan automáticamente esos cambios. Debe actualizar explícitamente el plan para aplicar los datos de referencia más recientes.

**Cómo actualizar los datos de referencia**

1. Abre el plan que deseas actualizar.
2. Asegúrate de que estás viendo **Todos los departamentos**.
3. Abre los **puntos suspensivos (...) menú** y seleccione **Actualizar datos de referencia**.
4. Revise el **resumen del impacto** que se muestra en la ventana modal de confirmación, que incluye:
   1. Partidas que se actualizarán
   2. Partidas que se eliminarán
   3. Nuevos artículos
   4. Elementos eliminados
   5. Códigos principales modificados
5. Si el impacto parece correcto, seleccione **Actualizar** para aplicar los cambios.

**Notas importantes**

- De forma predeterminada, las actualizaciones que eliminarían elementos de línea existentes se bloquean para evitar la pérdida accidental de datos.
- Para permitir actualizaciones destructivas, un administrador debe habilitar **la opción Desactivar restricciones de datos de referencia de actualización** en el perfil de la empresa.
- Cuando se permiten actualizaciones destructivas, **se crea automáticamente** un plan de copia de seguridad antes de aplicar la actualización de los datos de referencia.
