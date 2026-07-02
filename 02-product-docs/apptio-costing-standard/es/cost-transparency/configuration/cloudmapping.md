---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Mapeo de nubes"
breadcrumb: []
source_path: "cost-transparency/configuration/cloudmapping.html"
images:
  - "resources/images/ct_images/10077_1.png"
  - "resources/images/ct_images/10077_2.png"
  - "resources/images/ct_images/10077_3.png"
  - "resources/images/ct_images/10077_4.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Mapeo de nubes

La función de asignación de nubes (a veces conocida como *asignación de etiquetas* ) ofrece la posibilidad de asignar metadatos de nubes (como etiquetas y cuentas) a atributos en Apptio, como Unidad de Negocio, Aplicación, etc. El mapeo de los datos de la nube le permitirá ver no sólo qué servicios en la nube se consumen, sino también etiquetar los datos de facturación de la nube con información que le ayude a comprender su gasto y propiedad de la nube.

## Antes de empezar

Como requisito previo, debe decidir si desea utilizar reglas de asignación directa, que le permiten rellenar la columna de destino a partir de una lista predefinida de columnas, o las reglas de correspondencia de tablas, que requieren que cree su propia tabla de reglas y defina la columna que rellena la columna de destino. Si tiene previsto utilizar reglas de coincidencia de tablas, deberá crear una tabla de reglas (por ejemplo, TMRules\_2 ) antes de realizar los siguientes pasos.

Para crear una tabla de reglas, realice una de las siguientes acciones:

- Cree una tabla de reglas en un formato compatible con TBM Studio y, a continuación, cárguela en TBM Studio.
- Cree una tabla de reglas en TBM Studio y guárdela.

Ejemplo:

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/10077_1.png)

## Acerca de esta tarea

- Las asignaciones se aplican tanto al archivo mensual (utilizado en el informe mensual de TCO) como al archivo diario/hora (utilizado en el informe diario de transparencia).
- Los cambios en los informes mensuales aparecen inmediatamente después de que se guarden en el entorno de desarrollo y se registren en el entorno de preparación.
- Los cambios en los informes diarios aparecen en cuanto se ingiere la siguiente factura a través del preprocesador tras hacer clic en Promoción a producción en TBM Studio.

**NOTA** La función de asignación de nubes sólo está habilitada para Cloud Cost Management (CCM) y Cloud Business Management (CBM). No está disponible para ninguna otra tabla en Studio. Las tablas con mapeo en la nube no pueden utilizar un paso de fórmula en su canal de transformación. Si necesita añadir una lógica de fórmulas al proceso de transformación, consulte [Añadir un paso de fórmula a las tablas de la nube 12.6](addformulastep.html "Actualmente, Apptio no admite la adición de pasos de fórmula a las tablas de nubes AWS y Azure. No obstante, si surge la necesidad (por ejemplo, si tiene que modificar Costes), utilice la siguiente solución.").

**NOTA** El conector DataLink AWS puede procesar facturas de Informe de Costes y Usos (CUR)

Tipos de reglas de asignación

Existen dos tipos de reglas de asignación:

Normas de asignación directa
:   - Cada regla consta de 4 columnas: 1 columna de destino | columna 1 | columna 2 | columna 3
    - La regla intentará primero rellenar la columna de destino con el valor de la columna 1. Si esa columna está vacía, se utiliza el valor de la columna 2. Si esa columna está vacía, se utiliza el valor de la columna 3. Si todas las columnas están vacías, la columna de destino estará vacía.
    - La lista de valores de las columnas 1, 2 y 3 se extrae de la cabecera de la tabla AWS.

Reglas de concordancia de la tabla
:   - Cada regla consta de 2 columnas 1 columna de destino | 1 tabla de entrada de reglas
    - La tabla de reglas debe tener una columna que coincida con la columna de destino seleccionada. Por ejemplo, si la columna de destino es Proyecto, la tabla de reglas debe contener una columna denominada Proyecto.
    - La tabla de reglas sólo puede tener columnas de entrada que formen parte de la factura original. En otras palabras, las columnas ya emitidas y procesadas no pueden utilizarse como columnas de entrada.

Para asignar su facturación en la nube, haga lo siguiente en el entorno de desarrollo en TBM Studio:

## Procedimiento

1. En el Explorador de proyectos, abra una de las siguientes tablas de nubes:
   1. AWS Informe de costes y utilización en bruto
   2. Azure EA Bill Raw
2. En la pestaña **Inicio**, haga clic en **Salida**.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/10077_2.png)
3. Haga clic en el signo más de **Añadir paso**.
4. Haga clic en **Mapeo de nubes**.

   **NOTA** El paso Asignación de nubes aparece (sustituyendo al paso Fórmulas) sólo después de seleccionar una tabla de nubes.
5. Haga clic en **Añadir una nueva asignación**.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/10077_3.png)
6. En la lista **Columna de destino**, seleccione una o varias columnas para utilizarlas como origen.
7. En la lista **Regla de asignación**, seleccione **Asignación directa** o **Coincidencia de tabla**. Para obtener una descripción de estas normas, consulte la sección [Requisitos previos](cloudmapping.html#base_file_name__prereq).

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/10077_4.png)
8. En las listas de **entrada de reglas**, realice una de las siguientes acciones:
   1. Para la asignación directa, en una o más de las listas desplegables, seleccione el nombre de la columna que desea utilizar para rellenar la columna de destino.

      - La regla intentará primero rellenar la columna de destino con el valor de la lista de la primera columna (por ejemplo, Aplicación en la imagen). Si esa columna está vacía, se utiliza el valor de la lista de la segunda columna (por ejemplo, Unidad de Negocio). Si esa columna está vacía, se utiliza el valor de la lista de la tercera columna (por ejemplo, Centro de coste). Si todas las columnas están vacías, la columna de destino estará vacía.
      - La lista de valores de las columnas 1, 2 y 3 se extrae de la cabecera de la tabla AWS.
   2. Para la correspondencia de tablas, seleccione el nombre de la tabla de reglas que creó anteriormente (por ejemplo, TMRules\_2 ).

      La tabla de reglas debe tener una columna que coincida con la columna de destino seleccionada. Por ejemplo, si la columna de destino es "Proyecto", la tabla de reglas debe contener una columna denominada "Proyecto"
9. Comprueba tus cambios.

   La nueva columna aparece ahora en el informe CCM Monthly TCO y en el informe Daily Transparency (Daily/Hourly > Reports > Iaas Paas > Daily Transparency), pero los datos del informe Daily Transparency no serán exactos hasta después de la siguiente ingesta programada de datos de facturación en nube (no más de 24 horas).

   A continuación, debe pasar a producción para permitir que los cambios se utilicen en el informe de transparencia diario/horario.
10. Cambie al entorno **Staging**.
11. Haga clic en la pestaña **Proyecto**.
12. Haz clic en **Bloquear**.
13. Haga clic en **Opciones de promoción**.
14. Haga clic en **Promover ahora**.
15. Una vez finalizado el proceso, haga clic en **Desbloquear para** que la siguiente actualización diaria se realice correctamente.

    Los datos de mapeo aparecerán en el informe de Transparencia Diaria/Horaria después de que se ingiera la siguiente factura en nube programada (no más tarde de 24 horas).

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
