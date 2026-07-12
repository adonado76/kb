---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Taller sobre dispositivos de usuario final"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/eudevicesworkshop.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Taller sobre dispositivos de usuario final

## Preparación de los datos de los dispositivos de usuario final

1. Si aún no lo has hecho, carga los datos de tus dispositivos de usuario final como:
   - Sistemas de sobremesa
   - Dispositivos móviles
   - Cualquier dispositivo de usuario final
2. Siguiendo las prácticas habituales de Apptio las prácticas habituales, clasifique cada conjunto de datos brutos en la categoría 01 - Datos brutos.
3. Si procede, aplique un filtro de fecha a los datos de sus dispositivos de usuario final.

## Acerca de los identificadores de dispositivos de usuario final

El identificador para el conjunto de datos maestros de dispositivos de usuario final es Object Identifier por defecto. Debe tener alguna forma de identificar cada dispositivo de usuario final y utilizarlo como identificador de objeto.

## Acerca de las claves de los dispositivos de usuario final

Algunas de las claves del conjunto de datos maestros de usuario final son generadas por el sistema y otras son definidas por el usuario. Cualquier clave generada por el sistema no debe ser alterada. Las teclas predefinidas son:

ITRT\_End Clave de dispositivos de usuario
:   Clave generada por el usuario utilizada para asignar costes del objeto Torre de recursos de TI al objeto Dispositivos de usuario final.

Communication\_End User Devices Clave
:   Clave generada por el usuario que se utiliza para asignar costes del objeto Comunicaciones al objeto Dispositivos de usuario final.

Dispositivos de red\_Dispositivos de usuario final Clave
:   Clave generada por el usuario utilizada para asignar costes del objeto Dispositivos de red al objeto Dispositivos de usuario final.

Usuario final Dispositivos\_Servicios Clave
:   Clave generada por el usuario utilizada para asignar costes del objeto Dispositivos de usuario final al objeto Servicios.

Server\_End User Devices Clave
:   Una clave generada por el usuario para asignar instancias de servidor utilizadas para alojar instancias VDI

## Asignar datos a los datos maestros de los dispositivos de usuario final

Asigne sus datos de dispositivos de usuario final al conjunto de datos maestros de dispositivos de usuario final. En 12.7, ahora puede aprovechar la función de asignación de columnas en su conjunto de datos sin procesar para asignarlos a los datos maestros de los dispositivos de usuario final ([asignar columnas](https://community.apptio.com/docs/DOC-10561 "(se abre en una pestaña o una ventana nueva)") )

## Informes sobre dispositivos de usuario final

Actualmente no hay informes que se iluminen después de añadir datos al conjunto de datos Datos maestros de dispositivos de usuario final.

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
