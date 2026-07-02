---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Dispositivos para usuarios finales: Introducción"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso de la solución"
  - "Usuario final"
source_path: "cost-transparency/solution-uc/eud-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Dispositivos para usuarios finales: Introducción

El componente Dispositivos de usuario final permite a las organizaciones comprender el coste total de propiedad de los dispositivos de la plantilla, como ordenadores personales, portátiles, teléfonos inteligentes, tabletas y otros equipos informáticos de cliente. Este componente permite asignar con precisión los costes de los dispositivos de los usuarios finales a los servicios y unidades de negocio que los consumen.

## Instalación de componentes

**Aplicaciones CT: dispositivos para usuarios finales**

El componente CT Apps – Dispositivos de usuario final instala las estructuras de datos fundamentales, los conjuntos de datos y las estrategias de asignación recomendadas necesarias para calcular el TCO de los dispositivos de usuario final. Permite asignar los costes de los dispositivos a los servicios de los usuarios finales y a servicios empresariales específicos en los que se utilizan recursos informáticos distribuidos.

## Prerrequisito

Debe instalar los siguientes componentes antes de instalar el componente Dispositivos de usuario final:

CTF: Fuente de costes

CTF- Torres de TI

## Fuentes comunes de datos

Los datos sobre el coste y el inventario de los dispositivos de los usuarios finales suelen obtenerse de sistemas de contabilidad general, plataformas de gestión de activos, herramientas de gestión de terminales y sistemas de adquisición. Estas fuentes determinan el nivel de detalle disponible para el análisis de los costes, la propiedad y la asignación de los dispositivos.

## Conjuntos de datos

Al instalar el componente CT Apps – Dispositivos de usuario final, se crea un nuevo grupo Dispositivos de usuario final con las siguientes tablas:

• Dispositivos de usuario final (tabla de modelos)

• Datos maestros de dispositivos de usuario final

Después de cargar los datos de los dispositivos de los usuarios finales, asigne el conjunto de datos a la tabla de datos maestros de dispositivos de usuarios finales. Una vez mapeados, los costes fluyen desde las torres de recursos informáticos y las comunicaciones hasta los dispositivos de los usuarios finales, y desde los dispositivos de los usuarios finales hasta los servicios empresariales que consumen dentro del modelo de costes.
