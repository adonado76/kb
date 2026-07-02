---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Entornos de cálculo de costes: en desarrollo, ensayo y producción"
breadcrumb:
  - "Billing"
  - "Administración y operaciones"
  - "Entornos y gestión de lanzamientos"
source_path: "boit/billing/environ-relnmgmt/environments.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Entornos de cálculo de costes: en desarrollo, ensayo y producción

La facturación utiliza los **mismos entornos** que el proyecto de cálculo de costes en el que está instalada. Los cambios de configuración en Facturación se gestionan a través de los entornos del proyecto Costing: **En desarrollo**, **En fase de pruebas** y **En producción**.

Los entornos **no** son proyectos independientes. Son áreas ambientales diferentes del **mismo** proyecto.

## Entornos de cálculo de costes: en desarrollo, ensayo y producción.

Cada proyecto de cálculo de costes (y, por lo tanto, el contenido de facturación que contiene) tiene tres entornos principales:

- **En desarrollo**
  - Donde los administradores y analistas realizan cambios en la configuración.
  - Aquí se editan los componentes, modelos, conjuntos de datos e informes.
- **Transfiriendo**
  - Recibe compilaciones completadas de Desarrollo.
  - Se utiliza para control de calidad, comprobaciones de regresión y validación antes de la producción.
- **Producción**
  - El entorno en vivo para los usuarios finales.
  - Aquí solo se promocionan las compilaciones completadas y probadas.

Comportamientos clave:

- En Desarrollo es el único entorno en el que se revisan y editan los elementos.
- Cada registro genera una nueva compilación para «En desarrollo», y la plataforma crea automáticamente la compilación correspondiente para «Puesta en escena».
- La producción solo recibe compilaciones que se promocionan explícitamente.
