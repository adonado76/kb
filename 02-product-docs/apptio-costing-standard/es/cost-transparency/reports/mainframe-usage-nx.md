---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Uso de mainframes"
breadcrumb:
  - "Costing Standard"
  - "Guía paso a paso de Report NX"
  - "Informes de mainframes NX"
source_path: "cost-transparency/reports/mainframe-usage-nx.html"
images:
  - "resources/images/ct_images/mf-nx-usage2.png"
  - "resources/images/ct_images/nx-mf-usage1.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Uso de mainframes

Utilice este informe para comprender el consumo de los procesadores, evaluar el uso por categorías y periodos de tiempo, e identificar tendencias que sirvan de apoyo a la planificación de la capacidad y la optimización de la carga de trabajo. Aplica filtros y vistas disponibles para centrarte en los datos relevantes para tu análisis.

Este informe está destinado a los siguientes perfiles:

- Planificadores de capacidad
- Analistas de rendimiento
- Responsables de operaciones de TI
- Arquitectos de infraestructuras

## Elementos clave

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/nx-mf-usage1.png)

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/mf-nx-usage2.png)

| Elemento | Descripción |
| --- | --- |
| Controles de filtro (1) | Los cinco filtros te permiten filtrar el informe por nombre de la línea de productos, nombre del producto, nombre del complejo de procesadores, ubicación y entorno. |
| Pestañas de consumo de MSU (2) | Dos pestañas te permiten alternar entre las vistas de consumo de MSU de GCP y zIIP. |
| Selector de dimensiones (3) | Utiliza este menú desplegable para seleccionar qué dimensión deseas ver en los gráficos, como por ejemplo, «Nombre de la línea de productos». |
| GCP gráfico por categorías (4) | Este gráfico de barras horizontales muestra el consumo de MSU de GCP por categoría, como tarjetas de crédito, fidelización de clientes, préstamos, gestión patrimonial y soluciones de suscripción. |
| GCP gráfico de tendencias (5) | Este gráfico de barras apiladas muestra las tendencias de consumo de MSU de GCP a lo largo del tiempo por categoría, con datos mensuales desde agosto de FY2021 hasta agosto de FY2021. |
| Pestañas con detalles de la varianza de la MSU (6) | Hay tres pestañas que te permiten ver los datos de variaciones por periodo: « MoM » (mes a mes), « QoQ » (trimestre a trimestre) y « YoY » (año a año). |
| Tabla de detalles de la varianza de la MSU (7) | Esta tabla muestra datos de variación de MSU con columnas para el nombre de la línea de productos, GCP los valores de MSU y MoM GCP las variaciones porcentuales de MSU a lo largo de varios meses. La tabla incluye una fila de totales y controles de paginación. |

## Preguntas y respuestas

- ¿Qué líneas de productos consumen más capacidad del procesador?
- ¿Cómo evoluciona el consumo de los procesadores a lo largo del tiempo en las distintas categorías?
- ¿Cuáles son las variaciones intermensuales e interanuales en el consumo de MSU?
- ¿En qué áreas se observa un aumento o una disminución en el uso del procesador?
- ¿Cómo se distribuye la carga de trabajo entre los procesadores « GCP » y « zIIP »?
- ¿Existen patrones estacionales o anomalías en el consumo de los procesadores?
- ¿Qué líneas de productos podrían beneficiarse de la optimización de la carga de trabajo o de cambios en el tipo de procesador?

## Acciones recomendadas

- Cambia entre las pestañas « GCP » y « zIIP » para comparar el consumo entre los distintos tipos de procesadores.
- Revisa los detalles de las variaciones para comprender los cambios respecto al mes anterior y al mismo periodo del año anterior.
- Identificar las líneas de productos que registran un aumento significativo del consumo e investigar las causas.
- Filtra por línea de productos o entorno para centrarte en áreas específicas de interés.
- Analizar las tendencias para prever las necesidades futuras de capacidad y planificar las inversiones en infraestructura.
- Exportar datos de uso para compartirlos con los equipos de planificación de la capacidad y de operaciones.
- Compara el uso de GCP y zIIP para identificar las cargas de trabajo que podrían migrarse a procesadores especializados.
