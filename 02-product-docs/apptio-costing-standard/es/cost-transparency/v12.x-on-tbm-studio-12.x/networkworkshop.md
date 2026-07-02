---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Taller de redes"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/networkworkshop.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Taller de redes

## Preparación de los datos de la red

La red difiere mucho según el cliente, ya que la definición significa cosas diferentes para las distintas empresas. A algunas empresas no les interesan los informes adicionales de la Red y, por tanto, sólo se utilizarán para costear los Servicios. Otras empresas dispondrán de dispositivos de red, centros de contacto, etc. Así pues, si existen estos datos, instale el componente, calcule el coste de los elementos, asigne los costes directamente a la infraestructura cuando pueda y envíe el resto a los servicios que utilizan redes.

1. Si aún no lo ha hecho, cargue los datos de su Red incluyendo (difiere mucho según el cliente):

   - Dispositivos de red
   - Datos de uso de la red
2. Siguiendo las prácticas estándar de Apptio las prácticas habituales, clasifique cada conjunto de datos brutos en la categoría de Dispositivos de red.
3. Si procede, aplique un filtro de fechas a los datos de su red.

## Acerca de los identificadores de red

Por defecto, el identificador del conjunto de datos maestros de dispositivos de red es Nombre del dispositivo. Debe tener alguna forma de identificar cada dispositivo de red y utilizarlo como nombre de dispositivo.

## Acerca de las claves de red

Algunas de las claves del conjunto de datos maestro de dispositivos de red son generadas por el sistema y otras son definidas por el usuario. Cualquier clave generada por el sistema no debe ser alterada. Las teclas predefinidas son:

- ITRT\_Network Devices Clave
- Dispositivos de red\_Mainframe Clave
- Dispositivos de red\_Phys Key
- Dispositivos de red\_Clave de dispositivos de almacenamiento
- DC\_Network Devices Clave

## Asignar datos a los datos maestros de la red

Asigne sus datos de dispositivos de red al conjunto de datos maestro de dispositivos de red. La mayor parte de la cartografía se explica por sí misma en este punto. En 12.7 ahora puede aprovechar la función Column Map en su conjunto de datos sin procesar para asignar a los Datos Maestros de Dispositivos de Red (Map Columns )

## Informes de la red

Actualmente no hay informes que se iluminen después de añadir datos al conjunto de datos Maestro de Dispositivos de Red.

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
