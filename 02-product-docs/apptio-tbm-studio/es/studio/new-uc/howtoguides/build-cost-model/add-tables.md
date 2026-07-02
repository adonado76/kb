---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Añadir una tabla al modelo"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Crear modelos de costes"
  - "Conceptos básicos sobre modelos"
source_path: "studio/new-uc/howtoguides/build-cost-model/add-tables.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Añadir una tabla al modelo

|  |  |
| --- | --- |
| **Tipo de contenido** | Guía práctica |
| **Destinatarios** | Analistas de negocios, equipos de TI y finanzas |
| **Tiempo estimado** | Entre 5 y 10 minutos por mesa |
| **Requisitos previos** | Tabla de transformación creada en Data Studio con los datos cargados |

## Objetivo

Añade una tabla de transformación al modelo de costes para que pueda participar en las asignaciones y aparecer en los informes del modelo.

## Cuándo utilizar este procedimiento

Siga este procedimiento cuando haya creado una tabla en Data Studio y desee incluirla en su modelo de costes. Entre los casos más habituales se incluyen:

- Añadir la tabla de fuentes de costes que contiene datos del libro mayor o financieros
- Añadir tablas de destino, como unidades de negocio, aplicaciones o servicios
- Añadir tablas intermedias como «Proveedores», «Infraestructura» o «Torres de TI»
- Incorporación de tablas de factores que se utilizarán para ponderar las asignaciones

## Antecedentes: Tablas de transformación frente a objetos de modelo

En TBM Studio, la creación de una tabla en « Data Studio » y su incorporación al modelo son pasos independientes. **Una tabla de transformación** es donde se preparan, limpian y estructuran los datos. **Un objeto de modelo** es aquel en el que la tabla forma parte del modelo de costes, con factores determinantes, asignaciones y flujos de métricas.

Al añadir un paso de modelo al proceso de transformación de una tabla, esta se convierte en un objeto de modelo. Hasta que no lo hagas, la tabla solo existe en Data Studio y no puede recibir ni asignar costes.

## Pasos

1. **Echa un vistazo a la tabla.** En el Explorador de proyectos, busca la tabla que quieras añadir al modelo. Haz clic con el botón derecho del ratón y selecciona **«Desproteger»**, o bien selecciona la tabla y haz clic en **«Desproteger»** en la pestaña «Inicio».
2. **Abre el proceso de transformación.** Haz clic en el nombre de la tabla para abrirla. Verás el proceso de transformación en la parte izquierda del espacio de trabajo, donde se muestra la secuencia de pasos aplicados a tus datos (fuente, importación, pasos de fórmula, etc.).
3. **Añade un paso de modelo.** Haz clic en **«Añadir paso»** en la parte inferior del proceso de transformación. En el selector de tipo de paso, seleccione «**Modelo** ». El paso «Modelo» se añade a tu proceso.
4. **Ver el espacio de trabajo del modelo.** Haz clic en el nuevo paso **«Modelo»** del flujo de trabajo. El espacio de trabajo muestra ahora una vista de una sola tabla en la que tu tabla aparece en el centro, con espacios para los conductores a la izquierda y los destinos de asignación a la derecha. Esta es la vista del diagrama de Sankey.
5. **Guarde sus cambios.** Haz clic en **«Guardar»** en la pestaña «Inicio» para guardar los cambios.
6. **Consúltalo en la tabla.** Cuando hayas terminado, haz clic **en «Guardar»** para que los demás puedan ver los cambios y para que se apliquen a los cálculos del modelo.

## Resultados previstos

Una vez completados estos pasos:

- La tabla aparece en la vista «Model step», con su nombre mostrado en la columna central
- La tabla es ahora un objeto modelo que puede recibir controladores y participar en asignaciones
- Puedes ver la tabla en el diagrama del modelo (Ver > Métrica modelada) junto con otros objetos del modelo
- La tabla está disponible como origen o destino al crear asignaciones a partir de otras tablas

## Errores habituales

**La tabla no contiene datos para el periodo actual.** Los cálculos del modelo son específicos para cada período. Si no hay datos cargados en tu tabla para el periodo de tiempo seleccionado actualmente, aparecerá vacía en el modelo. Comprueba que los datos estén presentes consultando la tabla en el paso «Salida» antes de añadir el paso «Modelo».

**Olvidarse de hacer el check-out antes de añadir el paso «Modelo».** Debes desproteger una tabla antes de poder modificar su canalización de transformación. Si intentas añadir un paso sin realizar el check-out, aparecerá un mensaje de error.

**Colocación de los escalones del modelo.** El paso «Model» suele ser el último paso de tu proceso (o uno de los últimos, antes de cualquier paso de seguridad a nivel de fila). Añadir pasos de transformación después del paso «Modelo» puede provocar un comportamiento inesperado.

Consejo: Si necesitas aplicar seguridad a nivel de fila a una tabla, al añadir un paso de RLS se añadirá automáticamente un paso de modelo si aún no existe. Solo se puede aplicar la seguridad a nivel de fila a las tablas modeladas.

## ¿Qué viene ahora?

- Añade [controladores](config-drivers.html) de unidad para aportar valor a tus tablas de fuentes de coste
- [Crear asignaciones](create-allocation.html) para transferir valores entre tablas
- Consulte el [diagrama del modelo](view-model-diagram.html) para ver cómo encaja su tabla en el flujo general de costes.

## Conceptos relacionados

- [Arquitectura del modelo](../../concepts-architecture/model-architecture/model-concepts-overview.html) : análisis en profundidad del funcionamiento del motor de modelado
- [Arquitectura de datos](../../concepts-architecture/data-architecture/data-architecture.html) : comprender la relación entre « Data Studio » y «Model Studio»

**Tema principal:** [Conceptos básicos del modelo](../../../../studio/new-uc/howtoguides/build-cost-model/model-basics.html)
