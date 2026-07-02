---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Costes no asignados"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Arquitectura del modelo"
source_path: "studio/new-uc/concepts-architecture/model-architecture/unallocated-costs.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Costes no asignados

Los costes no asignados son uno de los conceptos más importantes que hay que comprender en la modelización de costes. Son costes que se introdujeron en el motor de asignación pero que no encontraron un destino al que asignarse: dinero que se ha «quedado en el tintero» de tu modelo.

## ¿Qué son los costes no asignados?

Cuando se ejecuta una asignación, se intenta distribuir cada dólar de la fuente a uno o varios destinos. Si el controlador o la lógica de asignación no pueden encontrar un destino para una parte de los costes de origen, dichos costes quedan sin asignar. Se quedan en el objeto de origen en lugar de fluir hacia abajo.

Los costes no asignados no son un error en el sentido tradicional, sino una señal. Te dicen que las reglas de tu modelo no tienen en cuenta todos tus datos. En un modelo bien ajustado, los costes no asignados deberían ser mínimos.

## Causas comunes

|  |  |  |
| --- | --- | --- |
| **Causa** | **Ejemplo** | **Resolución** |
| Faltan datos del conductor | La tabla de recuento de ETC no incluye una unidad de negocio de reciente creación, por lo que los costes destinados a dicha unidad no tienen ningún peso que distribuir | Actualiza la tabla de controladores para incluir la entidad que falta |
| Valores de dimensiones que no coinciden | Los datos de origen utilizan el código de proveedor « “AWS-001” », pero la tabla de destino utiliza « Amazon Web Services » como clave de coincidencia | Estandarizar los valores de las dimensiones mediante asignaciones de transformación |
| Tablas de correspondencias incompletas | En la tabla de correspondencias que vincula las aplicaciones con las unidades de negocio faltan 15 aplicaciones que se han añadido recientemente | Añade las asignaciones que faltan a la tabla de asignaciones |
| Problemas relacionados con la calidad de los datos | Una columna de ponderación contiene valores nulos o no numéricos en algunas filas, lo que hace que estas queden excluidas de la asignación | Limpiar los datos de ponderación en Data Studio |
| Nuevas categorías que aún no se han modelado | Aparece un nuevo tipo de gasto en los datos del libro mayor que no se ajusta a ninguna regla de asignación existente | Añadir una nueva regla de asignación o una nueva correspondencia de categorías |

## Estrategias de gestión

**Estrategia 1: Investigar y resolver**

Lo mejor es considerar los costes no asignados como un indicador de la calidad de los datos y abordar la causa raíz. Utilice la vista previa de asignación del Modelador de objetos individuales para identificar qué filas siguen sin asignar y, a continuación, analice el origen del problema para determinar la causa.

**Pasos:**

1. Abre el objeto del modelo en el Modelador de objetos individuales
2. Revisa la vista previa de la asignación para identificar las filas sin asignar
3. Comprueba si hay lagunas en los datos de los conductores y en la lógica de emparejamiento
4. Actualiza las tablas de transformación o los datos de mapeo según sea necesario
5. Vuelve a ejecutar la compilación y comprueba que los importes no asignados disminuyen

**Estrategia 2: Fondos residuales**

Cuando algunos costes no pueden asignarse de forma clara a un objetivo concreto, se puede crear un fondo residual, es decir, un objeto de modelo genérico que recopila los costes no asignados para facilitar su visibilidad y su posterior análisis.

- **Cuándo utilizarlo:** cuando hay un pequeño porcentaje de gastos que no se pueden clasificar en ninguna categoría y se desea que aparezcan en los informes en lugar de dejarlos ocultos.
- **Precaución:** un gran volumen de residuos es una señal de alerta. Si más del 5-10 % de tus costes se destinan a gastos residuales, es probable que tu modelo necesite una revisión.

**Estrategia 3: Distribución uniforme de los residuos**

Como último recurso, puedes repartir los costes no asignados de manera equitativa entre todos los objetivos. Esto garantiza que tu modelo «cuadre» (el total de origen es igual al total de destino), pero sacrifica la precisión de la asignación.

- **Ventajas:** El modelo ofrece un balance general; no hay costes ocultos
- **Contras:** Reduce la precisión; asigna costes a entidades que quizá no los hayan incurrido

Nota:

**Realizar un seguimiento continuo de los costes no asignados**

Después de cada compilación, comprueba los costes no asignados. Un modelo que el mes pasado estaba perfectamente equilibrado puede presentar este mes nuevos importes sin asignar debido a cambios en los datos. Adquiere el hábito de revisar los importes sin asignar como parte de tu proceso de cierre mensual.
