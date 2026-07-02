---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Almacenamiento: Introducción"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso de infraestructura"
  - "Almacenamiento"
source_path: "cost-transparency/infra-use-cases/storage-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Almacenamiento: Introducción

## Introducción: descripción general de los costes de almacenamiento

La solución Storage Cost Overview permite a las organizaciones establecer una transparencia de costes fundamental para la infraestructura de almacenamiento, asignando los costes de almacenamiento a las aplicaciones y servicios para comprender el verdadero coste total de propiedad del almacenamiento. Proporciona visibilidad del gasto en almacenamiento en entornos locales y en la nube, y es un requisito previo para el análisis y la optimización avanzados del almacenamiento disponibles a través de Storage Insights.

**Instalación de componentes**

**CT Apps- Almacenamiento** : la solución «Descripción general de los costes de almacenamiento» se habilita instalando el **componente CT Apps-** Almacenamiento. Este componente instala las estructuras de datos básicas, las métricas y los informes de almacenamiento fundamentales necesarios para el análisis del coste total de propiedad del almacenamiento y la asignación de costes de las aplicaciones.

**Prerrequisito**

Antes de instalar el componente CT Apps-Storage, deben estar instalados los siguientes componentes:

- CTF: Fuente de costes
- CTF- Torres de TI

**Fuentes comunes de datos**

Los datos sobre los costes de almacenamiento y el inventario suelen proceder de una combinación de sistemas financieros y de infraestructura. Las fuentes comunes incluyen sistemas de gestión de activos para dispositivos de almacenamiento e inventario de LUN, plataformas de gestión de almacenamiento para información sobre capacidad y niveles, bases de datos de gestión de configuraciones para relaciones entre aplicaciones y el libro mayor para costes relacionados con el almacenamiento, como hardware, software, mano de obra y asistencia técnica.

**Conjuntos de datos**

Para habilitar los informes de costes de almacenamiento, los datos deben cargarse y asignarse a los conjuntos de datos maestros de almacenamiento central instalados con el componente CT Apps-Storage. Estos conjuntos de datos incluyen datos maestros de dispositivos de almacenamiento que contienen atributos físicos de almacenamiento y datos maestros de almacenamiento que recogen información sobre unidades lógicas, capacidad, niveles, fuentes y entorno. Una vez completados, estos conjuntos de datos respaldan los informes sobre el coste total de propiedad del almacenamiento básico y proporcionan información sobre el almacenamiento posterior.

## Introducción: optimización y Storage Insights

Storage Insights & La optimización amplía la visibilidad de los costes básicos de almacenamiento con análisis más profundos de las operaciones, la capacidad y la utilización. Permite a las organizaciones analizar la rentabilidad del almacenamiento, los patrones de utilización y el estado del ciclo de vida en entornos locales, en la nube e híbridos. Esta capacidad respalda las revisiones operativas, las iniciativas de optimización y la planificación de la actualización tecnológica al combinar datos financieros, de capacidad y de utilización en una única vista analítica.

**Instalación de componentes**

BI- Storage Insights

Este componente proporciona un análisis mejorado de la infraestructura de almacenamiento, incluyendo visibilidad de los costes unitarios, la utilización y la eficiencia.

**Prerrequisito**

Para poder habilitarlo, es necesario instalar los siguientes componentes:

- CTF: Fuente de costes
- CTF- Torres de TI
- Aplicaciones de TC: almacenamiento

**Fuentes comunes de datos**

Storage Insights La optimización se basa en datos procedentes de múltiples sistemas empresariales y de infraestructura para proporcionar una visión completa del coste y la utilización del almacenamiento, incluyendo:

- Datos de la infraestructura de almacenamiento local que abarcan dispositivos de almacenamiento y unidades lógicas (LUN)
- Sistemas de inventario de centros de datos e infraestructura
- VMware vCenter para entornos de nube privada, recopilados a través de conectores Apptio Datalink (Classic) cuando corresponda
- Datos de facturación de la nube pública de AWS, Azure o Google Cloud, recopilados a través de conectores ApptioDatalink (Classic), cuando corresponda
- Datos de utilización del almacenamiento que recogen la capacidad bruta, asignada y utilizada
- Métricas operativas, incluidos los indicadores de utilización media y máxima

**Conjuntos de datos**

Storage Insights La optimización requiere que los siguientes conjuntos de datos se rellenen y asignen correctamente:

- Datos maestros de almacenamiento: unidades lógicas de almacenamiento (LUN), capacidad, asignación, nivel y atributos del entorno
- Datos maestros de dispositivos de almacenamiento: inventario físico de dispositivos de almacenamiento, tipo, modelo, proveedor, ubicación y detalles del ciclo de vida
