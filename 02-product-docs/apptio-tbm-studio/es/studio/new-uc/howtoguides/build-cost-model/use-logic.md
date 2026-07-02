---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Utilizar la lógica de correspondencia para las asignaciones"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Crear modelos de costes"
  - "Modelización avanzada"
source_path: "studio/new-uc/howtoguides/build-cost-model/use-logic.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Utilizar la lógica de correspondencia para las asignaciones

## Objetivo

Configure las relaciones entre los datos para que las filas de origen se asignen dinámicamente a las filas de destino durante la asignación, lo que elimina la necesidad de utilizar múltiples líneas de asignación cuando los datos cambian.

## Cuándo utilizar este procedimiento

Utiliza la lógica de coincidencia (relaciones entre datos) cuando:

- Debe asignar los costes de una tabla de origen a filas específicas de la tabla de destino (por ejemplo, los costes del centro de datos a los servidores de ese mismo centro de datos)
- Las tablas de origen y destino comparten una dimensión común (por ejemplo, centro de datos, región, ID de proveedor, categoría de aplicación)
- Es mejor evitar crear líneas de asignación independientes para cada valor único
- Los nuevos elementos (por ejemplo, nuevos centros de datos) deberían gestionarse automáticamente sin necesidad de reconfiguración

**Requisitos previos**

- Las tablas de origen y destino se han añadido al modelo mediante los pasos del modelo
- Ambas tablas contienen una columna con valores coincidentes (la columna de relación)
- Tablas seleccionadas para su edición

## Tiempo estimado

15-20 minutos

## Comprender el concepto

Sin una lógica de correspondencia, tendrías que crear una línea de asignación independiente para cada valor único. Por ejemplo, para asignar los costes del centro de datos únicamente a los servidores de ese mismo centro de datos, podrías crear:

- Asignación 1: De filtro = «SEA», A filtro = «SEA»
- Asignación 2: De filtro = «NYC», A filtro = «NYC»
- Y así sucesivamente para cada centro de datos...

No se recomienda este enfoque, ya que genera una carga de mantenimiento adicional y obliga a añadir nuevas líneas de asignación cada vez que cambian los datos.

La opción **«Relación de datos»** resuelve este problema creando una única línea de asignación que divide automáticamente la asignación en grupos en función de los valores coincidentes de las columnas. Cada valor único de la columna de relación de datos da lugar a un valor de ORIGEN independiente y a un conjunto correspondiente de filas de destino.

## Ejemplo de situación

**Antes** : Tienes una tabla «Data Centers» con los costes (100 000 $ para SEA, 80 000 $ para NYC) y una tabla «Servers» con servidores en varios centros de datos. Sin una lógica de asignación, los 180 000 dólares se distribuirían proporcionalmente entre todos los servidores.

**Después** : Al establecer una relación de datos en la columna «Centro de datos», los costes de SEA (100 000 $) se asignan únicamente a los servidores de SEA, y los costes de NYC (80 000 $) se asignan únicamente a los servidores de NYC.

**Pasos**

1. En el Explorador de proyectos, haz clic en la tabla de origen y, a continuación, haz clic en el paso «Modelo» del proceso de transformación.
2. En el diagrama de Sankey, haz clic en «Añadir asignación» debajo del encabezado «Asignaciones» (o haz clic en una asignación existente para editarla).
3. En la sección «Asignar», seleccione las métricas a las que se aplicará la asignación (por ejemplo, «Coste», «Presupuesto»).
4. En «Uso», seleccione el tipo de asignación (valor ponderado, equidistribuido u otro método de distribución).
5. En «Para», selecciona la tabla de destino.
6. Busca la sección «Relación de datos» en el panel de configuración de la asignación.
7. Si la opción «Relación automática» está activada, desmarca la casilla para configurar relaciones explícitas.
8. En «Columna de origen», seleccione la columna de la tabla de origen que contenga los valores coincidentes (por ejemplo, «Centro de datos»).
9. En la columna «Destino», seleccione la columna correspondiente de la tabla de destino.
10. (Opcional) Para añadir criterios de coincidencia adicionales, repite los pasos 8 y 9 para cada par de columnas adicional. Todas las relaciones deben coincidir para que se asigne el valor.
11. Haz clic en «Vista previa» para comprobar que los resultados de la asignación muestran que los costes se distribuyen en las filas correspondientes.
12. Haz clic en «Guardar» para aplicar los cambios.

## Resultados previstos

La vista previa de la asignación muestra:

- Costes de las fuentes agrupados por tus columnas de relación
- Cada valor único cuenta con su propio conjunto de costes
- Las filas de destino reciben costes únicamente de las filas de origen correspondientes

## Uso de relaciones de datos múltiples

Puedes especificar más de una relación cuando necesites realizar una coincidencia en varias dimensiones. Por ejemplo, para asignar los costes de los proveedores a las aplicaciones tanto por ID de proveedor como por región:

- Columna de origen 1: ID del proveedor → Columna de destino 1: ID del proveedor
- Columna de origen 2: Región → Columna de destino 2: Región

Nota: Cuando se especifican varias relaciones, ***todas*** ellas deben coincidir para que se asigne el valor. Una fila debe coincidir tanto en el ID de proveedor como en la región para recibir los costes.

## Errores habituales

- Valores que no coinciden: Asegúrate de que los valores de las columnas de origen y destino coincidan exactamente (teniendo en cuenta las mayúsculas y minúsculas y los espacios en blanco). Los valores que no coinciden dan lugar a costes no asignados.
- Valores NULL: Las filas que contengan un valor NULL en la columna de relación no se emparejarán y los costes permanecerán sin asignar.
- Relaciones automáticas heredadas: si aparecen errores relacionados con la «operación de unión del modelo heredado», desmarque la casilla de verificación «Relación automática» y configure explícitamente las columnas de origen y destino.
- Demasiadas relaciones: añadir demasiados criterios de coincidencia puede hacer que no se encuentren coincidencias. Empieza por una o dos relaciones clave.

## Tareas relacionadas

- [Configurar columnas de ponderación](config-wc.html)
- [Gestionar los costes no asignados](handle-unallocated-costs.html)
- [Seguimiento de los flujos de costes a lo largo del modelo](trace-cost-flow.html)

**Tema principal:** [Modelización avanzada](../../../../studio/new-uc/howtoguides/build-cost-model/adv-model.html)
