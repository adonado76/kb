---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Taller para vendedores"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/vendorsworkshop.html"
images:
  - "resources/images/ct_images/vendors-workshop.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Taller para vendedores

## Preparación de los datos del proveedor

Puede empezar a preparar los datos de su proveedor consultando los siguientes puntos de control:

1. Si aún no lo ha hecho, cargue todos los datos relevantes del proveedor en Apptio.
2. Siguiendo las prácticas habituales de Apptio las prácticas habituales, clasifique cada conjunto de datos brutos en la categoría de Proveedores.
3. Si procede, aplique un filtro de fechas a sus datos de proveedor.

## Acerca del identificador de proveedor

El identificador del objeto Proveedor es generado por el sistema y no debe ser alterado. Incluye:

- Nombre de distribuidor
- ID de proveedor
- Tipo de proveedor
- Función de proveedor
- Proveedor Servicio principal

## Acerca de las claves de vendedor

Las claves del conjunto de datos maestros de proveedores son todas generadas por el sistema y no deben alterarse.

| Clave | La clave de campo se basa en | Lógica |
| --- | --- | --- |
| **Coste Fuente\_Vendedor Clave** | ID de proveedor  Fuente de costes Metacampo clave | Añada el texto CS\_Vendor con el ID de proveedor, Metacampo Clave de fuente de coste |
| **Clave Vendor\_ITRT** | Clave CSP del proveedor  Torre de recursos informáticos  Subtorre de recursos informáticos | IF  Vendor\_CSP Clave = Vendor\_CSP\_null  THEN  Añadir el texto Vendor\_ITRT con IT Resource Tower y IT Resource Sub-Tower  ELSE  Establecer el texto en Vendor\_ITRT\_null |
| **Clave Vendor\_CSP** | ¿Es CSP  Nombre de distribuidor | IF  Es CSP = sí  THEN  Añada el texto Vendor\_CSP con el nombre del proveedor  ELSE  Establecer el texto en Vendor\_CSP\_null |

Vendor\_CSP\_Key sólo es necesario si también está implementando el componente Public Cloud . De lo contrario, la clave (y otros campos relacionados con Cloud) pueden dejarse en blanco.

## Columnas computadas comunes necesarias para los proveedores

Puede que necesite crear alguna de las siguientes columnas computadas:

- Declaración condicional para determinar si un vendedor es un proveedor de servicios en nube. La respuesta debería ser Sí/No.
- Declaración condicional para determinar si un vendedor es un proveedor de servicios gestionados. La respuesta debería ser Sí/No.
- El tipo de proveedor debe clasificarse como "Estratégico", "Preferido" o "Transaccional"

Si los datos de asignación de proveedores se encuentran en un conjunto de datos independiente de los datos de proveedores, es posible que necesite columnas calculadas adicionales, entre las que se incluyen:

- Búsqueda de gastos objetivo anuales de una lista de proveedores a una lista de asignación de proveedores
- Búsqueda de ubicación de servicio de una lista de proveedores a una lista de asignación de proveedores
- Búsqueda de la interacción del usuario de una lista de proveedores a una lista de asignación de proveedores
- Búsqueda de la función de proveedor de una lista de proveedores a una lista de asignación de proveedores
- Búsqueda de la ubicación del proveedor de una lista de proveedores a una lista de asignación de proveedores
- Búsqueda del gestor de proveedores de una lista de proveedores a una lista de asignación de proveedores
- Búsqueda de un servicio de proveedor de una lista de proveedores a una lista de asignación de proveedores
- Búsqueda del tipo de proveedor de una lista de proveedores a una lista de asignación de proveedores

El nombre del proveedor DEBE coincidir con el nombre del proveedor en el conjunto de datos maestros del proveedor de servicios en nube para que exista una relación. Si no es así, es posible que tenga que limpiar los datos o crear una columna calculada.

## Asignar datos a los datos maestros de proveedores

Asigne los datos de proveedor del cliente al conjunto de datos maestros de proveedores. La mayor parte de la cartografía se explica por sí misma. En 12.7 ahora puede aprovechar la función Mapa de columnas en su conjunto de datos sin procesar para asignar a los datos maestros de proveedores ( [Asignar columnas](https://community.apptio.com/docs/DOC-10561 "(se abre en una pestaña o una ventana nueva)") ).

Para utilizar el porcentaje de asignación (para proveedores asignados a más de una torre), utilice la opción Seleccionar columnas de origen adicionales al asignar los datos. Se utilizará para la asignación de proveedores a torres de recursos de TI en los modelos.

## Revisar el objeto Vendedores en los modelos

Una vez que haya asignado sus datos a los datos maestros de proveedores, puede seguir adelante y revisar los objetos en los modelos. Revise los siguientes modelos y asegúrese de que los valores fluyen hacia los objetos de forma adecuada.

| Modelo | Acciones |
| --- | --- |
| **Coste** | Asegúrese de que los valores pasan del objeto Fuente de costes al objeto Proveedores.  Las claves que unen los dos conjuntos de datos incluyen el ID de proveedor y el metacampo Clave de fuente de coste. |
| **Presupuesto** | Asegúrese de que los valores pasan del objeto Fuente de costes al objeto Proveedores.  Las claves que unen los dos conjuntos de datos incluyen el ID de proveedor y el metacampo Clave de fuente de coste. |
| **Previsión** | Asegúrese de que los valores pasan del objeto Fuente de costes al objeto Proveedores.  Las claves que unen los dos conjuntos de datos incluyen el ID de proveedor y el metacampo Clave de fuente de coste. |
| **CapEx** | Asegúrese de que los valores pasan del objeto Fuente de costes al objeto Proveedores.  Las claves que unen los dos conjuntos de datos incluyen el ID de proveedor y el metacampo Clave de fuente de coste. |
| **CapEx Presupuesto** | Asegúrese de que los valores pasan del objeto Fuente de costes al objeto Proveedores.  Las claves que unen los dos conjuntos de datos incluyen el ID de proveedor y el metacampo Clave de fuente de coste. |
| **CapEx Previsión** | Asegúrese de que los valores pasan del objeto Fuente de costes al objeto Proveedores.  Las claves que unen los dos conjuntos de datos incluyen el ID de proveedor y el metacampo Clave de fuente de coste. |

## Revisar los informes de los proveedores

Los siguientes informes se actualizan una vez configurado el objeto Proveedores:

- Revisión de proveedores
- Cartera de proveedores
- Lista de proveedores
- Gastos de proveedores por proyecto
- Vendedores Validez
- Dimensiones de los datos - Proveedores
- Proveedor - Tendencia del centro de coste
- Proveedor - IT Tower Trend
- Proveedor - Tendencia del proyecto
- Proveedor - Tendencia del tipo de proveedor
- Detalles del vendedor
- Detalles del tipo de vendedor

Para ver los detalles de estos informes (incluida la navegación, las funciones, los objetivos y las preguntas a las que responde cada informe), consulte la Guía del usuario de Costing Standard en la Ayuda en línea.

## Seguimiento y gestión de los gastos de proveedores

La empresa típica habilitada para TBM utilizará Apptio para conocer mejor el coste y el valor de sus relaciones con los proveedores, supervisando la utilización de los distintos productos y servicios que ofrecen, así como las métricas relacionadas con la relación coste-volumen.

Apptio permite a los departamentos de compras, jurídico, financiero y de TI alinear los puntos de vista sobre el rendimiento financiero de los proveedores y aclarar la naturaleza de la contribución de un proveedor al valor de TI. Además, Apptio tiende un puente entre lo viejo y lo nuevo, proporcionando información estándar sobre la facturación de los proveedores de la nube y comparaciones de las tendencias de los costes unitarios. Los departamentos financieros y de TI pueden ver ahora los detalles significativos de lo que hacen los proveedores, qué tipos de proveedores contratan y cómo se comparan con las alternativas basadas en la nube.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/vendors-workshop.png)

Este procedimiento abarca el análisis de proveedores estratégicos, preferentes y transaccionales en función del coste total, el presupuesto, el objetivo, el centro de costes CapEx/OpEx,, el proyecto, la torre, la subtorre y la función del proveedor. Esto incluye el seguimiento de los proveedores por tipo y por objetivo de gasto con análisis de series temporales y métricas clave.

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
