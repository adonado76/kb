---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Configuración del periodo"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Propiedades de informe"
source_path: "studio/new-uc/reference/report-studio-reference/timeperiod-config.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configuración del periodo

La configuración del intervalo de tiempo determina qué periodos de datos ven los usuarios al consultar los informes. Estos ajustes interactúan con la configuración de tiempo a nivel de proyecto y afectan a los datos que se muestran en tablas, gráficos e indicadores clave de rendimiento (KPI).

**Herencia de tiempos a nivel de proyecto**

Los informes heredan la configuración del periodo de tiempo de la configuración del proyecto. Los siguientes ajustes del proyecto afectan a todos los informes:

|  |  |
| --- | --- |
| **Contexto del proyecto** | **Repercusión en los informes** |
| Período predeterminado | El periodo de tiempo que se muestra a los usuarios cuando abren un informe por primera vez. Por lo general, se establece en el último ejercicio cerrado. Los usuarios pueden anular esta selección mediante el selector de hora. |
| Definición de ejercicio fiscal | Determina la estructura del calendario fiscal (por ejemplo, enero-diciembre, octubre-septiembre, federal). Influye en cómo se etiquetan y agrupan los periodos en los informes de tendencias. |
| Periodo de inicio y finalización del proyecto | Limita el intervalo de fechas disponibles. Los datos que se encuentran fuera de este rango no se calculan, lo que mejora el rendimiento en modelos de gran tamaño. |
| Periodos cerrados | Los periodos marcados como cerrados siguen apareciendo en los informes, pero no se pueden modificar sus datos. Imprescindible para la gobernanza financiera y las pistas de auditoría. |

**Para configurar los ajustes de tiempo del proyecto:** ve a la pestaña «Proyecto» > «Ajustes de tiempo».

**Restricciones de fecha específicas del informe**

Los informes individuales pueden anular el periodo predeterminado del proyecto y limitar el momento en que son visibles.

**Fecha de entrada en vigor**

Limita la visibilidad del informe a las fechas comprendidas a partir de un periodo determinado. Esta función es útil para:

- Ocultar los informes que aún están en fase de desarrollo
- Publicación de informes en consonancia con los ciclos económicos
- Impedir el acceso a los informes antes de que los datos necesarios estén disponibles

**Para establecer la fecha más temprana aplicable:**

1. Echa un vistazo al informe
2. En la pestaña «Informe», haz clic en «Fecha de inicio»
3. En el cuadro de diálogo «Configurar la fecha más temprana aplicable», seleccione una fecha
4. Guarda y revisa el informe

Cuando los usuarios intentan consultar el informe antes de la fecha más temprana aplicable, aparece un mensaje en el que se les indica que el informe aún no está disponible, junto con un enlace para consultarlo en el primer periodo en el que esté disponible.

**Periodo de tiempo a nivel de componente**

Los componentes individuales del informe (tablas y gráficos) pueden tener su período de tiempo bloqueado independientemente del período actual del informe. Esto se configura mediante el campo «Período de datos» en las propiedades avanzadas de cada componente.

Ejemplos de casos de uso:

- Mostrar los datos comparativos del año anterior junto con los del período actual
- Mostrar el presupuesto de un periodo bloqueado concreto
- Crear gráficos de tendencias con fechas de inicio y fin fijas

**Tema principal:** [Propiedades del informe](../../../../studio/new-uc/reference/report-studio-reference/report-properties.html)
