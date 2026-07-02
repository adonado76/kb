---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Informática: Introducción"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso de infraestructura"
  - "Computación"
source_path: "cost-transparency/infra-use-cases/compute-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Informática: Introducción

## Introducción: descripción general de los costes informáticos

Utilice los componentes de gestión informática para cargar y gestionar los datos de inventario, utilización, coste y ciclo de vida de los servidores necesarios para la transparencia de los costes informáticos y el análisis del coste total de propiedad a nivel de aplicación. Esta capacidad establece el modelo de datos fundamental para analizar los costes informáticos en entornos físicos, virtuales, de nube privada y de nube pública, y admite la generación de informes sobre los costes de infraestructura y aplicaciones posteriores.

**Instalación de componentes**

CT Apps– Servers: el componente CT Apps– Servers proporciona las estructuras de datos, métricas y asignaciones básicas necesarias para modelar los costes de la infraestructura de servidores y asociarlos a las aplicaciones. Este componente es un requisito previo para la generación de informes avanzados de Server Insights y permite asignar los costes de la infraestructura informática a las aplicaciones para facilitar el análisis del coste total de propiedad (TCO).

**Requisitos previos:**

• Fuente del coste

• Torres de TI

**Fuentes comunes de datos**

Los datos informáticos suelen proceder de una combinación de sistemas de infraestructura y empresariales. Las fuentes comunes incluyen herramientas de supervisión de servidores para métricas de CPU, memoria y utilización; plataformas de virtualización como VMware o Hyper-V para relaciones entre máquinas virtuales y hosts; sistemas de gestión de activos para inventario de servidores, configuración y detalles del ciclo de vida; CMDB para relaciones entre servidores y aplicaciones y clasificación del entorno; herramientas de gestión de servicios para datos de incidentes y soporte; y sistemas de contabilidad general para costes relacionados con el hardware, el software, la mano de obra y el soporte informático.

**Conjuntos de datos**

La solución Compute Management requiere que se rellenen y asignen correctamente varios conjuntos de datos maestros. Estos incluyen datos maestros de servidor para todos los servidores físicos y virtuales, datos maestros de servidor físico para hosts físicos e hipervisores, y datos maestros de hipervisor para servidores que alojan cargas de trabajo virtuales. Los datos del servidor suelen proceder de una única extracción del inventario y se transforman en conjuntos de datos independientes para garantizar un modelado preciso de los servidores físicos, los servidores virtuales y los hipervisores, lo que permite una asignación correcta de los costes y un análisis adecuado de la utilización.

## Introducción: información y optimización informáticas

Compute Insights & Optimization proporciona una visibilidad profunda de los costes, la capacidad, la utilización y la eficiencia de los servidores en entornos de infraestructura híbrida. Esta capacidad se basa en el **componente** fundamental CT Apps-Servers y lo amplía a través **de BI-Server Insights**, que forma parte del módulo Infrastructure Insights. En conjunto, estos componentes permiten realizar análisis operativos y financieros avanzados de entornos de servidores físicos y virtuales, lo que facilita la optimización, la estandarización y la toma de decisiones sobre el ciclo de vida.

**Instalación de componentes**

**BI - Server Insights** : Compute Insights & Optimization se habilita a través del **componente** BI - Server Insights. Este componente ofrece un análisis mejorado de la infraestructura del servidor, incluyendo tendencias de costes unitarios, eficiencia de utilización y rendimiento operativo en entornos locales y en la nube.

**Prerrequisito**

Antes de instalar Server Insights, es necesario instalar los siguientes componentes:

• CTF: fuente de costes

• Torres CTF-IT

• Aplicaciones CT – Servidores

**Fuentes comunes de datos**

Los datos sobre informática e infraestructura suelen proceder de inventarios de servidores y sistemas de supervisión, plataformas de virtualización como VMware vCenter, sistemas de gestión de centros de datos y activos, y datos de facturación de la nube pública de proveedores como AWS, Azure y Google Cloud, cuando procede. Las métricas de utilización incluyen el uso promedio y máximo de la CPU y la memoria, junto con los datos de utilización del almacenamiento, cuando estén disponibles.

**Conjuntos de datos maestros**

La función Server Insights se basa en conjuntos de datos recopilados a través del componente CT Apps – Servers, que incluye datos maestros de servidores físicos, servidores lógicos (VM) e hipervisores, combinados con datos de costes de Cost Source y asignaciones de torres de IT Towers. Estos conjuntos de datos permiten realizar modelos detallados de los costes, la utilización y la asignación de los servidores a aplicaciones y servicios para el análisis de optimización.
