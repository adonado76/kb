---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Configurar el aprendizaje automático para los grupos de costes"
breadcrumb: []
source_path: "studio/data_studio/configuremachinelearning.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configurar el aprendizaje automático para los grupos de costes

**Se aplica a** : TBM Studio 12.7 y posteriores

Apptio utiliza técnicas de aprendizaje automático para predecir el conjunto de costes aplicable basándose en la información de la cuenta. Un nuevo paso del pipeline, **Asignar Pools de Costes**, se añade automáticamente a las tablas que se mapean a Datos Maestros del Plan General de Contabilidad utilizando **Mapear Columnas**.

**Requisitos previos**

- Costing Standard Componente de la fuente de costes, actualizado a 12.6, o más reciente.
- Plan de cuentas: La información de las cuentas suele estar disponible en un sistema financiero.
  - Las columnas obligatorias son Cuenta, Descripción de cuenta y Tipo de gasto. Sin embargo, se recomiendan las columnas Grupo de cuentas y Subgrupo de cuentas.
  - Utilice el paso **Asignar Columnas** con un destino de Datos Maestros del Plan General de Contabilidad.

## Asignar el plan de cuentas a los grupos de costes

Realiza las siguientes tareas.

## Configure el paso Asignar pools de costes

En la tabla del Plan General de Contabilidad para la que desea asignar pools de costes, añada el paso **Asignar Columnas**. Elija un destino para los datos maestros del Plan General de Contabilidad. Consulte [Columnas](mapcolumns.htm "(se abre en una pestaña o una ventana nueva)") de mapa para obtener más información sobre cómo utilizar las Columnas de mapa.

Aparece el paso **Asignar pools de costes**.

![Asignar pools de costes](../../resources/images/studio_images/studioimages/studio_charts%20of%20accounts_map%20columns.png)

## Configurar los datos de referencia

1. La primera vez que se utiliza Asignar pools de costes, se emplea la pestaña **Configuración**. Haga clic en **Configurar ahora** para obtener la información de referencia sobre los grupos de costes. La pantalla se actualiza automáticamente una vez recuperada toda la información. Las tablas **de referencia de clasificación de costos ATUM** y **de referencia de clasificación de OpEx CapEx** aparecen en la categoría Tablas de referencia a la izquierda.
2. Registre estas nuevas tablas y su tabla del plan contable al mismo tiempo.

   ![Configurar los datos de referencia](../../resources/images/studio_images/studioimages/studio_chart%20of%20accounts_map%20columns.png)

   Si hay una actualización disponible, aparecerá una notificación en la pestaña **Configuración**.
3. Para actualizar las tablas de referencia en cualquier momento, consulte la tabla que desea actualizar. Navegue hasta la tabla o haga clic en los datos de referencia que desea actualizar en la pestaña **Configuración**. Las actualizaciones se muestran con un icono de advertencia amarillo.
4. Haga clic en **Actualizar datos de referencia**.

   ![Actualizar datos de referencia](../../resources/images/studio_images/studioimages/studio_reference%20table_update.png)

## Actualizar el modelo

El aprendizaje automático se basa en un modelo que produce predicciones de conjuntos de costes a partir de sus datos. Cuando configura inicialmente su tabla con Asignar pools de costes, se identifica la última versión publicada y se utiliza para predecir sus datos. Este modelo no se actualizará a lo largo del tiempo para esta tabla a menos que realice una acción explícita.

1. Para ver el modelo en el que te encuentras, haz clic en la pestaña **Configuración**.
2. Si hay una actualización disponible, aparecerá una notificación en la pestaña Configuración. Para actualizar a la última versión, haga clic en **Actualizar ahora**.

   Nota: Al revertir el documento, el modelo volverá a la versión registrada.

## Ajustar la confianza

La confianza sólo está pensada para un uso avanzado. Ajustar la confianza al alza reducirá generalmente el número de registros asignados. Para ajustar la confianza:

1. Haz clic en la pestaña **Configuración**.
2. Edite el número que aparece en el cuadro **Min Confidence %** y, a continuación, pulse **Intro**.
3. Guarda la mesa. Las asignaciones se actualizarán.

## Utilizar el mapa del árbol y el panel de vista previa

Utilice el mapa de árbol para explorar los datos asignados. Las siguientes imágenes muestran todas las iteraciones disponibles.

A la derecha del mapa de árbol hay KPI que indican cómo se asignan las filas. Cuando un usuario interactúa con el mapa de árbol, se actualizan los KPI y la tabla siguiente. Los filtros aplicados directamente a la tabla no afectarán al mapa del árbol.

El mapa de árbol tiene los siguientes elementos y capacidades:

![Utilizar el mapa de árboles](../../resources/images/studio_images/studioimages/studio_chart%20of%20accounts_assign%20cost%20pools.png)

**(1) Visualización del mapa de árbol** - Haga clic en cualquier casilla para filtrar toda la pestaña **Resumen** de este paso por el valor de esa casilla.

El mapa de árbol tiene los siguientes niveles: **Grupo de costes > Subgrupo de costes > Grupo de cuentas > Subgrupo de cuentas > Cuenta**. Si algún nivel no está disponible por no estar cartografiado, el mapa de árbol desglosará automáticamente hasta el siguiente nivel.

Una vez que se ha descendido, aparece la ruta utilizada para filtrar hasta el nivel actual y todos los niveles anteriores se convierten en enlaces. Haga clic en **Todos** para volver a la vista por defecto, sin filtrar.

El estado de la asignación en el mapa de árbol está codificado por colores (véase el paso 4) y, cuando hay una mezcla de filas asignadas automáticamente y por reglas personalizadas, aparece una mezcla de los dos colores:

![Visualización del mapa de árboles](../../resources/images/studio_images/studioimages/studio_assign%20cost%20pools_overview.png)

**(2) Descripción** - Pase el ratón por encima de las casillas en el mapa de árbol para ver las descripciones y el recuento de filas dentro de esa casilla según el método de asignación. Cuando se muestre Cuenta, se mostrará Descripción de la cuenta.

Nota: El hover se retrasa ligeramente para no bloquear tu capacidad de interactuar con la mesa rápidamente.

**(3) Crear regla** - Este botón se activa cuando se filtra al menos un valor proporcionado por el cliente. Si se rellenan todas las columnas, esto ocurre después de hacer clic en un Grupo de cuentas. Las reglas creadas se aplicarán a todas las filas del grupo proporcionado por el cliente y, por lo tanto, pueden afectar a más filas de las que aparecen en el mapa de árbol.

Después de hacer clic en **Crear regla**, vaya a la pestaña **Reglas** para terminar de configurar la regla.

**(4) KPI** : los indicadores clave de rendimiento (KPI) a la derecha muestran cuántas filas están asignadas y mediante qué método. Los porcentajes se redondean normalmente. Los colores de los KPI son una leyenda de los colores del gráfico.

**(5)** Tabla - La tabla muestra todas las filas que coinciden con el estado del mapa de árbol. Para filtrar aún más la tabla, introduzca texto en el campo Buscar situado antes de cada encabezado. También puede hacer clic con el botón derecho en cualquier valor de la tabla y elegir **Filtrar por valor** para añadir texto al campo **Buscar**.

Las opciones son:

- Por defecto, la tabla no está ordenada. Haga clic en las cabeceras para mostrar las opciones para cambiar la clasificación. Cualquier acción que cambie el estado de las filas de la tabla actualizará inmediatamente la tabla y volverá a aplicar la ordenación.
- La tabla permite modificar filas individuales. Las filas se identifican por todos sus valores, por lo que si hay filas idénticas, se tratarán como una sola. Haga clic en **el grupo de costos** o **en el subgrupo de costos** para ver todas las asignaciones disponibles. Elija una opción para crear una regla para esa fila.
- Para asignar un grupo de costes a una fila, haga clic en la columna **Grupo de costes** o **Subgrupo de costes**. Aparece el menú **Asignar a** y muestra toda la lista de grupos y subgrupos de costes disponibles para su selección.

**(6) Estado** - La columna Estado tiene cinco estados posibles:

- Sin asignar
- Conflictos
- Automático
- Regla
- Verificado

Los colores coinciden con la leyenda de los KPI junto al mapa del árbol, excepto los verificados, que son de color verde oscuro. Además, puede interactuar con la columna **Estado** para cambiar el estado de cada fila.

Las opciones son:

- Haga clic en el icono de valor de la columna **Estado** cuando se asigne automáticamente o se asigne una regla personalizada para verificar esa fila. Las filas verificadas tienen valores bloqueados y no cambiarán aunque se les asignen automáticamente cambios en el pool de costes.
- Haga clic en **Conflictos** para verificar esa fila.
- Haga clic en **Sin asignar** para mostrar el mismo menú disponible en las columnas Grupo de costes y Subgrupo de costes.

## Crear y gestionar reglas

Utilice reglas para establecer el grupo de costes y el subgrupo de costes de las filas de la tabla que pueden aplicarse en función de los valores de las filas. Las reglas siguen aplicándose a todas las subidas en esa versión de la tabla.

La tabla de **Reglas** se encuentra en la parte superior izquierda de la pestaña Reglas. Por defecto, contiene el nombre de la regla y el recuento de filas que coinciden con los criterios de la regla, desglosados por cómo se aplicó la regla.

![Crear y gestionar reglas](../../resources/images/studio_images/studioimages/studio_assign%20cost%20pools_rules.png)

Para ver las opciones para mostrar u ocultar columnas, haga clic con el botón derecho del ratón en la cabecera.

## Crear una nueva regla

Las reglas aplican condiciones a la tabla y luego asignan un pool de costes.

1. Seleccione **Nueva Regla** para crear una regla sin condiciones y un pool de costes assignment.Use un nombre de regla y una descripción para ayudar a rastrear las decisiones tomadas en cada regla.

   Utilice un nombre de regla y una descripción para facilitar el seguimiento de las decisiones tomadas en cada regla.
2. Edita la regla.

## Editar una regla

Para editar una regla manualmente, añada condiciones y seleccione los criterios en los que se basará la selección.

- Haga clic con el botón derecho en un valor de la tabla y, a continuación, haga clic en **Añadir a regla** para añadir otro criterio a la regla. Si no hay ninguna regla seleccionada, se creará una nueva. A continuación, añada el criterio.

  Nota: Antes de eliminar una asignación en Columnas de mapa que utilizan las reglas, asegúrese de eliminar ese criterio de las reglas. Si elimina una asignación y no puede ajustar las reglas como desea, vuelva a añadir la columna, elimínela de las reglas y, a continuación, vuelva a eliminar la asignación.

## Aplicar las condiciones de la regla

Los operadores de condición siguen esta lógica:

| Nombre del operador | Descripción | Ejemplo |
| --- | --- | --- |
| Igual que | Utilizar para una coincidencia exacta. | Tipo de gasto *Igual a* OpEx |
| Contiene | Utilícelo para valores que incluyan su texto escrito pero que también puedan incluir otra información. | La cuenta *contiene* 2111 |
| Empieza por | Utilícelo cuando sepa cuál es su valor inicial. | La descripción de la cuenta *empieza por* salario |
| Termina por | Utilícelo cuando sepa en qué termina su valor. | Descripción de la cuenta *Termina con* beneficios |
| Está en | Utilícelo cuando su valor sea uno de los textos separados por comas de la lista. | La cuenta *está en* 2111,2112 |
| No igual | Elimina las filas que no coinciden con el texto introducido. | Tipo de gasto *no igual* CapEx |
| No contiene | Elimina las filas que no contienen el texto introducido. | La descripción de la cuenta *no contiene* mantenimiento |
| No empieza por | Elimina las filas que no empiezan por el texto introducido. | La cuenta *no empieza por* ACCT\_ |
| No termina con | Elimina las filas que no terminan con el texto introducido. | La cuenta *no acaba en* 23 |
| No está en | Elimina las filas que no coinciden con una de las listas de cadenas de texto introducidas. | La cuenta *no está en* 2111,2112 |
| Es nulo | Se utiliza cuando el valor está vacío. | El tipo de gasto *es nulo* |
| No es nulo | Se utiliza cuando el valor no está vacío. | El tipo de gasto *no es nulo* |

**NOTAS** :

- Puede añadir condiciones en la misma columna dos veces. Sin embargo, después de guardar una regla, las condiciones se condensarán en **Si está dentro** o **No está dentro** utilizando comodines para abordar otras permutaciones.
- Las columnas sólo funcionan por coincidencias positivas (Está dentro, Es igual, Contiene, etc.) o por coincidencias negativas (No es igual, etc.).
- Cuando se utiliza **Is Null** en una columna, dicha columna no puede utilizarse para otros operadores.
- Las reglas sólo pueden crearse o editarse en la rama troncal. Por lo tanto, para crear o editar reglas, fusione su tabla y luego complete las ediciones.

## Resolver conflictos de normas

Cuando más de una regla es aplicable a una o más filas y ninguna regla es más específica que la otra, la(s) fila(s) se establecerá(n) en estado **Conflicto** y no se asignará(n) ningún pool o subpool de costes a la(s) fila(s). Las reglas en conflicto se enumeran en la pestaña **Conflictos**.

Una norma contradictoria puede resolverse de dos maneras:

- Seleccione la regla que desea actualizar en **Seleccionar una regla**, modifique una o varias condiciones y, a continuación, haga clic en **Actualizar regla**.
- Haga clic con el botón derecho del ratón en la regla que desea sustituir y seleccione **Verificar**. Esto hará que la regla elegida anule las otras reglas con las que estaba en conflicto.

## Verificar filas

Puede verificar que cualquier línea asignada a un pool de costes ha sido revisada manualmente. Al hacerlo, se anulará cualquier otra forma de cambiar la fila. La fila puede verificarse independientemente de si la asignación se ha completado mediante aprendizaje automático o mediante intervención manual utilizando reglas. Los cambios en el modelo no afectarán a las filas verificadas.

## Asignación de grupos de costes y control de versiones

Las tablas que contienen el paso Asignar pools de costes pueden versionarse temporalmente como cualquier otra tabla. Para más información, consulte [Versionar una tabla](version_table.htm "(se abre en una pestaña o una ventana nueva)").

## Bifurcación o retroceso

Si haces retroceder un proyecto en check in history, las reglas volverán al estado en el que se encontraban en ese momento. Cualquier regla que se añada en el futuro tendrá por defecto un número automático más alto, como reflejo de las reglas que se han creado hasta ahora.

Las reglas sólo pueden crearse o editarse en la rama troncal. Por lo tanto, para crear o editar reglas, primero fusione su tabla y luego complete cualquier edición.

**VER TAMBIÉN** :

- [Columnas del mapa](mapcolumns.htm "(se abre en una pestaña o una ventana nueva)")
- [Asignar grupos de costes con aprendizaje automático](assigncostpools.htm "(se abre en una pestaña o una ventana nueva)")
- [Preguntas frecuentes sobre las columnas del mapa](faqmapcolumns.htm "(se abre en una pestaña o una ventana nueva)")
