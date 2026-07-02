---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Seguimiento del tiempo: Introducción"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso financiero"
  - "Plantilla"
source_path: "cost-transparency/it-financials/tt-getstar.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Seguimiento del tiempo: Introducción

El seguimiento del tiempo se habilita mediante el componente **CTF – Seguimiento del tiempo**. Este componente asigna los costes laborales utilizando informes de tiempo a nivel de proyecto y actividad, y se integra con el modelo de costes estándar de Costing.

El seguimiento del tiempo debe utilizarse cuando se requiere un informe detallado del tiempo para calcular los costes de mano de obra de un proyecto.

Nota: Dependiendo del caso de uso, los clientes suelen utilizar **el seguimiento del tiempo o las unidades de trabajo**, ya que el uso de ambos puede requerir una personalización adicional del modelo.

**CTF: Seguimiento del tiempo**

El componente CTF-Time Tracking asigna los costes laborales basándose en los informes de tiempo a nivel de proyecto y actividad. Permite realizar un análisis detallado del esfuerzo y el coste de mano de obra del proyecto.

- Asignar los costes laborales a proyectos y actividades operativas
- Apoyar las revisiones operativas mensuales, trimestrales y anuales
- Analizar el coste laboral y el esfuerzo del proyecto

## Requisitos previos

- CTF: Fuente de costes
- CTF- Trabajo

Este componente afecta tanto a las métricas de coste como a las de CapEx del modelo y requiere que se rellene la tabla **de datos maestros de seguimiento del tiempo**.

El componente de seguimiento del tiempo no introduce ningún informe adicional listo para usar. Los datos laborales basados en el tiempo se utilizan en los informes laborales y de proyectos existentes para mejorar la asignación de los costes laborales y el análisis a nivel de proyecto

## Conjunto de datos maestros

- **Datos maestros de seguimiento del tiempo**
- Contiene datos temporales a nivel de proyecto y actividad que se utilizan para asignar los costes laborales a los proyectos y las actividades operativas.
