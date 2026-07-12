---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Itinerarios de aprendizaje para desarrolladores"
breadcrumb:
  - "TBM Studio"
  - "Itinerarios de aprendizaje (basados en funciones)"
source_path: "studio/new-uc/learning-path/lp-dev.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Itinerarios de aprendizaje para desarrolladores

**Objetivo:** Integrar TBM Studio con los sistemas de la empresa y ampliar las capacidades de la plataforma

**A quién va dirigido:** desarrolladores de software, especialistas en integración, desarrolladores de ETL y cualquier persona que cree flujos de datos automatizados o integraciones personalizadas con TBM Studio

## Introducción (30 minutos)

**Lo que** aprenderás: Arquitectura de integración y cuándo utilizar los distintos métodos de integración

**Objetivos de aprendizaje:**

- Comprender la arquitectura de integración de TBM Studio
- Descubre los métodos de autenticación y la seguridad
- Decide cuándo utilizar la API, las tablas publicadas o DataLink
- Comprender los patrones de entrada y salida de datos
- Revisar los puntos de integración disponibles

**Temas que hay que completar:**

1. **Arquitectura de integración** (10 min) *→ Sección 4.1, 4.2*
2. **Métodos de autenticación** (10 min) *→ Sección 5.5*
3. [Integración de API](../howtoguides/integrate-extend/api-integration.html) (10 min)

**Requisitos previos:** Conocimientos de programación en cualquier lenguaje; comprensión de las API REST

## Habilidades básicas (3 horas)

**Lo que** aprenderás: Implementar la autenticación de la API, cargar y descargar datos, configurar tablas publicadas

**Objetivos de aprendizaje:**

- La autenticación de la API se ha configurado correctamente
- Subir datos de costes a través de la API (automatizar la carga de datos)
- Descargar datos a través de la API o de tablas publicadas
- Gestionar los errores e implementar la lógica de reintento
- Configurar las tablas publicadas para la integración de informes
- Probar y validar integraciones

**Temas que hay que completar:**

1. Configuración de la autenticación de la API (30 min) *→ Sección 5.5*
2. [Subir datos a través de la API](../howtoguides/integrate-extend/upload-data-via-api.html) (60 min)
3. [Descargar datos a través de la API](../howtoguides/integrate-extend/download-data-api.html) (45 min)
4. Configurar tablas publicadas (45 min) *→ Sección 3.5.2*

**Requisitos previos:** haber completado el curso básico y haber configurado el entorno de desarrollo

**Tiempo estimado para la práctica:** suma entre 2 y 3 horas para crear y probar las integraciones

## Avanzado (5 horas)

**Lo que** aprenderás: Dominar ApptioScript,, implementar integraciones complejas, gestionar casos extremos y crear soluciones aptas para producción

**Objetivos de aprendizaje:**

- Escribe a ApptioScript para solicitar cálculos y lógica personalizados
- Implementar patrones de fórmulas complejos
- Crear una integración de « ServiceNow » u otras integraciones empresariales
- Gestiona los errores de forma adecuada mediante una lógica de reintento
- Optimizar el rendimiento de la API
- Implementar la supervisión de la producción y el sistema de alertas
- Crear soluciones de integración sólidas y fáciles de mantener

**Temas que hay que completar:**

1. ApptioScript Fundamentos (90 min) *→ Sección 5.6*
2. Patrones de fórmulas complejas (60 min) *→ Sección 5.4, 5.6*
3. [Integración de sistemas empresariales](../howtoguides/integrate-extend/api-integration.html) (90 min)
4. [Gestión de errores y lógica de reintentos (45 min)](../howtoguides/integrate-extend/handle-api-errors.html)
5. [Optimización del rendimiento](../admin/performance-optimize.html) (30 min)
6. [Patrones de integración de la producción (45 min)](../howtoguides/integrate-extend/htg-use-common-pattern.html)

**Requisitos previos:** haber completado el curso de «Habilidades básicas» y tener experiencia con sistemas de producción

## Retos habituales

- **Errores de autenticación:** comprueba la validez de la clave API y los permisos
- **Errores de validación en la carga:** revisa el formato de los datos y comprueba las asignaciones de columnas
- **Limitación de velocidad:** implementar retrasos y operaciones por lotes
- **Incoherencias en los datos:** añadir lógica de conciliación y validar antes de la carga
- **Problemas de rendimiento:** operaciones por lotes, optimizar el tamaño de los datos
