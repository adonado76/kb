---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Taller de servidores"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/serversworkshop.html"
images:
  - "resources/images/ct_images/servers-workshop.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Taller de servidores

## Preparación de los datos de sus servidores

1. Si aún no lo has hecho, carga los datos de tu servidor incluyendo:
   - Lista de servidores
   - Datos de supervisión del servidor
2. Siguiendo las prácticas habituales de Apptio prácticas estándar, clasifique cada conjunto de datos brutos en la categoría de Servidores.

## Transformaciones de datos del servidor

¿Incluyen sus datos de servidor todos los servidores físicos, hipervisores y servidores virtuales o están en conjuntos de datos separados? Si tienes un conjunto de datos que combina cualquiera de estos tres tipos de servidores, necesitas crear transformaciones para tener un conjunto de datos separado para cada uno de los siguientes:

- Servidores físicos
- Hipervisores
- Virtual Servers

Esto suele requerir el análisis de los datos de sus servidores para determinar qué se incluye y cómo segmentar los servidores en estas tres categorías. Puede utilizar la opción Filtro de datos de la transformación para limitar los registros mostrados a través de la transformación.

## Relación entre servidores físicos, hipervisores y servidores

Un servidor físico es una pieza específica de hardware que puede ser un servidor físico dedicado o una máquina anfitriona para servidores virtuales.

Un hipervisor es un programa informático que ejecuta servidores virtuales.

Un servidor virtual es un servidor que ejecuta su propia copia de un sistema operativo y software, pero está alojado en un servidor físico que puede estar compartido con muchos servidores virtuales.

El siguiente diagrama muestra cómo Apptio gestiona la relación entre servidores físicos, hipervisores, servidores virtuales y servidores físicos dedicados.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/servers-workshop.png)

## Acerca de los identificadores de servidor

El identificador del conjunto de datos maestros de servidores físicos es el ID de servidor físico. Debe tener alguna forma de identificar cada servidor físico y utilizarlo como ID de servidor físico.

El identificador del conjunto de datos maestros de hipervisores es el ID de hipervisor. Al igual que con los servidores físicos, debe tener alguna forma de identificar cada hipervisor y utilizarlo como ID del hipervisor.

El identificador del conjunto de datos maestros de servidores es el ID de servidor. Debe tener alguna forma de identificar cada servidor y utilizarlo como ID de servidor.

## Columnas computadas comunes necesarias para los servidores

Para los distintos tipos de servidores (que puede tener en uno o varios conjuntos de datos), hay un par de columnas computadas que puede desear tener.

- Perfil de virtualización (como físico, hipervisor o virtual)
- Es Máquina Virtual (como verdadero o falso)

A continuación, puede utilizar estas nuevas columnas para filtrar sus transformaciones y construir claves entre conjuntos de datos (véase la sección siguiente).

## Acerca de las claves de servidor

Todas las claves del conjunto de datos maestros del servidor físico están definidas por el usuario. La lógica recomendada figura en el cuadro siguiente.

| Clave | La clave de campo se basa en | Lógica recomendada |
| --- | --- | --- |
| **ITRT\_Servidor Clave** | Definida por el usuario | ="Asset\_Resource - Compute"&&OS    OS es el sistema operativo. El nombre de tu columna puede llamarse de otra manera. |
| **Clave\_Servidor\_almacenamiento** | Definida por el usuario | ="Clave\_servidor\_almacenamiento"&&Denominación\_dispositivo    Nombre del dispositivo es el nombre del hardware que vincula el almacenamiento al servidor físico específico. El nombre de tu columna puede llamarse de otra manera. Debe coincidir con la Clave\_Servidor\_almacenamiento que definió en Datos maestros de almacenamiento. |
| **DC\_Server Clave** | Definida por el usuario | ="DC\_Server Key"&&Localización    Utilícelo sólo si está implementando el componente Centros de datos. La Ubicación es el nombre del centro de datos. El nombre de tu columna puede llamarse de otra manera. |
| **Clave\_Servidor\_de\_activos** | Definida por el usuario | La lógica recomendada es "Asset\_Server" && Server ID |
| **Tecla Phys\_Hyp** | Definida por el usuario | =If(Virtualization Profile!= "Physical", "Phys\_Hyp Key"&&Location,"")    Al comprobar si el perfil de virtualización no es físico, se asegura de que sólo las máquinas host y los servidores virtuales tienen una clave Phys\_Hyp. |
| **Phys\_Server Clave** | Definida por el usuario | =If(Virtualization Profile="Physical", "Phys\_Server Key"&&Device Name,"")    Al comprobar si el perfil de virtualización es físico, se asegura de que sólo los servidores físicos dedicados tienen la clave Phys\_Server. |

Las claves del conjunto de Datos Maestros de Hipervisores son todas definidas por el usuario. La lógica recomendada figura en el cuadro siguiente.

| Clave | La clave de campo se basa en | Lógica recomendada |
| --- | --- | --- |
| **Tecla Phys\_Hyp** | Definida por el usuario | ="Phys\_Hyp Key" && Localización |
| **Hyp\_Server Clave** | Definida por el usuario | ="Hyp\_Server Key" && Ubicación |

Todas las claves del conjunto de datos maestros de los servidores están definidas por el usuario. La lógica recomendada figura en el cuadro siguiente.

| Clave | La clave de campo se basa en | Lógica recomendada |
| --- | --- | --- |
| **Hyp\_Server Clave** | Definida por el usuario | ="Hyp\_Server Key" && Ubicación |
| **Phys\_Server Clave** | Definida por el usuario | ="Phys\_Server Key" && ID del servidor |
| **Clave Server\_App** | Definida por el usuario | ="Server\_App" && ID de aplicación |
| **Clave\_Servidor\_de\_Comunicación** | Definida por el usuario | ="Communication\_Server" && Conexión al servidor |

## Asignación de datos a datos maestros de servidores físicos, datos maestros de hipervisores y datos maestros de servidores

Asigne los datos de su servidor físico al conjunto de datos maestros del servidor físico. La mayor parte de la cartografía debería explicarse por sí misma en este punto. En 12.7 ahora puede aprovechar la función Column Map en su conjunto de datos sin procesar para asignarlo a los datos maestros de los servidores físicos ([Map Columns](https://community.apptio.com/docs/DOC-10561 "(se abre en una pestaña o una ventana nueva)") )

Asigne sus datos del hipervisor al conjunto de datos maestros del hipervisor. En 12.7 ahora puede aprovechar la función Column Map en su conjunto de datos sin procesar para asignarlos a los datos maestros del hipervisor ([Map Columns](https://community.apptio.com/docs/DOC-10561 "(se abre en una pestaña o una ventana nueva)") )

Asigne los datos de sus servidores físicos y virtuales al conjunto de datos maestros de servidores. En 12.7 ahora puede aprovechar la función Column Map en su conjunto de datos sin procesar para asignarlo a los datos maestros del servidor ([Map Columns](https://community.apptio.com/docs/DOC-10561 "(se abre en una pestaña o una ventana nueva)") )

La mayoría de las asignaciones deberían explicarse por sí mismas en este punto. En cualquier lugar donde vea Unidades reales, Unidades presupuestadas, Recuento de artículos o Recuento de servidores, puede establecer **=1** si está utilizando el ID del servidor como identificador en cada uno de los conjuntos de datos.

## Revisar el objeto Servidores en los modelos

| Modelo | Acciones |
| --- | --- |
| **Coste** | Asegúrese de que los valores fluyen hacia los objetos Servidor físico, Hipervisor y Servidores.  De las Torres de Recursos TI al Servidor Físico, asigne utilizando la Referencia Basada en Datos, ponderada por Unidades Reales (esta es la configuración por defecto). Las claves que unen las torres de recursos de TI y el servidor físico son la clave Asset\_Resource en el lado de las torres de recursos de TI y la clave ITRT\_Server en el lado del servidor físico.  De Almacenamiento a Servidor Físico, asigne usando la Referencia Basada en Datos con una ponderación uniforme (esta es la configuración por defecto). Las claves que unen Storage con Physical Server son las columnas Storage\_Server Key en ambos conjuntos de datos.  Del Servidor Físico al Hipervisor, asigne usando la Referencia Basada en Datos con una ponderación uniforme (esta es la configuración por defecto). Las claves que unen el Servidor Físico con el Hipervisor son las columnas Phys\_Hyp Key en ambos conjuntos de datos.  De Servidor Físico a Servidores, asignar usando la Referencia Basada en Datos con una ponderación uniforme (esta es la configuración por defecto). Las claves que unen el Servidor Físico con los Servidores son las columnas Clave\_Servidor\_Físico en ambos conjuntos de datos.  NOTA: Es posible que tenga que marcar la casilla Crear automáticamente una relación entre varios para esta asignación.  Del Hipervisor a los Servidores, asigne utilizando la Referencia basada en Datos, ponderada por la Capacidad de Memoria (esta es la configuración por defecto). Las claves que unen el Hipervisor con los Servidores son las columnas Hyp\_Server Key en ambos conjuntos de datos. |
| **Presupuesto** | Asegúrese de que los valores fluyen hacia los objetos Servidor físico, Hipervisor y Servidores.  De las Torres de Recursos TI al Servidor Físico, asigne utilizando la Referencia Basada en Datos, ponderada por Unidades Reales (esta es la configuración por defecto). Las claves que unen las torres de recursos de TI y el servidor físico son la clave Asset\_Resource en el lado de las torres de recursos de TI y la clave ITRT\_Server en el lado del servidor físico.  De Almacenamiento a Servidor Físico, asigne usando la Referencia Basada en Datos con una ponderación uniforme (esta es la configuración por defecto). Las claves que unen Storage con Physical Server son las columnas Storage\_Server Key en ambos conjuntos de datos.  Del Servidor Físico al Hipervisor, asigne usando la Referencia Basada en Datos con una ponderación uniforme (esta es la configuración por defecto). Las claves que unen el Servidor Físico con el Hipervisor son las columnas Phys\_Hyp Key en ambos conjuntos de datos.  De Servidor Físico a Servidores, asignar usando la Referencia Basada en Datos con una ponderación uniforme (esta es la configuración por defecto). Las claves que unen el Servidor Físico con los Servidores son las columnas Clave\_Servidor\_Físico en ambos conjuntos de datos.  NOTA: Es posible que tenga que marcar la casilla Crear automáticamente una relación entre varios para esta asignación.  Del Hipervisor a los Servidores, asigne utilizando la Referencia basada en Datos, ponderada por la Capacidad de Memoria (esta es la configuración por defecto). Las claves que unen el Hipervisor con los Servidores son las columnas Hyp\_Server Key en ambos conjuntos de datos. |

## Revisar los informes del servidor

Los siguientes informes se actualizan después de haber configurado el objeto Servidores:

- TCO del servidor
- Infra - Servidor TCO - Detalle
- Infra - Resumen - Servidores
- Comparación de servidores
- Validez de los servidores
- Aplicación Infra
- Infraestructura de aplicaciones: detalles de computación
- Dimensiones de los datos - Servidores
- Calidad de datos - Recursos informáticos
- Calidad de datos - Servidores

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
