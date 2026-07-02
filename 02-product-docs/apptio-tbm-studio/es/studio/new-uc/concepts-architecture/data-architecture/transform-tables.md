---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Transformar tablas"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Arquitectura de datos"
  - "Tablas y tipos de tablas"
source_path: "studio/new-uc/concepts-architecture/data-architecture/transform-tables.html"
images:
  - "resources/images/studio_images/transform-pipeline.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Transformar tablas

**Objetivo:** Limpiar, combinar y reorganizar los datos en TBM Studio.

Cada tabla de « Data Studio » tiene un proceso de transformación asociado. Una tabla de transformación es el resultado de ese proceso: el resultado de aplicar uno o varios pasos de transformación a los datos de origen. También puedes crear nuevas tablas de transformación a partir de las ya existentes, creando cadenas de transformaciones que refinan progresivamente tus datos.

Piensa en las tablas de transformación como una cadena de montaje. Los datos brutos entran por un extremo, pasan por una serie de estaciones de procesamiento (pasos de transformación) y salen por el otro extremo como datos limpios y estructurados, listos para el modelo de costes.

![Canal de transformación](../../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/transform-pipeline.png)

Características principales de las tablas de transformación:

- Los pasos se ejecutan de arriba abajo, en el orden en que aparecen en el proceso.
- Puedes añadir, eliminar, cambiar el orden y editar los pasos en cualquier momento.
- El paso «Tabla» al final del proceso siempre muestra el resultado final de todas las transformaciones.
- Los resultados de las transformaciones se pueden utilizar como entradas para otras transformaciones, creando así cadenas de procesamiento de datos reutilizables.

**Tema principal:** [Tablas y tipos de tablas](../../../../studio/new-uc/concepts-architecture/data-architecture/table-types.html)
