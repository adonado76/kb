---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Conductores"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia del estudio de modelos"
source_path: "studio/new-uc/reference/model-studio-reference/drivers.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Conductores

Los controladores aportan un valor a un objeto de modelo y determinan cómo se distribuye ese valor. Son el mecanismo principal para vincular los datos de origen con el modelo de costes.

## Tipos de controladores

TBM Studio admite tres tipos de controladores, cada uno de los cuales se adapta a diferentes necesidades de asignación.

**Conductor de unidad**

**Descripción:** Un controlador de unidad introduce un valor en un objeto de modelo a partir de una columna de la tabla subyacente. Los controladores de unidad suelen utilizarse en el nivel más bajo de un modelo, donde los datos financieros se introducen en el sistema.

**Configuración del controlador de la unidad**

|  |  |  |  |
| --- | --- | --- | --- |
| **Parámetro** | **Obligatorio** | **Valores** | **Descripción** |
| Nombre | Sí | Cadena de texto | Nombre que se muestra para el controlador |
| Añadir a | Sí | Selección de métricas | A qué métricas se aplica este controlador |
| Uso de | Sí | Columna, Métrico, Fórmula | Origen del valor del controlador |
| Notas | Nee | Cadena de texto | Documentación del controlador |

**Uso de las opciones**

|  |  |  |
| --- | --- | --- |
| **Opción** | **Origen** | **Caso de uso** |
| Columna | Valor de una columna de la tabla | El más común. Asignación directa desde la columna de costes/presupuesto |
| Métrica | Valor de otra métrica del modelo | Cuando el controlador depende de otra métrica calculada |
| Fórmula | Valor calculado a partir de una fórmula | Cálculos complejos o referencias entre tablas |

**Ejemplo: Creación de un controlador de unidad**

Crear un controlador de unidad para OpEx tiene un coste de:

1. Echa un vistazo a la tabla y haz clic en el paso «Modelo»
2. En el área de trabajo del modelo, haz clic en «Añadir controlador de unidad» en la columna «Controladores»
3. En «Añadir a», selecciona la métrica «Coste»
4. En «Usar», selecciona «Columna» y elige la columna « OpEx »
5. Guardar cambios

*→ Consulte la sección [«Añadir controladores de dispositivos» para conocer el procedimiento detallado](../../howtoguides/build-cost-model/adv-model.html)*

**Controlador de asignación**

**Descripción:** Los controladores de asignación aparecen en la parte izquierda del área de trabajo de edición del modelo y representan las asignaciones entrantes procedentes de otros objetos del modelo. Se crean automáticamente al configurar una asignación de un objeto de origen a un objeto de destino.

**Nota:** Los controladores de asignación aparecen entre paréntesis cuando se utilizan los nombres predeterminados. Los nombres personalizados no llevan paréntesis.

**Piloto de Fórmula**

**Descripción:** Un conductor de fórmulas utiliza un cálculo para determinar el valor. Las fórmulas pueden hacer referencia a columnas de tablas, a otras métricas o a valores de otras tablas.

**Ejemplos de sintaxis de fórmulas**

|  |  |
| --- | --- |
| **Finalidad** | **Fórmula** |
| Columna de referencia en la misma tabla | table.column nombre |
| Suma todos los valores de una columna | tabla:nombre de columna |
| Suma condicional | tabla:columna[ column2= «valor»] |
| Métrica de referencia | $\_ (abreviatura de «nombre métrico») |
| Referencia entre proyectos | proyecto!tabla:nombre de columna |

*→ Consulte la sección «Fórmulas y funciones» en 5.4: para obtener una referencia completa de fórmulas*

- **[Opciones de configuración del controlador](../../../../studio/new-uc/reference/model-studio-reference/driver-config-option.html)**
- **[Requisitos relativos a los datos de los conductores](../../../../studio/new-uc/reference/model-studio-reference/driver-data-requirements.html)**
- **[Reglas de validación de controladores](../../../../studio/new-uc/reference/model-studio-reference/driver-validation-rules.html)**
- **[Eliminar un controlador](../../../../studio/new-uc/reference/model-studio-reference/delete-driver.html)**
