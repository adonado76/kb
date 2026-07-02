---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Propiedades comunes de los gráficos"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes del informe: Gráficos"
source_path: "studio/new-uc/reference/report-studio-reference/common-charts.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Propiedades comunes de los gráficos

Todos los gráficos comparten un conjunto común de propiedades configurables a las que se accede a través del cuadro de diálogo «Propiedades». Selecciona un gráfico y accede a sus propiedades mediante el icono «Propiedades» de la pestaña «Autor», el menú «Acciones» (el pequeño triángulo situado en el encabezado del gráfico) o haciendo clic con el botón derecho del ratón sobre el gráfico.

**Propiedades de la pestaña «Gráfico»**

|  |  |
| --- | --- |
| **Propiedad** | **Descripción** |
| Etiqueta del eje X | Selecciona la columna de origen para los valores del eje X. |
| Etiqueta de valor Y | Selecciona la columna de origen para los valores del eje Y. |
| Escala del eje Y | Selecciona la escala lineal o logarítmica para el eje Y. |
| Especificaciones de color | Introduce cadenas de formato de color para personalizar los colores de las métricas (por ejemplo, «Coste=azul;Presupuesto=verde»). |
| Formato del número de gráfico | Introduce un formato para los números de los ejes (por ejemplo, «#,###» para el separador de miles). |
| Prefijo del número de gráfico | Texto que aparece delante de los números (por ejemplo, «$» para los dólares). |
| Sufijo del número de gráfico | Texto que aparece después de los números (por ejemplo, «M» para millones). |
| Mostrar valores de datos | Mostrar los valores de los datos de cada punto del gráfico. |
| Ubicación de leyenda | Selecciona la orientación de la leyenda: Norte, Sur, Este, Oeste u Oculta. La opción predeterminada es «Sur». |
| Ocultar líneas de cuadrícula | Elimina las líneas de cuadrícula horizontales y verticales del gráfico. |
| Incluir el cero en el eje Y | Forzar que el eje Y comience en 0 en lugar de ajustarse automáticamente. |

**Propiedades de la pestaña «Datos»**

|  |  |
| --- | --- |
| **Propiedad** | **Descripción** |
| Número máximo de filas | Limita los elementos que se muestran. En los gráficos de barras: número de barras. En gráficos circulares: número de sectores. Artículos sobrantes agrupados en «Otros». |
| Incluir columnas\* | Limitar las columnas mostradas a las seleccionadas (solo gráficos antiguos). |
| Excluir columnas\* | Permitir todas las columnas excepto las seleccionadas (solo en gráficos heredados). |
| Mostrar filas con todos los valores a cero\* | Anular el comportamiento predeterminado para mostrar las filas con valor cero (solo en gráficos heredados). |
| Conjunto de datos de pivote\* | Intercambiar los ejes X e Y en el gráfico (solo en gráficos antiguos). |

*\* Solo gráficos antiguos*

**Propiedades de la pestaña «General»**

|  |  |
| --- | --- |
| **Propiedad** | **Descripción** |
| Nombre | El título que aparece en el encabezado del gráfico (cuando la opción «Mostrar encabezado» está activada). |
| Título | Información adicional que aparece junto al gráfico. Se permite el uso de HTML (sin enlaces por motivos de seguridad). |
| Posición del pie de foto | Coloca el pie de foto: arriba, abajo, a la izquierda, a la derecha u oculto. |
| Mostrar borde | Aplica un borde al gráfico. Los bordes ocultos aparecen al pasar el cursor por encima en el modo de edición. |
| Mostrar encabezado | Mostrar el nombre del gráfico como encabezado. Por defecto, está activado. |
| Título del resumen | Ajusta los nombres largos de los gráficos para que quepan en el ancho del gráfico. |

**Propiedades de la pestaña «Avanzadas»**

|  |  |
| --- | --- |
| **Propiedad** | **Descripción** |
| Periodo de datos | Fija el gráfico a un periodo de tiempo concreto, independientemente de la fecha seleccionada para el informe. |
| Ocultar aviso sobre hidratación | Omitir las advertencias cuando un gráfico muestre deliberadamente datos procedentes de varias fuentes. |
| Actualización automática al finalizar el cálculo | Actualizar automáticamente el gráfico cuando finalicen los cálculos en segundo plano. |
| Acortar automáticamente los nombres de las columnas | Mostrar solo la parte de los nombres de las columnas que se encuentra después del separador de puntos. |

**Tema principal:** [Componentes del informe: Gráficos](../../../../studio/new-uc/reference/report-studio-reference/report-component-charts.html)
