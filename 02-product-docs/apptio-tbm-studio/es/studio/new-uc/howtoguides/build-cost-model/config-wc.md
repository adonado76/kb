---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Configurar columnas de ponderación"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Crear modelos de costes"
  - "Modelización avanzada"
source_path: "studio/new-uc/howtoguides/build-cost-model/config-wc.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configurar columnas de ponderación

## Objetivo

Configure asignaciones de valores ponderados que distribuyan los costes de forma proporcional en función de una columna numérica, en lugar de repartirlos de manera uniforme entre todas las filas de destino.

## Cuándo utilizar este procedimiento

Utiliza las columnas de ponderación cuando:

- No todas las entidades de destino son iguales (por ejemplo, los servidores tienen un número diferente de CPU y las aplicaciones tienen un número diferente de usuarios)
- Dispones de un indicador cuantificable que refleja el consumo o la capacidad relativos
- Quieres que los grandes consumidores paguen proporcionalmente más que los pequeños consumidores
- Una distribución uniforme no reflejaría con precisión el consumo real ni los patrones de uso

**Requisitos previos**

- Las tablas de origen y destino se han añadido al modelo
- La tabla de destino contiene una columna numérica con valores de ponderación
- La columna «Ponderación» contiene valores numéricos distintos de nulo y no negativos (véanse las notas sobre los valores negativos más abajo)
- Tablas seleccionadas para su edición

## Tiempo estimado

10-15 minutos

## Comprender el concepto

Una asignación de valores ponderada distribuye los costes en función de la proporción (tamaño relativo) de los valores de una columna que selecciones de la tabla de destino. La fórmula es:

Asignación a la fila = FUENTE × (peso de la fila / peso total de todas las filas coincidentes)

Por ejemplo, si vas a distribuir 100 000 dólares entre cinco servidores en función del número de CPU:

|  |  |  |
| --- | --- | --- |
| **Servidor** | **Número de CPU** | **Asignación** |
| Servidor A | 4 | 10 000 $ (4/40 = 10 %) |
| Servidor B | 8 | 20 000 $ (8/40 = 20 %) |
| Servidor C | 16 | 40 000 $ (16/40 = 40 %) |
| Servidor D | 8 | 20 000 $ (8/40 = 20 %) |
| Servidor E | 4 | 10 000 $ (4/40 = 10 %) |
| Total | 40 | 100 000 dólares |

## Pasos

1. En el Explorador de proyectos, haz clic en la tabla de origen y, a continuación, haz clic en el paso «Modelo» del proceso de transformación.
2. En el diagrama de Sankey, haz clic en «Añadir asignación» (o haz clic en una asignación existente para editarla).
3. En la sección «Asignar», selecciona las métricas a las que se aplicará la asignación.
4. En «Uso», seleccione «Valor ponderado» como tipo de asignación.
5. En «Para», selecciona la tabla de destino.
6. En las opciones de distribución, selecciona «Ponderar por».
7. Selecciona la columna numérica de la tabla de destino que contenga los valores de ponderación (por ejemplo, «Número de CPU», «Número de usuarios» o «Metros cuadrados»).
8. (Opcional) Configura las relaciones entre los datos si necesitas hacer coincidir las filas del origen con las del destino.
9. Haz clic en «Vista previa» para comprobar que los costes se distribuyen proporcionalmente según tu columna de ponderación.
10. Haz clic en «Guardar» para aplicar los cambios.

## Resultados previstos

La vista previa de la asignación muestra:

- El valor de la ponderación de cada fila objetivo y su porcentaje respecto al total
- Coste asignado proporcional a la relación de pesos
- Coste total asignado que coincide con el importe de origen

## Avanzado: Uso de otras ponderaciones de pilotos

En TBM Studio 12.5 y versiones posteriores, puede utilizar «Otro controlador» para ponderar una asignación basándose en los resultados de otra asignación. Esto resulta útil cuando se desea aplicar una ponderación uniforme en varias asignaciones.

Por ejemplo, si ya ha asignado los costes de personal a las torres de recursos de TI, podría utilizar ese mismo patrón de ponderación para asignar los costes del proyecto a las torres de recursos de TI. Seleccione «Otro controlador» y elija el controlador Labor existente para mantener la coherencia.

## Errores habituales

- Valores no numéricos: si la columna de ponderación contiene al menos un valor no numérico, se ignorará la ponderación y los costes se distribuirán de manera uniforme. Limpia tus datos para asegurarte de que todos los valores sean numéricos.
- Todo son ceros: si todos los valores de ponderación son 0, los costes se distribuyen de manera uniforme entre las filas de destino (comportamiento predeterminado mediante la función Ratio).
- Valores NULL: Las filas que contengan un valor NULL en la columna de ponderación no recibirán ninguna asignación.
- Valores negativos: Por defecto, TBM Studio no realiza la asignación cuando hay ponderaciones negativas, ya que esto puede dar lugar a resultados inesperados. Si tienes que utilizar pesos negativos, consulta la documentación sobre el manejo de números negativos.

Consejo: Comprueba siempre que la columna de ponderación esté correctamente definida como numérica en el paso de importación de tu canalización de transformación. Los códigos que parecen números pero se almacenan como texto provocarán que la ponderación falle sin que se detecte ningún error.

## Tareas relacionadas

- [Utilizar la lógica de correspondencia para las asignaciones](use-logic.html)
- Crear asignaciones de fórmulas (Referencia de la sección « 5.2 »)
- [Gestionar los costes no asignados](handle-unallocated-costs.html)

**Tema principal:** [Modelización avanzada](../../../../studio/new-uc/howtoguides/build-cost-model/adv-model.html)
