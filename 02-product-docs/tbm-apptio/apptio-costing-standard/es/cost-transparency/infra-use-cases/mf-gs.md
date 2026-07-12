---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Introducción al mainframe"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso de infraestructura"
  - "Sistema principal"
source_path: "cost-transparency/infra-use-cases/mf-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Introducción al mainframe

Utilice los componentes de TCO del mainframe para cargar y gestionar los datos de costes y consumo del mainframe necesarios para la elaboración de informes completos. La solución requiere la integración con IBM IntelliMagic Vision para obtener datos precisos sobre el uso y la conexión con su libro mayor para obtener información completa sobre los costes.

Instale y configure los componentes de TCO para mainframe antes de cargar los conjuntos de datos de costes, consumo y asignación de su mainframe. Después de la instalación, cargue sus datos y asígnelos a las tablas de datos maestros adecuadas para habilitar la generación de informes.

## Instalación de componentes

**Aplicaciones CT: ordenadores centrales**

El componente Mainframes forma parte del módulo Aplicaciones y servicios de transparencia de costes. Se utiliza para comprender el TCO de los mainframes y asignar los costes de los mainframes al objeto Aplicaciones.

**BI: Información sobre mainframes**

El componente BI-Mainframe Insights ofrece una mayor visibilidad del coste total de propiedad (TCO) y la utilización del mainframe, incluyendo un análisis detallado de los costes unitarios y el uso medido en millones de unidades de servicio (MSU), con desgloses entre las MSU de « GCP » y las MSU de « zIIP ».

**Nota:** Este componente está disponible en las plantillas **v120 y posteriores**.

**BI: Informes de Mainframe Insights NX (componente adicional)**

Este componente ofrece informes NX predefinidos basados en datos del mainframe para realizar análisis por aplicación, uso y periodos de tiempo.

Utiliza este componente cuando:

- Necesitas informes estándar de mainframe
- ¿Quieres analizar las tendencias de consumo y de costes?
- Necesitas informes de mainframe de forma regular

## Componentes previos necesarios

- CTF: Fuente de costes
- CTF- Torres de TI
- CT Apps: aplicaciones

## Fuentes comunes de datos

Los datos sobre el coste total de propiedad (TCO) de los mainframes suelen proceder de múltiples fuentes del entorno mainframe y de los sistemas empresariales. Las fuentes de datos comunes incluyen:

- **IBM IntelliMagic Visión:** Fuente principal de datos sobre la utilización de mainframes, incluyendo MSU de « GCP », MSU de « zIIP », almacenamiento asignado, almacenamiento utilizado, consumo de cargas de trabajo y métricas de uso de aplicaciones.
- Otras soluciones de rendimiento o telemetría para mainframes, como zPCA,, etc
- **Libro mayor:** Fuente de los costes reales del hardware, software, instalaciones y gastos de amortización del mainframe, clasificados por centro de costes y cuenta.
- **Sistemas de RR. HH.:** Costes laborales y plantilla para operaciones de mainframe, desarrollo y personal de soporte.
- **Sistemas de gestión de proveedores:** Costes de licencias de software para mainframe, contratos de mantenimiento y servicios externos.
- **Sistemas de gestión de activos:** inventario de hardware del mainframe, configuraciones e información sobre el ciclo de vida de los activos.
- **Cartera de aplicaciones:** nombres de aplicaciones, propietarios y asociaciones de unidades de negocio para la asignación de costes.

## Conjuntos de datos maestros

La solución Mainframe TCO requiere que se rellenen varias tablas de datos maestros con datos sobre los costes y el consumo del mainframe. Cargue los datos en estas tablas y asegúrese de que todos los campos obligatorios estén asignados correctamente.

**Datos maestros del mainframe:** consumo de MSU de GCP, consumo de MSU de zIIP, almacenamiento asignado, almacenamiento utilizado, categoría de carga de trabajo, tipo de carga de trabajo, línea de productos, nombre del producto y nombre de la aplicación de IBM IntelliMagic Vision.

Para obtener más información sobre la configuración y la instalación del TCO de Mainframe, haz clic [aquí](../reports/mainframe-config-guide.html)
