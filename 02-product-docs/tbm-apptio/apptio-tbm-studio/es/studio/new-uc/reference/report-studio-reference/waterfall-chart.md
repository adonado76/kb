---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Gráficos en cascada"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes del informe: Gráficos"
source_path: "studio/new-uc/reference/report-studio-reference/waterfall-chart.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Gráficos en cascada

**Aplicable a:** TBM Studio 12.2 y versiones posteriores

Los gráficos en cascada (también llamados gráficos de puente) muestran el efecto acumulativo de valores positivos y negativos sucesivos sobre un valor inicial. Destacan por su capacidad para explicar las variaciones, como por ejemplo, cómo han variado los costes entre los valores presupuestados y los reales, o de un periodo a otro.

**Comprensión de los componentes del gráfico en cascada**

- Valores de referencia: Las columnas completas inicial y final (y, opcionalmente, columnas de periodos intermedios, como los trimestres).
- Pasos intermedios: Columnas flotantes entre los valores de referencia que indican contribuciones positivas (al alza) o negativas (a la baja).
- Columna «Sin explicar»: representa cualquier variación que no se haya tenido en cuenta en los pasos intermedios definidos.
- Tabla explicativa: tabla configurable situada debajo del gráfico en la que se definen los pasos intermedios.

**Creación de un gráfico en cascada**

1. En la pestaña «Informe», haz clic en el icono de cascada.
2. En el panel «Configuración en cascada», selecciona un objeto de modelo en el menú desplegable.
3. En la sección «Métricas», arrastra una métrica modelada al área «Valores» (esto establece el valor inicial).
4. Arrastra una segunda métrica al área de métricas (esto crea el valor final).
5. Para modificar los intervalos de tiempo, haz clic con el botón derecho del ratón sobre el intervalo y selecciona «Shift»; a continuación, introduce un número positivo o negativo.

**Añadir pasos intermedios**

Los pasos intermedios explican la variación entre los valores de referencia. Deben añadirse en el entorno de producción:

1. Cambia al entorno de producción.
2. Abre el informe con el gráfico en cascada.
3. Haz clic en «Añadir explicación» en la parte inferior de la tabla de pasos intermedios.
4. Introduce una etiqueta en la columna «Paso», un valor positivo o negativo en la columna «Valor» y una descripción en la columna «Explicación».
5. Para cambiar el orden de los pasos, haz clic con el botón derecho del ratón y selecciona «Subir» o «Bajar».

Nota: Las explicaciones se almacenan en la base de datos de planificación de TI. Si esta base de datos no está instalada, no se pueden añadir explicaciones.

**Opciones del gráfico en cascada (pestaña «Cascada»)**

- Mostrar tabla: muestra la tabla explicativa debajo del gráfico. Al desmarcar esta casilla, la tabla queda oculta para los usuarios.
- Mostrar filas detalladas: muestra los pasos intermedios asociados a valores específicos del filtro en la parte inferior de la tabla de pasos (solo lectura).
- Explicación en las descripciones emergentes: muestra el texto del campo «Explicación» al pasar el cursor por encima de las barras.
- Número: Formato de los números que se muestran en el gráfico en cascada.
- Colores: Personaliza los colores de las barras de aumento, las barras de disminución y las barras de total.

Importante: Los valores del gráfico en cascada siempre se muestran en la moneda base establecida para el proyecto. Los gráficos en cascada no admiten múltiples divisas.

**Tema principal:** [Componentes del informe: Gráficos](../../../../studio/new-uc/reference/report-studio-reference/report-component-charts.html)
