---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Tablas y tipos de tablas"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Arquitectura de datos"
source_path: "studio/new-uc/concepts-architecture/data-architecture/table-types.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Tablas y tipos de tablas

Las tablas son los contenedores de datos fundamentales en TBM Studio. Todos los datos que entran, pasan por o salen de la plataforma lo hacen a través de una tabla. TBM Studio ofrece varios tipos de tablas, cada una de ellas diseñada para desempeñar una función específica en el ciclo de vida de los datos.

## Fuentes / Tablas de archivos

**Objetivo:** Importar datos externos a TBM Studio desde archivos o conexiones a bases de datos.

Una tabla de origen es el punto de entrada de tus datos. Cuando creas una nueva tabla y subes un archivo de CSV o Excel, TBM Studio crea una tabla de origen con un proceso de transformación asociado. La plataforma analiza tu archivo, detecta automáticamente los tipos de columna (Etiqueta, Numérico o Estado) y muestra una vista previa para que la confirmes.

Las tablas de origen admiten varios métodos de importación de datos:

- **Carga de archivos:** Arrastra y suelta los archivos o selecciona la ruta para cargar archivos de formato CSV, TSV, XLS o XLSX. La plataforma analiza el archivo y detecta automáticamente la fila de encabezado, las filas de datos y los tipos de columna.
- **DataLink (Clásico) Conector:** Importa datos utilizando un conector predefinido para extraerlos directamente de bases de datos o sistemas externos.
- **Tabla generada:** crea una nueva tabla derivada de una tabla existente en el proyecto. La nueva tabla no estará vinculada a la original.
- **Tabla existente (vinculada):** crea una nueva tabla a partir de una tabla existente, manteniendo un vínculo para que la tabla derivada permanezca conectada a su origen.

Una vez cargados, tus datos pasan a formar parte de un proceso de transformación en el que puedes añadir pasos para limpiarlos, filtrarlos, combinarlos y reestructurarlos antes de que se incorporen al modelo de costes.

Nota:

**Cuándo utilizar tablas de origen**

Utiliza las tablas de origen siempre que necesites importar datos externos a TBM Studio. Esto incluye exportaciones del libro mayor, archivos de presupuesto, hojas de cálculo con previsiones, inventarios de activos y cualquier otro dato que provenga de fuera de la plataforma.

- **[Transformar tablas](../../../../studio/new-uc/concepts-architecture/data-architecture/transform-tables.html)**
- **[Tablas editables](../../../../studio/new-uc/concepts-architecture/data-architecture/editable-tables.html)**
- **[Cómo encajan las tablas editables en el flujo de datos](../../../../studio/new-uc/concepts-architecture/data-architecture/editable-tables-fir-data-flow.html)**
- **[Tablas publicadas](../../../../studio/new-uc/concepts-architecture/data-architecture/published-tables.html)**
- **[Matriz de decisión en forma de tabla](../../../../studio/new-uc/concepts-architecture/data-architecture/table-type-decission-matrix.html)**
