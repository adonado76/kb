---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Recomendaciones para la agrupación numérica"
breadcrumb:
  - "TBM Studio"
  - "Solución de problemas y asistencia técnica"
  - "Explicación de los mensajes de error"
source_path: "studio/troubleshooting/numeric-grouping-tables-reports.html"
images:
  - "resources/images/studio_images/adhoc-component.png"
  - "resources/images/studio_images/data-group.png"
  - "resources/images/studio_images/identified-problem.png"
  - "resources/images/studio_images/numeric-grouping-table.png"
  - "resources/images/studio_images/numeric-video-ss.png"
  - "resources/images/studio_images/removing-numeric.png"
  - "resources/images/studio_images/report-grouping.png"
  - "resources/images/studio_images/table-transform.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Recomendaciones para la agrupación numérica

La reestructuración de la caché en Q2 2026 eliminará la posibilidad de agrupar por dimensión numérica, independientemente de los criterios de cálculo. Debe abordar las recomendaciones antes del próximo lanzamiento para evitar cambios inesperados en el comportamiento de los datos.

El motor de recomendaciones identificó configuraciones en su entorno que actualmente utilizan dimensiones numéricas para la agrupación. Tome medidas para garantizar una transición fluida en todas las fases y evitar interrupciones en sus procesos de generación de informes y flujos de datos.

PRECAUCIÓN:

Si no se tienen en cuenta estas recomendaciones antes de una liberación de 12.11.20, las dimensiones numéricas se filtrarán automáticamente de las operaciones de agrupación.

## Cómo resolver

Utilice las siguientes opciones para determinar la ruta de resolución adecuada.

**Opción 1** : (Recomendada): Esta opción se utiliza cuando la agrupación incluye campos calculados, como importes, porcentajes u otros valores calculados. Si una columna contiene un valor porcentual o decimal, debe eliminarla de la agrupación.

Nota: Resolver la recomendación antes del registro permite verificar que el cambio de configuración cumple con la alerta de agrupación numérica. Si el cambio de configuración no solucionó el problema de agrupación numérica, la alerta volverá a aparecer tras el cálculo.

**Opción 2**

**Recomendación sobre agrupación numérica en tablas**

1. Seleccione **Recomendaciones** y, a continuación, seleccione **Agrupación numérica de tablas: Dimensión numérica detectada en el paso de agrupación** para ver la tabla afectada

   ![tabla de agrupación numérica](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/numeric-grouping-table.png)
2. En la sección **Problemas identificados**, seleccione la tabla afectada y revise qué campo está afectado en la tabla en **NumericGroupings** el campo.

   ![problema identificado](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/identified-problem.png)
3. En la tabla seleccionada, vaya a la pestaña **Importar** y cambie la dimensión numérica a **Etiqueta** para el campo afectado.
4. Seleccione **Guardar** y **registrar.**
5. Verifique que la recomendación se haya resuelto en la lista de recomendaciones. Si la alerta vuelve a aparecer, siga los pasos adicionales descritos en **la Opción 3**.

**Informe sobre la recomendación relativa a la agrupación numérica**

1. Seleccione **Recomendaciones** y, a continuación, seleccione **Agrupación numérica del informe: Dimensión numérica utilizada en la agrupación del informe** para ver el informe afectado.

   ![agrupación de informes](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/report-grouping.png)
2. En la sección **Problemas identificados**, seleccione el informe afectado y revise qué campo se ve afectado en el informe en **NumericGroupings** el campo.
3. Vaya a la pestaña **Datos** y seleccione **Grupo**.

   ![Pestaña Datos y Grupo](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/data-group.png)
4. Si se incluye la dimensión numérica, seleccione *(ninguna)* en el campo **Y por** y haga clic en el botón **Agrupar** para guardar los cambios.

   ![Eliminar numérico](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/removing-numeric.png)
5. Si la dimensión no se incluyó en la configuración del botón de la barra de cinta **del grupo**, es posible que se agrupe automáticamente en función de su posición en la configuración del componente.
   1. Esto suele significar que la dimensión se incluye en las filas de la configuración del componente, que se agruparán de forma predeterminada.
   2. En este escenario, localice la dimensión en el acordeón **Configuración de componentes ad hoc**, haga clic con el botón derecho del ratón en la dimensión para abrir el menú contextual, seleccione **Desagrupar** y, a continuación, seleccione **Guardar**.

      ![Configuración de componentes ad hoc](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/adhoc-component.png)
6. Resuelva las recomendaciones y seleccione **Guardar** y **registrar**.
7. Verifique que la recomendación se haya resuelto en la lista de recomendaciones. Si la alerta vuelve a aparecer, siga los pasos adicionales descritos en **la Opción 3**.

**Opción 3** Si la dimensión numérica debe seguir siendo numérica para fines computacionales, siga los pasos a continuación para crear un equivalente basado en etiquetas para la agrupación.

**Tabla de tuberías**

1. Seleccione **Recomendaciones** y vaya a la tabla afectada.
2. Seleccione el icono **+** en la pestaña **Grupo** y, a continuación, seleccione **Fórmula** > **Añadir una nueva columna**.
3. Cree una nueva columna con un nombre descriptivo (por ejemplo, si agrupa por department\_id, cree department\_id\_grouping\_label)
4. Establezca el **tipo** de columna en **Etiqueta.**

   ![transformación de tabla](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/table-transform.png)
5. Establezca la **fórmula** para convertir el número en texto utilizando la fórmula « NumberFormat » (Convertir texto en número):

   ```
   =NumberFormat(numeric_dimension_name, "#")
   ```

   Ejemplo: Si la dimensión numérica se llama DRIVE\_CAPACITY, la fórmula más sencilla sería:

   ```
    =NumberFormat(DRIVE_CAPACITY, "#")
   ```
6. Vaya a la pestaña **Grupo** y sustituya la dimensión numérica por su nueva columna de etiquetas.
7. Seleccione **Guardar** y **registrarse**.
8. Después del cálculo, confirma que la recomendación se ha resuelto y no ha vuelto a aparecer.

**Para los componentes del informe:**

1. Seleccione **Recomendaciones** y vaya al informe afectado.
2. Consulte el informe y seleccione el componente problemático para abrir el panel de configuración del componente del informe ad hoc.
3. Vaya a la pestaña **Datos**, seleccione la flecha desplegable **Insertar** y seleccione **Insertar una nueva columna de fórmula**.
   - Si el botón **Insertar** está desactivado, elimine o mueva cualquier columna que se encuentre actualmente en la sección Columnas del panel de configuración del componente de informe ad hoc. Puedes volver a añadirlos.
4. Añade un nombre de columna, inserta la columna de fórmula proporcionada anteriormente y selecciona la **etiqueta** de tipo.
5. Reemplace la dimensión numérica antigua por la nueva etiqueta equivalente en el panel de configuración del componente del informe ad hoc y, a continuación, sustituya la columna numérica por la nueva etiqueta equivalente actualizándola en el botón de la barra de cinta Grupo del componente del informe ad hoc, situado en la pestaña **Datos**
6. Seleccione **Guardar** y **registrar.**
7. Después del cálculo, confirma que la recomendación se ha resuelto y no ha vuelto a aparecer

[![Agrupación numérica Vídeo](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/numeric-video-ss.png)](https://community.ibm.com/community/user/viewdocument/test-76?CommunityKey=44bcb0d2-5ce6-4504-89eb-019253d3b5d8 "(se abre en una pestaña o una ventana nueva)")

## Validación de la corrección

- Después de guardar los cambios y registrarlos, si la recomendación vuelve a aparecer, significa que el cambio de configuración no ha cumplido el requisito de agrupación numérica. En este caso:
- - Verifique que haya guardado todos los cambios de configuración
  - Asegúrese de haber eliminado TODAS las dimensiones numéricas de la operación de agrupación
  - Comprueba que la nueva columna de etiquetas esté correctamente configurada (si utilizas la solución alternativa)
