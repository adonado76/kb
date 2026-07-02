---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Publicar tablas para exportación"
breadcrumb: []
source_path: "studio/data_studio/published-tables.html"
images:
  - "resources/images/studio_images/method-1.png"
  - "resources/images/studio_images/method-2a.png"
  - "resources/images/studio_images/method-2b.png"
  - "resources/images/studio_images/pt-1_964x592.png"
  - "resources/images/studio_images/pt-new.png"
  - "resources/images/studio_images/pt-pe_304x333.png"
  - "resources/images/studio_images/using-1.png"
  - "resources/images/studio_images/using-2.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Publicar tablas para exportación

**Se aplica a** : TBM Studio 12.11.3 y posteriores. Las Tablas publicadas se utilizan para exportar datos de un proyecto de Cálculo de costes y planificación a otro proyecto de Cálculo de costes y planificación, o a un sistema de terceros.

Antes de esta función, los usuarios tenían que crear un informe para exportar los datos. La principal preocupación era bloquear el informe para que los usuarios finales no pudieran acceder a él. Algunas tablas de exportación eran bastante grandes, lo que a su vez añadía carga al sistema. Esto ralentizó el proceso de calcinación, por lo que se retrasó la disponibilidad de las mesas.

Ventajas de las tablas publicadas

- Elimina la gestión de informes y permisos asociados al exportar tablas.
- Permite crear tablas del mismo modo que un informe.
- Admite la exportación en cuanto finaliza el calco de desarrollo.
- Crea una forma más accesible, detectable y fácil de mantener para exportar datos modelados.
- Elimina la dependencia de la superficie de informes TBM Studio , de los clientes que no son Studio para exportar datos.

## Creación de una tabla publicada

Hay dos maneras de crear una Tabla Publicada.

## Primer método: crear una tabla publicada

1. Vaya a la pestaña **Inicio** y seleccione **Nuevo**.

   ![Crear una tabla publicada Método 1](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pt-new.png)
2. Seleccione **Tabla publicada**. Introduzca un nombre y una categoría, y seleccione **OK**.

   ![Tabla publicada](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/method-1.png)
3. La tabla recién creada aparecerá en la categoría especificada en el Explorador de proyectos.

   ![Explorador de proyectos](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pt-pe_304x333.png)
4. Configure la tabla publicada del mismo modo que una tabla de informe (consulte la sección de ayuda [Tablas en los informes](../reports/tables/about-tables.htm "(se abre en una pestaña o una ventana nueva)") ).

## Segundo método: Crear una tabla publicada a partir de una tabla de informe existente

1. Vaya a un informe existente con una tabla que desee convertir en Tabla publicada.
2. Haga clic con el botón derecho del ratón en la tabla del informe y seleccione **Crear tabla publicada**.
3. Introduzca un nombre y una categoría y seleccione **OK**.

   ![Segundo método: crear una tabla publicada](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/method-2a.png)
4. La tabla recién creada aparecerá en la categoría especificada en el Explorador de proyectos.

   ![Explorador de proyectos](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/method-2b.png)

## Opciones de configuración

**Desactivar / activar el precálculo**

1. En el Explorador de proyectos, compruebe las Tablas publicadas.
2. Seleccione la pestaña Tabla publicada y ajuste el parámetro Activo adecuadamente.

   ![Opciones de configuración](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/pt-1_964x592.png)

   - Si está marcada, el sistema precalculará la tabla. Esta es la opción por defecto, ya que garantiza que la tabla estará lista para su exportación cuando se utilice la API URL.
   - Si no está marcada, el sistema no precalculará la tabla. La API URL seguirá funcionando, pero el sistema tendrá que calcular la tabla la primera vez que reciba una solicitud de la misma.

## Utilización de una tabla publicada

1. Haga clic con el botón derecho en la **tabla publicada** para ver la API URL.

   ![Utilización de una tabla publicada](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/using-1.png)
2. Copie la dirección URL y utilícela en DataLinko en automatizaciones con script.

   ![automatización programada](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/using-2.png)
