---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Taller de almacenamiento"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/storageworkshop.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Taller de almacenamiento

## Preparación de los datos de almacenamiento

1. Si aún no lo has hecho, carga tus datos de almacenamiento incluyendo:
   - Dispositivos de almacenamiento
     - Matrices (ejemplo)
     - Copia de seguridad en cinta (ejemplo)
   - Almacenamiento
     - LUNS (Ejemplo)
2. Siguiendo las prácticas habituales de Apptio prácticas estándar, clasifique cada conjunto de datos brutos en la categoría de Almacenamiento.
3. Si procede, aplique un filtro de fechas a sus datos de almacenamiento.

## Acerca de los identificadores de almacenamiento

El identificador del conjunto de datos maestros de dispositivos de almacenamiento es el ID del dispositivo de almacenamiento. Debe tener alguna forma de identificar cada dispositivo de almacenamiento y utilizarlo como ID del dispositivo de almacenamiento.

El identificador del conjunto de datos maestros de almacenamiento es el ID de almacenamiento. Un dispositivo de almacenamiento puede contener varios hosts de almacenamiento. Este identificador debe ser el ID de los hosts de almacenamiento independientes.

## Acerca de las claves de almacenamiento

Algunas de las claves del conjunto de datos maestros de dispositivos de almacenamiento son generadas por el sistema y otras son definidas por el usuario. Cualquier clave generada por el sistema no debe ser alterada. La lógica recomendada para las teclas definidas por el usuario figura en la tabla siguiente.

| Clave | La clave de campo se basa en | Lógica |
| --- | --- | --- |
| **Tecla ITRT\_Storage** | Definida por el usuario | La lógica recomendada es añadir Asset\_Resource - "Storage" y Sub-Tower |
| **Asset\_Storage Clave** | Definida por el usuario | Clave opcional que permite una referencia basada en datos entre Activos Fijos y Dispositivos de Almacenamiento |
| **Dispositivos\_Clave de almacenamiento** | ID del dispositivo de almacenamiento  Ubicación | Añada el ID del dispositivo de almacenamiento y la ubicación |
| **Dispositivos de red\_Clave de dispositivos de almacenamiento** | Definida por el usuario | La lógica recomendada es añadir Dispositivos de red\_dispositivos de almacenamiento con el ID del dispositivo de almacenamiento |

Algunas de las claves del conjunto de datos maestros de almacenamiento son generadas por el sistema y otras son definidas por el usuario. Cualquier clave generada por el sistema no debe ser alterada. La lógica recomendada para las teclas definidas por el usuario figura en la tabla siguiente.

| Clave | La clave de campo se basa en | Lógica |
| --- | --- | --- |
| **Clave\_Servidor\_almacenamiento** | Definida por el usuario | La lógica recomendada es añadir la clave Storage\_Server al ID del dispositivo de almacenamiento |
| **Dispositivos\_Clave de almacenamiento** | ID del dispositivo de almacenamiento  Ubicación | Añada el ID del dispositivo de almacenamiento y la ubicación |
| **Almacenamiento\_App Clave** | Definida por el usuario | La lógica recomendada es añadir la clave Storage\_Server al ID de la aplicación |
| **Clave\_Servidor\_almacenamiento** | Definida por el usuario | La lógica recomendada es añadir la clave Storage\_Server al ID del servidor |

## Columnas computadas comunes necesarias para el almacenamiento

Aparte de las claves definidas por el usuario mencionadas anteriormente, no es necesario crear ninguna columna calculada específica. Variará en función de tus datos, pero normalmente tendrás que calcular los recursos que utilizan el almacenamiento y asignarlos directamente a esos elementos de la infraestructura. Los atributos complementarios ayudan a elaborar informes, como las estadísticas de capacidad y utilización.

## Asignación de datos a dispositivos de almacenamiento y datos maestros de almacenamiento

Asigne los datos de su dispositivo de almacenamiento al conjunto de datos maestros de dispositivos de almacenamiento. La mayor parte de la cartografía debería explicarse por sí misma en este punto.

Si establece su identificador en el ID del dispositivo de almacenamiento, asigne =1 al campo Unidades reales. Si no dispone de datos de dispositivos de almacenamiento presupuestados, también puede establecer el campo Unidades presupuestadas en =1. En 12.7 ahora puede aprovechar la función Column Map en su conjunto de datos sin procesar para asignarlo a los datos maestros de los dispositivos de almacenamiento ([Map Columns](https://community.apptio.com/docs/DOC-10561 "(se abre en una pestaña o una ventana nueva)") )

Asigne sus datos de almacenamiento al conjunto de datos maestros de almacenamiento. La mayor parte de la cartografía debería explicarse por sí misma en este punto.

Si establece su identificador en el nombre del host de almacenamiento, asigne =1 al campo Unidades reales. Si no dispone de datos de almacenamiento presupuestados, también puede establecer el campo Unidades presupuestadas en =1. En 12.7 ahora puede aprovechar la función Column Map en su conjunto de datos brutos para asignarlos a los datos maestros de almacenamiento ([Map Columns](https://community.apptio.com/docs/DOC-10561 "(se abre en una pestaña o una ventana nueva)") )

## Revisar los objetos de almacenamiento en los modelos

| Modelo | Acciones |
| --- | --- |
| **Coste** | Asegúrese de que los valores fluyen hacia los objetos Dispositivos de almacenamiento y Almacenamiento.  De las Torres de Recursos TI a los Dispositivos de Almacenamiento, asigne utilizando la Referencia basada en Datos, ponderada por las Unidades Maestras de Dispositivos de Almacenamiento Data.Actual (esta es la configuración por defecto). Las claves que unen las torres de recursos de TI y los dispositivos de almacenamiento son la clave Asset\_Resource en el lado de las torres de recursos de TI y la clave ITRT\_Storage en el lado de los dispositivos de almacenamiento.  De Dispositivos de almacenamiento a Almacenamiento, asignación mediante la Referencia basada en datos (esta es la configuración predeterminada). La clave que une los dos conjuntos de datos es la clave Dispositivos\_almacenamiento. |
| **Presupuesto** | Asegúrese de que los valores fluyen hacia los objetos Dispositivos de almacenamiento y Almacenamiento.  De las Torres de Recursos TI a los Dispositivos de Almacenamiento, asigne utilizando la Referencia basada en Datos, ponderada por las Unidades Maestras de Dispositivos de Almacenamiento Data.Budgeted (esta es la configuración por defecto). Las claves que unen las torres de recursos de TI y los dispositivos de almacenamiento son la clave Asset\_Resource en el lado de las torres de recursos de TI y la clave ITRT\_Storage en el lado de los dispositivos de almacenamiento.  De Dispositivos de almacenamiento a Almacenamiento, asignación mediante la Referencia basada en datos (esta es la configuración predeterminada). La clave que une los dos conjuntos de datos es la clave Dispositivos\_almacenamiento. |

## Revisar los informes de almacenamiento

Los siguientes informes se actualizan después de haber configurado el objeto Almacenamiento:

- TCO de almacenamiento
- Infra - TCO de almacenamiento - Detalle
- Infra - TCO de almacenamiento - Detalle LUN
- Infra - Resumen - Almacenamiento
- Revisión de infraestructuras
- Validez de almacenamiento
- Aplicación Infra
- App Infra - Detalle de almacenamiento
- Dimensiones de los datos - Almacenamiento
- Calidad de datos - Recursos informáticos
- Calidad de datos - Almacenamiento

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
