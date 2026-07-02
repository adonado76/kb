---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "CT Apps - Componente de comunicaciones"
breadcrumb: []
source_path: "cost-transparency/configuration/comms.html"
images:
  - "resources/images/ct_images/6878_1.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# CT Apps - Componente de comunicaciones

El componente CT Apps - Comunicaciones forma parte del módulo Costing Standard Aplicaciones y Servicios. Se utiliza para asignar los costes de la infraestructura de comunicación, incluidos los circuitos y el uso, a los consumidores del recurso de comunicación.

Se aplica a: Costing Standard en TBM Studio 12.0 y posteriores

Icono de componente

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6878_1.png)

## Cuadros de apoyo

Al instalar el componente CT Apps - Comunicaciones, se crea un nuevo grupo Comunicaciones con dos tablas: Comunicación (tabla modelo), Datos maestros de comunicaciones.

## Datos maestros

Para obtener una descripción de los campos de la tabla de datos maestros, consulte la información de la página CT Apps - Componente de comunicaciones del producto. Para visualizar la página:

1. Haga clic en la pestaña **Proyecto** de la cinta de opciones.
2. Haga clic en **Componentes**.
3. Haga clic en el componente **CT Apps - Comunicaciones**.

## Cargar los datos

Cargue los datos de sus comunicaciones. A continuación se enumeran los campos obligatorios y recomendados. Todos los campos pueden asignarse a la tabla de datos maestros de comunicaciones.

- Cuenta (recomendado)
- Importe (obligatorio)
- ID de circuito (recomendado)
- Ubicación (recomendada)
- Tipo de ubicación (obligatorio)
- Identificador de objeto (obligatorio)
- Oferta (recomendada)
- Producto (recomendado)
- Proveedor de servicios (recomendado)
- Tipo (obligatorio)

## Mapear los datos

Después de cargar los datos de comunicaciones, asigne la tabla a la tabla de Datos Maestros de Comunicaciones.

Después de mapear los datos, debería haber un valor asignado de Torres de Recursos TI a Comunicaciones, y de Comunicaciones a Servidores y Servicios de Negocio en el modelo de Costes.

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
