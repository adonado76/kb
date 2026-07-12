---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Asignar datos a datos maestros"
breadcrumb:
  - "Costing Standard"
  - "Configuración"
source_path: "cost-transparency/configuration/config-mapdata.html"
images:
  - "resources/images/studio_images/ad1.png"
  - "resources/images/studio_images/ad6.png"
  - "resources/images/studio_images/map3.png"
  - "resources/images/studio_images/mapcol2.png"
  - "resources/images/studio_images/master2.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Asignar datos a datos maestros

Después de cargar una tabla de datos de origen y transformarla si es necesario, puede asignarla a una tabla de datos maestros. Siga las siguientes instrucciones para asignar datos a una tabla de datos maestros.

Hay dos métodos disponibles para asignar datos a conjuntos de datos maestros:

- Columnas del mapa (preferidas)
- Anexar tablas

**Columnas del mapa**

El método principal (y preferido) para mapear datos es utilizar Map Columns.The La función Map Columns está diseñada para transformar su conjunto de datos de origen.

Si los datos se reutilizan para varios conjuntos de datos maestros, cree una nueva tabla utilizando la fuente de la tabla existente para cada conjunto de datos maestros y, a continuación, añada columnas de mapa.

**Añade el paso de canalización Columnas del mapa y elige un destino.**

1. Cree o consulte una tabla y añada datos a la misma. Además, puede aplicar pasos de canalización transformadores, como la partición por fecha.
2. Pasa el cursor por encima de los pasos del proceso y haz clic en **+** para añadir un nuevo paso. **Las columnas del mapa** estarán disponibles a menos que se añada un paso Modelo.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/mapcol2.png)

   Nota: Si se ha revertido la tabla y no se ha revertido la carga de datos, el paso no estará disponible hasta que añada cualquier otro paso y, a continuación, añada Map Columns (Asignar columnas).
3. Haga clic en **Columnas del mapa** y seleccione un destino. Si no ve el conjunto de datos maestros que esperaba, vaya a **Componentes** e instale el componente necesario.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/map3.png)

## Asignar a una columna del conjunto de datos maestros

1. Revise las columnas de destino. Estas son las columnas de los conjuntos de datos maestros que se pueden asignar. Es posible que algunas ya estén asignadas porque el encabezado de una columna de la tabla coincide con un valor esperado en el destino.
2. Seleccione **Elegir fuente** en la columna Fuente o, para cambiar una asignación, seleccione uno de los otros valores de esa columna.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/master2.png)
3. Seleccione uno de los nombres de columna de la lista desplegable. Esta lista muestra todas las columnas de la tabla con un tipo de columna que coincide con el destino.

   Nota: La siguiente tabla de vista previa no se actualizará hasta que se guarde el cambio.

   Consejo: Si no ves las columnas que deseas en la lista desplegable, es posible que no sean del tipo adecuado para el destino. Vaya al paso Importar y cambie la opción Anular tipo según sea necesario. Si la columna esperada se creó en el canal de transformación, utilice o modifique el paso Fórmulas.
4. Para introducir una cadena o un número para todas las filas, seleccione **Introducir un valor fijo para todas las filas**. Como resultado, cada fila de la tabla muestra el mismo valor para esa columna. Esta opción no evalúa fórmulas. Para utilizar una fórmula, añada el paso **Fórmulas** y, a continuación, asigne la columna adicional resultante.
5. Introduzca el valor y haga clic **en Aceptar**. Ahora ha asignado dos columnas adicionales al conjunto de datos maestros seleccionando una columna de la tabla e introduciendo un valor.

**Añadir una columna personalizada al conjunto de datos maestros**

1. Para añadir una columna que no existe en el conjunto de datos maestros, haga clic en **Añadir columna personalizada**. Estas adiciones se mantendrán entre actualizaciones sin necesidad de realizar ninguna acción especial.
2. Introduzca el nombre de la columna que desea añadir y, a continuación, seleccione el tipo. Seleccione una fuente para esa columna, ya sea eligiendo otra columna de la tabla o un valor fijo.
3. Pulse **Aceptar**. Las columnas añadidas son siempre opcionales. Guarde la tabla para ver la columna en la vista previa.

**Añadir datos**

Este método es menos recomendable porque personaliza el conjunto de datos maestros, lo que aumenta el tiempo de actualización para recibir nuevos contenidos.

1. En el **Explorador de proyectos**, haga clic en la tabla de datos maestros que desee.
2. Echa un vistazo a la tabla.
3. En la canalización de transformación, haga clic en el paso **Añadir**.
4. Haga clic en **Añadir tabla** en el área de detalles.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/ad1.png)
5. Seleccione una tabla de datos de origen y haga clic en **Siguiente.**
6. Asigne las columnas de origen a las columnas del conjunto de datos maestros utilizando la siguiente **opción Añadir a...** Imagen de datos maestros.

   Nota: Un asterisco (\*) en la columna Datos maestros indica que el campo es obligatorio para completar los informes relacionados con ese conjunto de datos. Se permite el mapeo parcial. Si no dispone de todos los datos necesarios, puede asignar un subconjunto de los campos obligatorios, aunque esto podría provocar que falten datos en uno o varios informes.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/studio_images/ad6.png)
7. Haga clic en la opción para guardar.
