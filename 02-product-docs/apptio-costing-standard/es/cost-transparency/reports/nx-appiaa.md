---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Análisis de infraestructuras por aplicación"
breadcrumb:
  - "Costing Standard"
  - "Guía paso a paso de Report NX"
  - "Aplicaciones e informes de NX"
source_path: "cost-transparency/reports/nx-appiaa.html"
images:
  - "resources/images/ct_images/nx-appiaa.png"
  - "resources/images/ct_images/nx-appiaa1.png"
  - "resources/images/ct_images/nx-appiaa2.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Análisis de infraestructuras por aplicación

Utilice este informe para analizar el uso de los recursos de infraestructura en todas las aplicaciones, incluyendo la capacidad de procesamiento, el almacenamiento y la distribución del entorno, con el fin de identificar oportunidades de optimización para los recursos físicos, virtuales y en la nube.

Este informe está destinado a los siguientes perfiles:

- Administradores de infraestructuras
- Responsables de aplicaciones
- Controladores financieros de TI
- Arquitectos de la nube
- Planificadores de capacidad

## Elementos clave

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/nx-appiaa.png)

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/nx-appiaa1.png)

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/nx-appiaa2.png)

| Elemento | Descripción |
| --- | --- |
| Controles de filtro (1) | Cuatro filtros te permiten filtrar el informe por nombre de la aplicación, tipo de aplicación, responsable de TI de la aplicación y familia de aplicaciones. |
| Gráficos de análisis del entorno de las infraestructuras (2) | Tres gráficos de barras horizontales muestran las horas de funcionamiento de los servidores, los gastos operativos totales y los gastos operativos por hora por entorno, como producción, pruebas, desarrollo y recuperación ante desastres. |
| Tabla de detalles del entorno (3) | Esta tabla muestra las métricas de infraestructura por entorno, incluyendo las horas de servidor, el porcentaje por horas de servidor, los gastos de explotación y los gastos de explotación por horas de servidor. |
| Análisis informático por tabla de aplicaciones (4) | La tabla incluye columnas como el nombre de la aplicación, el responsable de TI de la aplicación, las horas de funcionamiento del servidor, el análisis del perfil de virtualización y el análisis del entorno. |
| Tabla de análisis de almacenamiento por aplicaciones (5) | Esta tabla incluye columnas como el nombre de la aplicación, el responsable de TI de la aplicación, el almacenamiento asignado, el análisis del nivel de almacenamiento y el análisis del entorno. |
| Análisis del servicio de asistencia técnica por aplicación (6) | En esta sección se muestran los datos del servicio de asistencia por aplicación, siempre que estén disponibles. |

## Preguntas y respuestas

- ¿Qué aplicaciones consumen más recursos de infraestructura?
- ¿Cuánto cuesta ejecutar cada aplicación en la infraestructura?
- ¿Qué porcentaje de la infraestructura corresponde a la física, a la virtual y a la nube?
- ¿Qué aplicaciones consumen más recursos de producción, de pruebas y de desarrollo?
- ¿Cuál es el coste por hora de servidor para cada tipo de infraestructura?
- ¿Qué aplicaciones consumen más espacio de almacenamiento y en qué niveles de almacenamiento?
- ¿Estamos sobredimensionando la infraestructura para los entornos que no son de producción?

## Acciones recomendadas

- Revisa las aplicaciones con un elevado número de horas de servidor en la nube pública para asegurarte de que se utilizan instancias reservadas o planes de ahorro con el fin de optimizar los costes.
- Revisa las aplicaciones con un alto porcentaje de infraestructura física para identificar aquellas que sean candidatas a la migración a la virtualización o a la nube.
- Consulte el gráfico « OpEx s por hora» para averiguar qué tipos de infraestructura son los más costosos y dar prioridad a las medidas de optimización en esos ámbitos.
- Filtra por «Responsable de TI de la aplicación» para asignar objetivos de reducción de costes de infraestructura a equipos específicos.
- Revisa las columnas de «Análisis del entorno» para identificar las aplicaciones que tienen un exceso de recursos asignados en los entornos de prueba o desarrollo en comparación con el de producción.
- Comprueba el análisis de niveles de almacenamiento para asegurarte de que el almacenamiento de alto rendimiento de nivel 1 solo se utilice cuando sea necesario, trasladando los datos a niveles más económicos siempre que sea posible.
- Haga clic en los nombres de las aplicaciones para profundizar en el consumo detallado de la infraestructura e identificar oportunidades específicas de optimización.
