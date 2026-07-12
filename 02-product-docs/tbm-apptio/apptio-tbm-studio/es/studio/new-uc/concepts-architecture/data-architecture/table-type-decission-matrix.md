---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Matriz de decisión en forma de tabla"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Arquitectura de datos"
  - "Tablas y tipos de tablas"
source_path: "studio/new-uc/concepts-architecture/data-architecture/table-type-decission-matrix.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Matriz de decisión en forma de tabla

Utiliza esta guía para elegir el tipo de mesa más adecuado para tu caso:

|  |  |  |
| --- | --- | --- |
| **Tus necesidades** | **Tipo de mesa recomendado** | **Por qué** |
| Importar archivos de datos externos (contabilidad general, presupuesto, previsiones) | Fuente / Tabla de archivos | Diseñado específicamente para la importación de archivos con detección y validación automáticas |
| Limpiar, unir o reorganizar datos | Tabla de transformaciones | Flujo de pasos configurables para la preparación de datos |
| Introducción manual de datos desde cero | Tabla en blanco editable | Los usuarios definen todas las filas y los valores; no hay dependencia de fuentes anteriores |
| Anotar o enriquecer datos generados automáticamente | Tabla editable con formato avanzado | Combina datos automatizados con el criterio humano |
| Exportar datos del modelo a sistemas externos | Tabla publicada | Esquema estable, accesible mediante API, diseñado para la salida de datos |

**Tema principal:** [Tablas y tipos de tablas](../../../../studio/new-uc/concepts-architecture/data-architecture/table-types.html)
