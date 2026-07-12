---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Crear una tabla a partir de una tabla editable"
breadcrumb: []
source_path: "studio/data_studio/create-table-from-et.html"
images:
  - "resources/images/studio_images/aftr-chkin.jpg"
  - "resources/images/studio_images/df-disable.jpg"
  - "resources/images/studio_images/df-enable.jpg"
  - "resources/images/studio_images/et-table.jpg"
  - "resources/images/studio_images/et-tbl1.jpg"
  - "resources/images/studio_images/et-tbl2.jpg"
  - "resources/images/studio_images/et-upload.png"
  - "resources/images/studio_images/ps-ddf.jpg"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Crear una tabla a partir de una tabla editable

Puede crear una tabla a partir de una Tabla Editable existente siguiendo los siguientes pasos:

Desde TBM Studio, vaya a la pestaña **Inicio** >� **Nuevo** desplegable > seleccione **Tabla**.

En la ventana emergente Crear tabla, introduzca un nombre para la tabla y seleccione Aceptar.

Seleccione el mosaico **Tabla editable**.

![Tabla editable](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/et-table.jpg)

Seleccione un valor en el desplegable Tabla editable.

![Tabla desplegable editable](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/et-tbl2.jpg)

Elija el método de carga y seleccione el calendario de publicación periódica

![calendario de publicación periódica](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/et-tbl1.jpg)

Guarda y registra la mesa.

## Desactivar el flujo de datos en Enriched Transform

Si configura una tabla editable enriquecida y luego cambia la información en la tabla de transformación de origen en la etapa de desarrollo, los datos no fluirán automáticamente a la tabla editable enriquecida. Sólo una vez publicada la tabla, los datos fluirán de la tabla de origen a la tabla editable enriquecida.

Para activar esta función, vaya a TBM Studio > Configuración del proyecto y seleccione la opción **Desactivar flujo de datos en transformación enriquecida**.

![Desactivar flujo de datos](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ps-ddf.jpg)

Si la función está desactivada, el flujo de datos será el que se muestra a continuación.

![Carga de tablas](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/df-disable.jpg)

Si la función está activada, el flujo de datos será el que se muestra a continuación.

![Función activada](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/df-enable.jpg)

Tras comprobar los cambios, los datos aparecerán como se muestra.

![Datos](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/aftr-chkin.jpg)

Para el flujo actual de tablas editables enriquecidas, considere 3 tablas implicadas:

- Table\_1 - tabla de transformación de la fuente
- EET\_Table\_2 - tabla editable enriquecida basada en Table\_1
- Trf\_Table\_3 - tabla de transformación creada en ET\_Table\_2.

Los valores que figuran en Trf\_Table\_3 proceden de 2 tablas:

- Table\_1 tiene las filas de origen originales, y
- EET\_Table\_2 tiene los registros superpuestos que modifican las celdas de las filas fuente originales de Table\_1, y pueden incluir nuevas filas añadidas. (No puede eliminar ninguna fila existente en Table\_1 ).

Cuando cargue un nuevo conjunto de datos en Table\_1, los cambios se verán inmediatamente en EET\_Table\_2 y Trf\_Table\_3 aunque NO haya publicado los cambios de EET\_Table\_2 a Trf\_Table\_3. EET\_Table\_2 sólo tiene los registros superpuestos a las filas de origen de Table\_1.

Esta nueva función le da la opción de controlar qué comportamiento prefiere y se controla mediante un nuevo ajuste del proyecto: "Desactivar flujo de datos en transformaciones enriquecidas"

- Desactivado (por defecto) - la tabla de transformación recibirá las actualizaciones de la tabla de origen ( Table\_1 ) inmediatamente (comportamiento actual)
- Activado: la tabla de transformación sólo verá las actualizaciones de la tabla de origen ( Table\_1 ) cuando la carga de la tabla esté "registrada"

Nota: Las Tablas editables son ahora específicas de cada rama, lo que permite trabajar en cada rama sin afectar al tronco principal. Es decir, la creación de una rama tendrá su propia copia de Tablas editables y la modificación en el tronco no será visible en la rama.

## Carga y publicación de datos en una tabla Transform

La función Transformar tabla permite a los administradores cargar y publicar datos de una tabla editable en el canal de datos.

**Corrección de errores en los cambios de tablas editables**

Puede corregir errores en modificaciones de tablas editables que se publicaron en un período anterior. Supongamos que publicó cambios en una tabla editable en enero, pero más tarde descubrió que había errores en los datos. Puede descargar los datos de la Tabla de Transformación de enero, hacer las correcciones necesarias y, a continuación, cargar los datos corregidos directamente en la Tabla de Transformación. Así se corregirán los errores del modelo de costes y se garantizará que los datos sean exactos y estén actualizados.

Nota: Esta función sólo es aplicable a la ET en blanco y no a la ET enriquecida

1. Vaya al paso de canalización de datos y seleccione la tabla de transformación cuyos datos desea cargar.
2. **Descargue** los datos de la tabla correspondientes a un periodo determinado.
3. Realice los cambios necesarios en el archivo descargado. Los datos deben tener el mismo formato: sólo se pueden modificar, no se pueden borrar ni añadir filas/columnas.
4. **Cargue** los datos corregidos directamente en la tabla de transformación para el periodo específico. Esto sobrescribirá los datos originales y corregirá los errores del modelo de costes.

![Corrección de errores en los cambios de tablas editables](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/et-upload.png)

**Tema principal:** [Editar la configuración del proyecto](../../studio/admin/edit-project-settings.html "Se aplica a: TBM Studio 12.0 y posteriores. Algunos ajustes están disponibles en versiones posteriores de TBM Studio, como se indica a continuación.")

**Tema principal:** [Cargar datos](../../studio/data_studio/upload-data.html "Se aplica a: TBM Studio 12.0 y posteriores")
