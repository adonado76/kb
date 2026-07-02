---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Introducción al TCO de la IA"
breadcrumb:
  - "Costing Standard"
  - "Otras soluciones"
  - "Costo total de propiedad de la IA"
source_path: "cost-transparency/reports/aitcosol-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Introducción al TCO de la IA

La solución AI TCO & Usage permite a las organizaciones obtener una visibilidad clara y justificable del coste total de propiedad y uso de la IA en todos los modelos, soluciones y unidades de negocio. Está diseñado para apoyar la adopción responsable de la IA mediante la combinación de datos financieros, operativos y de uso en un único marco analítico. Antes de la implementación, las organizaciones deben evaluar si implementar esta solución dentro de un proyecto existente o crear un proyecto específico para el TCO y el uso de la IA, en función de las necesidades de gobernanza, separación de datos y generación de informes.

## Instalación de componentes

La solución AI TCO & Usage se introduce a través de cuatro componentes, instalados en una secuencia priorizada. Dos componentes están diseñados específicamente para el TCO y el uso de la IA, y dos son componentes existentes que deben actualizarse (o deben añadirse cambios a los datos maestros) para habilitar la funcionalidad específica de la IA.

**Costo total de propiedad y uso de la IA**

El componente **AI TCO & Usage** debe instalarse en primer lugar, ya que establece los conjuntos de datos maestros, modelos, métricas y bancos de trabajo específicos de la IA necesarios para calcular los resultados de costes y uso de la IA.

**Informe sobre el coste total de propiedad y el uso de la IA**

Instale el componente **AI TCO & Usage Reporting**, que proporciona la recopilación de informes de IA, incluido el informe principal AI TCO & Usage y el informe AI Cost Model utilizado para la trazabilidad de la asignación.

Nota: Estos componentes están disponibles con las plantillas v120 o superior

**Informes de AI sobre el coste total de propiedad (TCO) y el uso de NX (componente adicional)**

Ofrece informes NX predefinidos basados en datos de costes y uso de la IA para el análisis de servicios, cargas de trabajo y periodos de tiempo.

Utiliza este componente cuando:

- Necesitas informes estándar sobre los costes y el uso de la IA
- ¿Quieres analizar las tendencias en cuanto a costes y consumo?
- Necesitas informes de IA sistemáticos

## Prerrequisito

**CTF: fuente de costes**

Si este componente ya está instalado, debe actualizarse (los campos se añaden automáticamente al actualizar) o configurarse para admitir mejoras específicas de IA. Esto incluye añadir los campos **«Porcentaje de coste de IA»** y **«Importe de IA»** a los datos maestros de fuentes de costes, lo que permite una atribución precisa de los costes de IA y la visibilidad del gasto en IA como porcentaje del gasto total en TI.

**Aplicaciones de TC: servicios**

Del mismo modo, si este componente ya está instalado, debe actualizarse (los campos se añaden automáticamente al actualizar) o configurarse para admitir mejoras específicas de IA. Esto incluye **añadir la clasificación de soluciones de IA, el tipo de solución de IA y el recuento de usuarios de IA**, lo que amplía los servicios empresariales con atributos específicos de la IA. Estos campos son esenciales, ya que los informes de IA se generan a partir de los servicios empresariales marcados como soluciones de IA.

## Fuentes comunes de datos

Los datos sobre el coste total de propiedad y el uso de la IA suelen proceder de una combinación de plataformas de facturación en la nube, proveedores de servicios de IA y sistemas internos de la empresa. Los proveedores de servicios en la nube suministran la infraestructura y la plataforma de IA, incluidos los servicios informáticos, de almacenamiento y de IA gestionados. Los proveedores de modelos y plataformas de IA aportan métricas de uso, como el consumo de tokens, las solicitudes de inferencia, las licencias y los cargos por suscripción. Los sistemas laborales y de proveedores proporcionan los costes de personal y servicios externos asociados con el desarrollo, las operaciones y la gobernanza de la IA. Los metadatos de los servicios empresariales y las jerarquías organizativas se utilizan para asociar las soluciones de IA con las aplicaciones, los servicios y las unidades de negocio consumidoras, lo que permite realizar un análisis integral de los costes y el uso de la IA.

**Conjuntos de datos**

La solución introduce conjuntos de datos maestros específicos para IA a través del componente AI TCO & Usage y amplía los datos maestros existentes de Cost Source y Business Services para dar soporte a la atribución de costes de IA, el seguimiento del uso y el análisis a nivel de solución. La configuración se basa en completar los porcentajes de coste de IA, los atributos de la solución de IA y los campos relacionados con el uso para permitir un modelado y una generación de informes precisos.

**Para obtener más información sobre cómo configurarlo, vaya** [aquí.](ai-tco-configguide.html)
