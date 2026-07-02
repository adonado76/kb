---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "CT Apps - Componente de aplicaciones"
breadcrumb: []
source_path: "cost-transparency/configuration/apps.html"
images:
  - "resources/images/ct_images/6859_1.png"
  - "resources/images/ct_images/6859_2.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# CT Apps - Componente de aplicaciones

El componente Aplicaciones es un prerrequisito fundamental que utiliza el componente Información sobre aplicaciones. El componente Aplicaciones proporciona nuevos informes y también crea métricas que se exponen en el componente Application Insights.

Se aplica a: Costing Standard en TBM Studio 12.0 y posteriores

Icono de componente:

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6859_1.png)

## Cuadros de apoyo

Al instalar el componente CT Apps - Aplicaciones, se crea un nuevo grupo Aplicaciones con tres tablas: Aplicaciones (tabla modelo), Datos maestros de aplicaciones, Lista de referencia de aplicaciones.

La tabla Lista de referencia de aplicaciones incluye una lista de familias de aplicaciones (por ejemplo, g.: Business Apps, Collaboration, Database, etc.) y las distintas funciones de aplicación asociadas a cada familia de aplicaciones. No debe modificar esta tabla.

## Datos maestros

Para obtener una descripción de los campos de la tabla de datos maestros, consulte la información de la página CT Apps - Componente Aplicaciones del producto. Para visualizar la página:

1. Haga clic en la pestaña **Proyecto** de la cinta de opciones.
2. Haga clic en **Componentes**.
3. Haga clic en el componente **CT Apps - Aplicaciones**.

## Cargar los datos

Cargue los datos de su solicitud. A continuación se enumeran los campos obligatorios y recomendados. Todos los campos pueden asignarse a la tabla Datos maestros de aplicaciones.

- Unidades reales (obligatorias)
- Propietario de negocio de aplicaciones (recomendado)
- Recuento de aplicaciones (recomendado)
- Familia de la solicitud (obligatorio)
- Aplicación Función (recomendada)
- ID de la solicitud (obligatorio)
- Fecha de entrada en servicio de la solicitud (recomendada)
- Solicitud Objetivo de inversión (obligatorio)
- Propietario de TI de aplicaciones (recomendado)
- Ciclo de vida de la aplicación (recomendado)
- Nombre de la aplicación (obligatorio)
- Fecha de jubilación de la solicitud (recomendada)
- Tipo de aplicación (recomendada)
- Categoría de usuario de la aplicación (recomendada)
- Criticidad empresarial (recomendado)

## Mapear los datos

Tras cargar los datos de la aplicación, asigne la tabla a la tabla Datos maestros de aplicaciones.

Después de asignar los datos, debería haber valor asignado de Torres de Recursos TI, Servidores, Tickets y Proyectos a Aplicaciones en el modelo de Costes.

## Asignar almacenamiento a las aplicaciones

Recuerde que los LUN de Almacenamiento se asignaron a Aplicaciones cuando configuró Almacenamiento. Para asignar almacenamiento a las aplicaciones, siga los pasos que se indican a continuación.

1. Haga clic en Almacenamiento dentro del grupo Almacenamiento.
2. Consulte el documento "Almacenamiento".
3. Haga clic en **Añadir Asignación** y defina la Asignación utilizando la siguiente configuración:

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6859_2.png)

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
