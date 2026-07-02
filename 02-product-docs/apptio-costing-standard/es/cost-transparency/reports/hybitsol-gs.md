---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Impacto del TCO de la TI híbrida Introducción"
breadcrumb:
  - "Costing Standard"
  - "Otras soluciones"
  - "Impacto del TCO de la TI híbrida"
source_path: "cost-transparency/reports/hybitsol-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Impacto del TCO de la TI híbrida Introducción

La solución Hybrid IT TCO Impact ayuda a las organizaciones a comprender el impacto financiero de las migraciones de aplicaciones en entornos locales, de nube privada y de nube pública. Permite comparar el TCO, los costes unitarios y los volúmenes antes y después de la migración, y ofrece información sobre los grupos de costes y las torres de TI que impulsan el cambio. Esta solución permite validar los casos de negocio de migración basándose en datos y realizar un seguimiento financiero continuo de las transformaciones de TI híbridas.

## Instalación de componentes

Para habilitar el impacto del TCO de la TI híbrida, instale los siguientes componentes en el orden indicado. Antes de la instalación, asegúrese de **que la versión de los componentes** en **la configuración del proyecto** esté temporalmente establecida en **la versión 120**. Después de la instalación, revierta la versión para evitar indicadores de actualización innecesarios.

1. **Entorno de trabajo de aplicaciones**

   Permite el enriquecimiento de los metadatos de las aplicaciones necesarios para el análisis del impacto del coste total de propiedad (TCO) de la TI híbrida.

   Los campos obligatorios incluyen:

   **Alojado en** (local, nube privada, nube pública)

   **Objetivo de inversión de la aplicación** (mantener, retirar, migrar, invertir)
2. **Impacto del TCO de la TI híbrida**

   Instala el marco central, incluyendo bancos de trabajo de migración, tablas editables, métricas y modelos. También implementa informes intermedios que se utilizan para capturar y congelar las métricas de referencia de la aplicación antes de la migración.
3. **Informes sobre el impacto del coste total de propiedad (TCO) de la TI híbrida**

   Instala los informes para el usuario final, que abarcan desde vistas resumidas a nivel ejecutivo hasta análisis detallados a nivel de aplicación de los beneficios de la migración y los factores que influyen en los costes.

   Nota: Estos componentes están disponibles con las plantillas v120 o superior

## Requisitos previos

Debe tener instalados los siguientes componentes antes de configurar Hybrid IT TCO Impact:

• CTF: fuente de costes

• Torres CTF-IT

• Aplicaciones CT: aplicaciones

## Fuentes comunes de datos

**Herramientas de gestión de cartera de aplicaciones (APM)** : Proporcione metadatos de aplicaciones, incluyendo identificadores de aplicaciones, propiedad, estado del ciclo de vida y objetivos de inversión (mantener, migrar, retirar, invertir).

## Conjuntos de datos

La solución Hybrid IT TCO Impact instala y utiliza los siguientes conjuntos de datos clave:

• Datos maestros de aplicaciones

• Migración de aplicaciones

• Relaciones de migración de aplicaciones

• Aplicaciones migradas (sin procesar, grupo de costes, torre de TI)

Estos conjuntos de datos permiten comparar los costes antes y después, agrupar migraciones y analizar variaciones.

## Descripción general de la configuración

Para activar los informes sobre el impacto del TCO de la TI híbrida, siga estos pasos generales:

- **Establecer el TCO de referencia**
- Asegúrese de que el coste total de propiedad, los costes unitarios y los volúmenes de uso se calculen para todas las aplicaciones actuales utilizando asignaciones estándar de ATUM. Rellene los metadatos necesarios en el Applications Workbench.
- **Capturar metadatos de migración**
- Para las aplicaciones marcadas como **Migrar**, registre la estrategia de migración, el estado de la migración, los ID de las aplicaciones de destino y el momento de la migración utilizando el Application Migration Workbench.
- **Congelar métricas previas a la migración**
- Cuando el estado de la migración se establezca en **«Hecho»**, capture una instantánea del promedio de los últimos doce meses del TCO, los volúmenes y los costes unitarios de la aplicación migrada utilizando conectores de enlace de datos de Apptio a Apptio.
- **Modelar los costes previos y posteriores a la migración**
- Configure métricas modeladas para el coste previo a la migración, el coste posterior a la migración y el recuento de aplicaciones posterior a la migración para permitir una comparación equitativa entre los grupos de costes y las torres de TI.

Para obtener más información sobre la configuración y el funcionamiento de Hybrid IT TCO Impact, consulte [la Guía de configuración](hybrid-it-tco-config.html) de Hybrid IT TCO Impact.
