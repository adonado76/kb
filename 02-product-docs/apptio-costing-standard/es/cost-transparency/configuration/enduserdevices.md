---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Componente CT Apps - Dispositivos de usuario final"
breadcrumb: []
source_path: "cost-transparency/configuration/enduserdevices.html"
images:
  - "resources/images/ct_images/6859_1.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Componente CT Apps - Dispositivos de usuario final

El componente CT - Apps End User Devices forma parte del módulo Costing Standard Applications and Services. Se utiliza para comprender el coste total de propiedad de los dispositivos de usuario final, incluidos PC, portátiles, teléfonos inteligentes, tabletas y otros equipos informáticos de cliente, y para asignar los costes utilizados por la plantilla de la empresa.

Icono de componente:

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6859_1.png)

El componente Dispositivos de usuario final instala nuevas tablas de datos y estrategias de asignación recomendadas para determinar el TCO de los dispositivos de usuario final y para prorratear los costes de los dispositivos de usuario final entre los siguientes servicios típicos:

- Servicios de usuario final: para dispositivos de usuario final utilizados como ofertas de servicios de Client Compute por los trabajadores
- Servicios empresariales específicos: para necesidades empresariales específicas, como recursos informáticos distribuidos (por ejemplo, quioscos) para una oferta minorista (por ejemplo, cajeros automáticos)

## Cuadros de apoyo

Al instalar el componente CT Apps - Dispositivos de usuario final, se crea un nuevo grupo Dispositivos de usuario final con dos tablas: Dispositivos de usuario final (tabla modelo), Datos maestros de dispositivos de usuario final.

## Datos maestros

Para obtener una descripción de los campos de la tabla de datos maestros, consulte la información de la página del componente CT Apps - Dispositivos de usuario final del producto. Para visualizar la página:

1. Haga clic en la pestaña **Proyecto** de la cinta de opciones.
2. Haga clic en **Componentes**.
3. Haga clic en el componente **CT Apps - Dispositivos de usuario final**.

## Cargar los datos

Cargue los datos de sus dispositivos de usuario final. A continuación se enumeran los campos obligatorios y recomendados. Todos los campos pueden asignarse a la tabla Datos maestros de dispositivos de usuario final.

- Número de identificación del activo (recomendado)
- Recuento de dispositivos (obligatorio)
- Tipo de dispositivo (obligatorio)

## Mapear los datos

Una vez cargados los datos de comunicación, asigne la tabla a la tabla de datos maestros de dispositivos de usuario final.

Después de mapear los datos, debería haber un valor asignado de Torres de Recursos de TI y Comunicaciones a Dispositivos de Usuario Final, y de Dispositivos de Usuario Final a Servicios de Negocio en el modelo de Costes.
