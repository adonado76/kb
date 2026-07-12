---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "CT Apps - Componente Servidores"
breadcrumb: []
source_path: "cost-transparency/configuration/servers.html"
images:
  - "resources/images/ct_images/6864_1.png"
  - "resources/images/ct_images/6864_2.png"
  - "resources/images/ct_images/6864_3.png"
  - "resources/images/ct_images/6864_4.png"
  - "resources/images/ct_images/6864_5.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# CT Apps - Componente Servidores

El componente Servers es un prerrequisito fundamental que utiliza el componente Servers Insights. El componente Servidores no proporciona nuevos informes, sino que se utiliza para crear métricas que se exponen en el componente Server Insights.

Se aplica a: Costing Standard en TBM Studio 12.0 y posteriores

Icono de componente:

![CT Apps - Componente Servidores](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6864_1.png)

## Cuadros de apoyo

Al instalar el componente CT Apps - Servidores, se crean tres nuevos grupos de tablas como se muestra en la siguiente imagen.

![grupos de mesas](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6864_2.png)

Cada grupo contiene un mínimo de dos tablas: una tabla de datos maestros y una tabla modelo. Las tablas modelo son: Hipervisor, Servidor Físico y Servidores.

## Relación entre las tablas Servidores, Hipervisor y Servidor Físico

La tabla Servidores enumera todos los servidores físicos y virtuales. No incluye los servidores del hipervisor. Los servidores del hipervisor se asignan a los servidores virtuales de una de estas dos maneras en función de los datos:

- Si un servidor virtual PUEDE asociarse con el servidor en el que está alojado, enumere el servidor en la tabla Hipervisor.
- Si un servidor virtual NO PUEDE asociarse al servidor en el que está alojado, reparta los costes del hipervisor entre los servidores virtuales ponderados por el tamaño del servidor virtual.

La tabla Servidores Físicos sólo muestra los servidores físicos.

- La tabla Hipervisores enumera los servidores físicos que alojan servidores virtuales. A menudo puede identificar estos servidores porque los datos del servidor mostrarán estos ID de servidor en una columna HOSTED ON. Esto significa que hay servidores alojados en el servidor físico. Además, algunos datos de Servidor muestran una columna de Hipervisor con un "sí" o un "no". Por último, una forma adicional de identificar estos servidores se basa en el software asociado a estos servidores - VMWare ESX se asocia comúnmente con Hipervisores.

## Datos maestros

Para obtener una descripción de los campos de las tres tablas de datos maestros, consulte la información de la página del componente CT Apps Servers del producto. Para visualizar la página:

1. Haga clic en la pestaña **Proyecto** de la cinta de opciones.
2. Haga clic en **Componentes**.
3. Haga clic en el componente **CT Apps - Servidores**.

## Transformar los datos del servidor

Normalmente, subirá un archivo que contiene los datos de las tres tablas de datos maestros: Datos Maestros de Servidores, Datos Maestros de Servidores Físicos, Datos Maestros de Hipervisores. Creará una copia del fichero y lo modificará para incluir los datos que necesita cada una de las tablas de datos maestros.

Para acomodar los tres conjuntos de datos maestros, cree tres nuevas tablas a partir de la tabla de datos del servidor original:

1. Haga clic en Nuevo > Tabla en la cinta de opciones.
2. Asigne a la tabla un nombre que se asocie fácilmente con la tabla de datos maestros.
3. Para el origen, haga clic en Tabla existente y seleccione la tabla de datos del servidor original.
4. Repite la operación para las otras dos mesas.

## Tabla de datos de servidores

Cuando asigne los datos de los servidores a la tabla Datos maestros de servidores, debe incluir todos los servidores físicos y virtuales, pero no los servidores de hipervisor. Debe filtrar los datos de los servidores para excluir los servidores del hipervisor.

1. Abra la tabla de datos de servidores que ha creado.
2. Añada un paso de **Filtro** a la cadena de transformación similar al siguiente ejemplo de filtro.

   ![tuberías de transformación](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6864_3.png)

## Datos de los servidores físicos

Al asignar los datos de los servidores a la tabla Datos maestros de servidores físicos, debe incluir todos los servidores físicos e hipervisores, pero no los servidores virtuales. Debe filtrar los datos de los servidores para excluir los servidores virtuales utilizando un filtro similar al que se muestra a continuación.

![Servidores físicos Datos maestros](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6864_4.png)

**AVISO**

Cuando asigne los datos a la tabla de Datos Maestros de Servidores Físicos, deberá incluir el texto "Asset\_Resource - Compute" al principio del campo ITRT\_Server Key. Por ejemplo:

="Recurso\_activo - Computación"&&Categoría\_del\_sistema\_operativo

## Datos del hipervisor

Al asignar los datos de los servidores a la tabla Datos maestros del hipervisor, ésta debe incluir sólo los hipervisores, pero no los servidores físicos o virtuales. Debe filtrar los datos de los servidores para excluir los servidores físicos y virtuales utilizando un filtro similar al que se muestra a continuación.

![Datos del hipervisor](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6864_5.png)

## Mapear los datos

Una vez creadas las tres tablas de datos, asígnelas a sus respectivas tablas de Datos Maestros.

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
