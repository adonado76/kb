---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Servicio de asistencia técnica: Introducción"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso de infraestructura"
  - "Centro de servicio al usuario"
source_path: "cost-transparency/infra-use-cases/sd-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Servicio de asistencia técnica: Introducción

## Introducción: descripción general de los costes del servicio de asistencia técnica

La función de resumen de costes del servicio de asistencia técnica permite a las organizaciones comprender y asignar los costes de asistencia técnica y soporte entre aplicaciones, servicios y unidades de negocio en función del volumen de tickets, la prioridad, el impacto y el esfuerzo. Al vincular los datos de actividad del servicio de asistencia técnica con los datos de costes financieros, este componente proporciona transparencia sobre el coste real de la prestación de asistencia y ayuda a las organizaciones a gestionar la eficiencia, la demanda y los factores que influyen en los costes del servicio de asistencia técnica de forma más eficaz.

Este componente es un requisito previo para obtener informes operativos y analíticos más detallados a través de Service Desk Insights.

**Instalación de componentes**

Aplicaciones CT – Servicio de asistencia técnica

El componente CT Apps– Service Desk proporciona la estructura de datos fundamental necesaria para la asignación de costes del servicio de asistencia técnica. Registra las actividades relacionadas con la gestión de incidentes y solicitudes, incluyendo el volumen de tickets, las prioridades, los niveles de impacto y el tiempo dedicado a resolver los problemas.

**Prerrequisito**

Debe instalar los siguientes componentes antes de instalar el componente Service Desk:

- CTF – Fuente de costes
- CTF – Trabajo
- CTF – Torres de TI

**Fuentes comunes de datos**

Los datos sobre los costes y las actividades del servicio de asistencia técnica suelen proceder de una combinación de sistemas financieros y plataformas de gestión de servicios de TI. Los datos sobre costes y presupuestos suelen proceder del libro mayor, mientras que el volumen de tickets, la gravedad, la prioridad y el esfuerzo de resolución se obtienen de ITSM y de herramientas de soporte. El nivel de detalle disponible depende de los datos capturados en estos sistemas y asignados a los datos maestros del servicio de asistencia técnica.

**Conjuntos de datos**

Para habilitar los informes de resumen de costes del servicio de asistencia técnica, cargue los datos de entrada del servicio de asistencia técnica y asígnelos a las tablas de datos maestros proporcionadas con el componente.

Los datos maestros de tickets contienen la lista completa de tickets del servicio de asistencia técnica, incluyendo el impacto, la prioridad, las aplicaciones o servicios asociados, los datos del responsable y el tiempo dedicado a resolver los problemas.

Al instalar el componente CT Apps – Service Desk, se crea un grupo de tablas Service Desk con una tabla modelo Tickets y una tabla Datos maestros de tickets. Tras mapear los datos, los costes del servicio de asistencia se asignan desde IT Resource Towers a los tickets dentro del modelo de costes, lo que permite una atribución y un informe precisos de los costes de asistencia.

## Introducción: información y optimización del servicio de asistencia técnica

Service Desk Insights & Optimization se basa en el modelo de costes básico del servicio de asistencia técnica para ofrecer un análisis operativo y financiero más profundo del rendimiento del servicio de asistencia técnica. Esta capacidad proporciona visibilidad sobre el volumen de tickets del servicio de asistencia técnica, los costes y la eficiencia en todas las ubicaciones, prioridades y categorías, lo que permite a las organizaciones pasar del seguimiento básico de costes a la optimización del servicio basada en datos

Esta capacidad se basa en **CT Apps,** el componente Service Desk

**Instalación de componentes**

**BI: información sobre el servicio de asistencia técnica**

Service Desk Insights se ofrece a través del componente **BI – Service Desk Insights**.

**Prerrequisito**

Antes de instalar el componente Service Desk Insights, asegúrese de que los siguientes componentes previos estén instalados y configurados en el orden correcto:

- CTF: Fuente de costes
- CTF- Torres de TI
- CT Apps - Servicio de asistencia técnica
