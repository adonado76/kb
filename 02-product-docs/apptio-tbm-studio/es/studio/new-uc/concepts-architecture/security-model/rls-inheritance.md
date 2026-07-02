---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Herencia y flujo en RLS"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Modelo de seguridad"
  - "Seguridad a nivel de fila (RLS)"
source_path: "studio/new-uc/concepts-architecture/security-model/rls-inheritance.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Herencia y flujo en RLS

Comprender cómo fluye el RLS a lo largo del canal de datos es fundamental para evitar brechas de seguridad.

**RLS en las asignaciones de modelos**

Cuando se asignan costes de una tabla a otra, la configuración de RLS en las tablas de origen y destino es independiente. Consideremos un ejemplo en el que la unidad de negocio 3 imputa costes a la unidad de negocio 2:

- Si Bob (que solo puede ver la unidad de negocio 2) consulta los resultados de la asignación, verá los costes asignados a la unidad de negocio 2—including, así como los costes procedentes de la unidad de negocio 3.
- Bob no puede ver directamente los datos de origen de la unidad de negocio 3, pero sí puede ver los efectos de las asignaciones en las unidades de negocio a las que tiene acceso.

Este es el comportamiento esperado: RLS filtra las filas visibles, pero no impide que los costes asignados se reflejen en el modelo.

**RLS en las agregaciones de informes**

Cuando un informe muestra datos agregados (totales, sumas, medias), la agregación refleja únicamente las filas visibles para el usuario actual. Si Bob solo puede ver la unidad de negocio 2, la columna de «coste total» de su informe solo mostrará los costes de la unidad de negocio 2’s, y no el total de toda la organización.

**RLS y publicación de tablas editables**

Cuando un usuario publica cambios desde una tabla editable, RLS garantiza que solo las filas visibles para ese usuario sean editables. Es importante destacar que las filas ocultas se conservan durante la publicación: no se eliminan ni se sobrescriben. Esto significa que varios usuarios pueden editar diferentes subconjuntos de la misma tabla editable sin interferir en los datos de los demás.

Nota:

**Pruebas de RLS**

Utiliza el filtro de vista previa en el paso del proceso de RLS para comprobar tu configuración. Introduce la dirección de correo electrónico de un usuario para ver exactamente qué filas vería ese usuario. También puede utilizar la función de suplantación de identidad (disponible para los administradores) para ver los informes como un usuario concreto.

**Tema principal:** [Seguridad a nivel de fila (RLS)](../../../../studio/new-uc/concepts-architecture/security-model/row-level-security.html)
