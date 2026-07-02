---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Todas las filas Recomendación"
breadcrumb: []
source_path: "studio/troubleshooting/studio-troubleshooting-all-rows-recommendation.html"
images:
  - "resources/images/studio_images/all-rows-recommdentation-1.png"
  - "resources/images/studio_images/all-rows-recommdentation-2.png"
  - "resources/images/studio_images/all-rows-recommdentation-3.png"
  - "resources/images/studio_images/all-rows-recommdentation-4.png"
  - "resources/images/studio_images/all-rows-recommdentation-5.png"
  - "resources/images/studio_images/all-rows-recommdentation.png"
  - "resources/images/studio_images/arr-1.jpg"
  - "resources/images/studio_images/arr-2.jpg"
  - "resources/images/studio_images/arr-3.jpg"
  - "resources/images/studio_images/arr-4.jpg"
  - "resources/images/studio_images/arr-5.jpg"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Todas las filas Recomendación

Esta función simplifica el proceso proporcionando una guía paso a paso basada en recomendaciones de expertos, lo que garantiza tiempos de cálculo más rápidos y un mayor rendimiento. Puede acceder a los documentos y automatizar los cambios de configuración para agilizar su flujo de trabajo. El sistema comprobará automáticamente los cambios y marcará las incidencias como resueltas.

Vaya a **TBM Studio** > pestaña **Recomendaciones** y, a continuación, seleccione **Solucionar todos los problemas identificados**.

![Solucionar todos los problemas identificados](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/arr-1.jpg)

Cambie al espacio de trabajo **Desarrollo** y seleccione **Siguiente**.

![Asistente de recomendaciones](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/arr-2.jpg)

Haga clic en el icono **Siguiente**.

![Siguiente](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/arr-3.jpg)

¡Seleccione **Set Automatic!ALL\_ROWS\_Assignment** botón.

![TODAS LAS FILAS](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/arr-4.jpg)

Seleccione **Siguiente** y, a continuación, **Checkin** en la última página.

![Facturación](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/arr-5.jpg)

Active la opción "¡Manejar automáticamente!Opción "ALL\_ROWS" en la [configuración del proyecto](../admin/edit-project-settings.html "Se aplica a: TBM Studio 12.0 y posteriores. Algunos ajustes están disponibles en versiones posteriores de TBM Studio, como se indica a continuación."). Con esta opción activada, el TBMA ya no necesita crear perspectivas para gestionar ALL\_ROWS. Añade y quita permisos cuando es necesario y, por lo tanto, elimina la necesidad de marcar la casilla de todas las filas en las perspectivas.

## Método antiguo: Recuperación de todas las filas en una consulta basada en el tiempo

![Recuperación de todas las filas en una consulta basada en el tiempo](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/all-rows-recommdentation.png)

Esta opción puede configurarse al publicar una columna en una perspectiva. ¡Añadirá un ALL\_ROWS! A una ruta de datos, lo que garantizará, cuando se utilice un agregado temporal como =YearToDate( ) o Annual(), que todas las filas de la tabla se incluyan en el cálculo. En datos que varían con el tiempo, deberá utilizar ALL\_ROWS para asegurarse de que se calcula la información correcta. No siempre se incluye por motivos de rendimiento.

Suponiendo que tengas datos estructurados así.

![recomendación de fila](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/all-rows-recommdentation-1.png)

La cantidad =Anual() para A y B es 12, y C es 1. Sin embargo, si ejecuta esta función en los meses de febrero a diciembre, sólo tendrá los identificadores A y B en la tabla (véase el ejemplo siguiente).

![Fila Recomendaciones 2](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/all-rows-recommdentation-2.png)

Dado que el identificador C no está presente en los datos de febrero a diciembre, esas filas no están presentes en la tabla del mes actual, lo que hace que el Cálculo anual muestre un total general incorrecto. Para solucionar este problema, cree una perspectiva de la columna y marque la casilla "Mostrar todas las filas en la consulta basada en el tiempo"

![publicar campo](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/all-rows-recommdentation-3.png)

Al colocar esta nueva perspectiva en la configuración, se muestra la fila C y se tiene en cuenta para el total.

![recomendaciones de filas](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/all-rows-recommdentation-4.png)

Cuando se utiliza "Tiempo" en Columnas, ALL\_ROWS no es necesario, esto se debe a que los buckets de tiempo construyen una estructura de datos diferente llamada TREND\_APPEND, que toma los datos de cada mes y los añade juntos. Una no es necesariamente mejor que la otra, sino que depende de la visión específica que se quiera obtener. A continuación puede ver las 2 tablas, que muestran los mismos datos, pero tienen diferentes rutas de datos, y ligeramente diferente nomenclatura / formato.

![recomendaciones de filas](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/all-rows-recommdentation-5.png)

## Conclusión

- ALL\_ROWS no es necesario y no se añadirá a las rutas de datos que utilicen los buckets de tiempo (TREND\_APPEND)
- ALL\_ROWS no es necesario si no se utilizan agregados temporales.
- ALL\_ROWS es necesario si los datos subyacentes varían con el tiempo y se utilizan agregados temporales.
