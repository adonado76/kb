---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Información sobre los usuarios finales: Introducción"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso de la solución"
  - "Usuario final"
source_path: "cost-transparency/solution-uc/eui-gs.html"
images:
  - "resources/images/ct_images/euigs.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Información sobre los usuarios finales: Introducción

El componente Dispositivos de usuario final proporciona visibilidad sobre el coste de los dispositivos de usuario final, como ordenadores personales, portátiles, teléfonos inteligentes, tabletas y otros equipos informáticos de cliente, y permite asignar dichos costes a la plantilla de la empresa.

Se trata de una solución independiente que no requiere la configuración del modelo de costes básico. Todos los datos necesarios se cargan directamente en las tablas de entrada, tal y como se describe en la guía de configuración.

## Instalación de componentes

**Dispositivos de usuario final**

El componente **Dispositivos de usuario final** instala el modelo Dispositivos de usuario final, las tablas maestras y de alimentación necesarias, la lógica de asignación y los informes predefinidos para analizar el inventario de dispositivos, el ciclo de vida, el cumplimiento normativo y los costes estimados de actualización.

**Nota:** Este componente está disponible en las plantillas **v110 y posteriores**.

## Requisitos previos

No hay requisitos previos, ya que la solución se puede instalar y utilizar de forma independiente

## Fuentes comunes de datos

Los datos de los dispositivos de los usuarios finales suelen proceder de una combinación de sistemas de identidad, personal y activos. Active Directory o servicios de directorio similares proporcionan información sobre el uso de dispositivos y la actividad de inicio de sesión, mientras que los sistemas de RR. HH. o de personal proporcionan atributos relacionados con los empleados, los centros de coste y la organización. Las herramientas de inventario de dispositivos y gestión de activos aportan información sobre el hardware, la propiedad, el ciclo de vida, la garantía y la actualización de ordenadores personales, portátiles, dispositivos móviles y otros terminales.

## Conjuntos de datos

El componente instala los conjuntos de datos y las tablas maestras necesarios. La configuración requiere crear tres tablas de entrada para garantizar que se carguen los detalles relevantes y, a continuación, asignarlas a las tablas maestras correspondientes.

- **Active Directory**
- **Dispositivos de usuario final**
- **Datos laborales**

  Ejemplo de referencia: El nombre de las tablas puede ser específico para cada cliente

  ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/euigs.png)

Para obtener más información sobre los pasos de configuración, vaya [aquí.](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=configuration-configure-end-user-devices "(se abre en una pestaña o una ventana nueva)")
