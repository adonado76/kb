---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Ruta de incorporación para administradores y analistas"
breadcrumb:
  - "Billing"
  - "Guía de formación basada en funciones"
source_path: "boit/billing/role-based-tg/op-admin.html"
images:
  - "resources/images/boit_images/p2-admin.png"
  - "resources/images/boit_images/p3-admin.png"
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Ruta de incorporación para administradores y analistas

Esta es la ruta de formación más intensiva y debe estar estructurada, no ser improvisada.

## Fase 1: Fundamentos

**Objetivo** : Comprender el panorama antes de tocar cualquier configuración.

**Temas** :

- Conceptos de facturación y relación con el cálculo de costes.
- Ediciones y capacidades (Essentials frente a Standard).
- Arquitectura y dependencias (Sección 6).
- Entornos y gestión de lanzamientos (Sección 7).
- Resumen del ciclo de facturación (Sección 9).

**Actividades** :

- Recorrido por el entorno en vivo o de ensayo:
  - Mostrar dónde se encuentran los informes de facturación.
  - Mostrar flujos de datos de alto nivel y diagramas de modelos.

## Fase 2: Datos e informes

**Objetivo** : Comprender cómo se muestran los datos en los informes antes de editar los modelos.

**Temas** :

- Requisitos de datos y patrones de integración (Sección 8).
- Trabajar con informes de facturación (Sección 10).
- Recetas básicas de casos de uso (Sección 15) para:
  - PxQ showback.
  - Contracargo con diarios.
  - Investigación sobre la tasa unitaria.

**Actividades** :

- Ejercicios prácticos:
  - Filtrar y exportar informes clave de facturación.
  - Compare los resultados de facturación con casos de prueba conocidos o facturas anteriores.
  - Realizar una investigación sobre la tarifa unitaria de un servicio.

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/p2-admin.png)

Fig. n.º: Informe detallado de facturas en Billing Standard con el cursor sobre el botón Exportar

## Fase 3: Cambios en la configuración y el modelo

**Objetivo** : Realizar cambios de forma segura en «En desarrollo» y comprender su impacto.

**Temas** :

- Configuración de Billing Essentials y/o Billing Standard (Secciones 11 y 12).
- Estructura de componentes y tablas clave.
- Cómo revisar, editar y registrar documentos en TBM Studio.
- Cómo fluyen las compilaciones desde «En desarrollo» a «En fase de pruebas» y a «En producción».

**Actividades** :

- Ejercicios guiados en desarrollo:
  - Añadir o modificar una oferta y su tarifa.
  - Cargar el consumo de muestras y ejecutar modelos.
  - Validar el efecto en una compilación de prueba similar a Staging.

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/p3-admin.png)

Fig. n.º: En TBM Studio, edición de fórmulas en la tabla de datos maestros de asignación de unidades de negocio

## Fase 4: Control del ciclo de facturación

**Objetivo** : Los administradores y analistas pueden ejecutar el ciclo completo y gestionar los problemas habituales.

**Temas** :

- Libro de operaciones mensual detallado basado en la Sección 9 y la Sección 16.
- Patrones de control de calidad y gestión de excepciones.
- Comunicaciones a los propietarios del servicio y al departamento financiero en cada ciclo de facturación.

**Actividades** :

- Sombra, luego lidera, uno o más ciclos de facturación reales:
  - Primero con un guía experimentado, luego de forma independiente con controles aleatorios.
