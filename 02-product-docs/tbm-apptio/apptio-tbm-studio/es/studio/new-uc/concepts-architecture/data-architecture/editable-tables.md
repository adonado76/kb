---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Tablas editables"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Arquitectura de datos"
  - "Tablas y tipos de tablas"
source_path: "studio/new-uc/concepts-architecture/data-architecture/editable-tables.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Tablas editables

**Objetivo:** Permitir la introducción manual de datos y el enriquecimiento humano de los datos generados automáticamente.

Las tablas editables permiten a los usuarios introducir, modificar y gestionar datos directamente en TBM Studio. Sirven de puente entre los flujos de datos automatizados y el criterio humano necesario para tareas como la clasificación de centros de coste, la asignación de mano de obra y las anotaciones presupuestarias.

TBM Studio admite dos tipos de tablas editables:

**Tablas en blanco editables**

Una tabla en blanco y editable se abre vacía. Los administradores definen las columnas (esquema), los tipos de datos, las reglas de validación y los valores opcionales de los menús desplegables. A continuación, los usuarios rellenan la tabla a través de la interfaz de generación de informes o mediante la introducción directa de datos.

- **Caso de uso:** Introducción de datos totalmente manual, como la creación de una tabla de correspondencias para la asignación de centros de coste a soluciones, la introducción de explicaciones de desviaciones presupuestarias o la elaboración de tablas de consulta de referencia.
- Los usuarios pueden añadir y eliminar filas libremente.
- La tabla editable es la fuente de información fiable: no depende de datos de otras fuentes.

**Tablas editables con funciones avanzadas**

Una tabla editable enriquecida se crea a partir de los datos de una tabla de transformación ya existente. El sistema carga todas las filas y columnas de origen, y los administradores pueden añadir columnas editables adicionales para que los usuarios las rellenen. Los usuarios pueden modificar las columnas editables, pero no pueden eliminar las filas existentes que provienen de la transformación de origen.

- **Caso de uso:** Aportar un contexto humano a los datos generados por máquinas. Por ejemplo, un archivo de facturación de AWS (transformación de origen) podría requerir que una persona asigne un proyecto responsable a cada etiqueta de instancia (columna editable).
- Las filas de origen son de solo lectura; solo se pueden editar las columnas añadidas.
- Los registros de superposición modifican las celdas de las filas originales de origen o añaden nuevas filas, pero no pueden eliminar filas de origen.

**Tema principal:** [Tablas y tipos de tablas](../../../../studio/new-uc/concepts-architecture/data-architecture/table-types.html)
