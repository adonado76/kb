---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Gráficos de tendencia e indicadores de estado"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes del informe: Tablas"
source_path: "studio/new-uc/reference/report-studio-reference/sparklines-status-indi.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Gráficos de tendencia e indicadores de estado

**Columnas de minigráficos**

Los minigráficos muestran pequeñas líneas de tendencia que reflejan datos históricos y futuros en una sola celda.

**Sintaxis de la función «Sparkline»:**

`=SPARKLINE(past, future, column)`

|  |  |
| --- | --- |
| **Parámetro** | **Descripción** |
| pasados | Número de períodos para el análisis de tendencias retrospectivo. Debe ser un número positivo. |
| Futuro | Número de períodos para la extrapolación. Debe ser un número positivo. |
| columna | Nombre de la columna que contiene los datos que se van a representar gráficamente. |

**Ejemplo:** =SPARKLINE( 4,4,Cost ) muestra una línea de tendencia que abarca los 4 meses anteriores y los 4 meses siguientes de la columna «Coste».

**Columnas de indicadores de estado**

Los indicadores de estado utilizan iconos de colores para mostrar el estado de los valores de un solo vistazo.

**Sintaxis de la función «Icon»:**

`=Icon(["icon_type"], condition1, condition2, ...)`

|  |  |
| --- | --- |
| **Tipo de icono** | **Descripción** |
| círculos rojos | 2 estados: círculo rojo (expresión 1 verdadera), círculo rosa (expresión 2 verdadera) |
| 3colorcircles | 3 estados: círculos verdes, amarillos y rojos según las condiciones |
| (predeterminado) | Si no se especifica ningún tipo de icono, el valor predeterminado es «redcircles» |

Los valores que no coincidan con ninguna expresión recibirán el último icono del conjunto. Para ver todos los tipos de iconos disponibles, pasa el cursor por encima del nombre del cálculo en el cuadro de diálogo «Configuración del campo de valor».

**Indicadores de cálculo rápido**

Accede a ellos a través de la configuración de campos de valor (haz clic con el botón derecho del ratón en un valor en la configuración de componentes):

|  |  |
| --- | --- |
| **Indicador** | **Descripción** |
| Iconos de umbral | El icono rojo indica que se está por debajo del umbral, mientras que el icono verde indica que se está por encima del umbral. |
| Cero flechas | Flecha hacia arriba (>0), flecha lateral (=0), flecha hacia abajo (<0). |
| Tendencia del gráfico de tendencia | Pequeño gráfico de tendencias de los últimos seis meses. |

**Tema principal:** [Componentes del informe: Tablas](../../../../studio/new-uc/reference/report-studio-reference/report-component-table.html)
