---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Pivote rápido"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "ApptioIBM Report Studio (Nuevo)"
  - "Componentes"
source_path: "studio/report-studio/components/rs-quick-pivot.html"
images:
  - "resources/images/studio_images/quick-pvt.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Pivote rápido

El pivote rápido funciona de manera similar a una tabla dinámica de Excel, lo que permite a los usuarios cambiar dinámicamente la forma en que se agrupan y resumen los datos en una tabla.

## Cuándo utilizar Quick Pivot

Utilice Quick Pivot cuando desee:

- Agrupar datos por diferentes dimensiones sobre la marcha
- Compare métricas entre desgloses alternativos

## Añadir un pivote rápido al informe

1. Añadir un pivote rápido desde el panel Componentes de la barra de herramientas
2. Haga clic en el pivote rápido para habilitar los paneles Datos y Formato.
3. Panel de datos
   1. Seleccione el objeto modelo de la lista desplegable
   2. Arrastra las dimensiones desde el Explorador de dimensiones a la sección de pivotes del panel de datos
4. Panel de formato
   1. Propiedades generales: consulte [Propiedades de los componentes.](components.html#abt-comp__comprop)

Ejemplo: Pivote rápido

![pivote rápido](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/quick-pvt.png)

Quick Pivot admite fórmulas personalizadas y dimensiones de fórmulas. Para obtener más información, consulte [Fórmulas personalizadas.](../create-first/custom-formula.html "Las fórmulas personalizadas (también denominadas dimensiones de fórmula) le permiten definir nuevas dimensiones calculadas utilizando campos existentes en su modelo de datos. Esto permite realizar análisis más profundos y obtener información más detallada sin necesidad de realizar cambios en el conjunto de datos o el esquema subyacentes.")
