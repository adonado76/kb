---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Propiedades del objeto modelo"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia del estudio de modelos"
  - "Objetos modelo"
source_path: "studio/new-uc/reference/model-studio-reference/model-objects-properties.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Propiedades del objeto modelo

Cada objeto del modelo tiene propiedades configurables que controlan su comportamiento en el modelo.

**Características principales**

|  |  |  |  |
| --- | --- | --- | --- |
| **Propiedad** | **Tipo** | **Descripción** | **Notas** |
| Nombre | Serie | Nombre visible del objeto modelo | Debe ser único dentro del proyecto |
| Tabla | Referencia | La tabla de transformación subyacente | La tabla debe incluir el paso «Modelo» |
| Identificador | Columna(s) | Columnas que identifican de forma única las filas | Similar a una clave principal |
| Descripción | Serie | Documentación opcional | Se muestra en el diagrama del modelo |
| Métricas | Selección múltiple | ¿Qué métricas se aplican a este objeto? | Coste, presupuesto, previsión, etc. |

**Configuración del identificador de tabla**

El identificador de la tabla determina el nivel de detalle del objeto del modelo. De forma predeterminada, TBM Studio crea un identificador que identifica de forma única cada fila. Puede personalizar esto para mejorar la precisión de los informes y la asignación.

**Opciones de configuración del identificador**

|  |  |  |
| --- | --- | --- |
| **Opción** | **Comportamiento** | **Caso de uso** |
| Predeterminado (a nivel de fila) | Cada fila se considera única | Máximo nivel de detalle para el seguimiento y la elaboración de informes |
| Una sola columna | Agrupa las filas según el valor de una columna | Agrupar por departamento, cuenta o categoría |
| Varias columnas | Agrupa las filas por combinación de columnas | Se requiere una combinación única (por ejemplo, proveedor + cuenta) |

Consejo: Ten en cuenta los tiempos de cálculo y el rendimiento a la hora de elegir el nivel de detalle. Una mayor granularidad ofrece más detalle, pero aumenta el tiempo de procesamiento.

**Ejemplo: Creación de un identificador personalizado**

Para agrupar los gastos por departamento en lugar de por transacciones individuales:

1. Haz clic en el paso «Modelo» en el flujo de transformación de la tabla
2. Haz clic en la tabla en la vista de una sola tabla
3. En el panel «Filas», marca la columna «Departamento»
4. Guardar cambios: los costes ahora están agrupados por departamento

Advertencia: Cambiar el identificador de un objeto de modelo existente afecta a todas las asignaciones que hacen referencia a él. Revisa las asignaciones posteriores antes de realizar cambios.

*→ Consulte [«Configurar identificadores de tablas» para obtener información detallada sobre el procedimiento](../../howtoguides/build-cost-model/create-allocation.html)*

**Tema principal:** [Objetos modelo](../../../../studio/new-uc/reference/model-studio-reference/model-objects.html)
