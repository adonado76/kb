---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Configuración de columnas"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes del informe: Tablas"
source_path: "studio/new-uc/reference/report-studio-reference/column-config.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configuración de columnas

Cada columna de una tabla se puede configurar de forma individual en cuanto a su visualización, formato y comportamiento.

**Tipos de columnas**

|  |  |  |
| --- | --- | --- |
| **Tipo de columna** | **Descripción** | **Origen** |
| Dimensión | Columnas de etiquetas/texto de las tablas. Se utiliza en el área «Filas» para agrupar. | Sección «Tablas» en el Explorador de proyectos |
| Métrica | Columnas numéricas con formato predefinido. Incluye el modelo y las métricas calculadas. | Sección de métricas en el Explorador de proyectos |
| Fórmula | Columnas calculadas personalizadas mediante fórmulas. Puede hacer referencia a otras columnas y funciones. | Creado a través de la pestaña «Datos» > «Nueva columna» |
| Calculado | Columnas derivadas: Recuento, Porcentaje, Variación, Comparación, Iconos de umbral. | Creado mediante la configuración de campos de valor |
| Basado en el calendario | Valores acumulados: acumulado del año, acumulado del trimestre, ejercicio fiscal, ejercicio fiscal anterior, anual, últimos doce meses, etc. | Creado a través de la pestaña «Fórmulas» > «Fechas» |
| Gráfico de tendencia | Pequeña línea de tendencia que muestra datos históricos. | Creado a través de la pestaña «Fórmulas» > «Fechas» > «Gráficos de tendencia» |
| Indicador de estado | Iconos que indican el estado de los valores (rojo/amarillo/verde, flechas, etc.). | Creado mediante la función «Icono» |
| Total | Suma los totales de las filas en varias columnas de valores. | Creado a través de la pestaña «Datos» > «Suma» |
| Espaciador | Columna en blanco para separar visualmente. | Creado a través de la pestaña «Datos» > «Insertar» > «Columna de separación» |
| Editable | Columna editable por el usuario en tablas editables. | Configuración de la tabla editable |

**Añadir columnas de fórmulas**

Las columnas de fórmulas permiten realizar cálculos personalizados utilizando los datos de la tabla.

**Para añadir una columna de fórmula:**

1. Selecciona la tabla y haz clic en la pestaña «Datos».
2. Haz clic en «Nueva columna».
3. Introduce un nombre para la columna.

1. Selecciona «Introducir fórmula» e introduce la fórmula utilizando el formato « table.column ».
2. Selecciona el formato y el tipo, y, si lo deseas, activa la opción «Sumable».
3. Pulse Aceptar.

**Referencia de propiedades de columna**

|  |  |  |
| --- | --- | --- |
| **Propiedad** | **Descripción** | **Valores** |
| Nombre | Nombre que se mostrará para la columna. Acepta caracteres alfanuméricos. | Cualquier texto |
| Tipo | Tipo de datos de los valores de la columna. | Automático, Numérico, Etiqueta, Fecha |
| Formato | Formato de visualización de los valores. | Número, Moneda, Porcentaje, Fecha, Avanzado (fórmula) |
| Summable | Si la columna se puede sumar de forma segura cuando se agrupa. Desactivar para las columnas de ratios calculados. | Sí/No (por defecto: No) |
| Decimales | Número de decimales para los valores numéricos. | 0-10 (varía según el formato) |
| Usar separador de agrupación | Añade el separador de miles según la configuración regional del proyecto. | Sí/No |

**Ancho de columna**

**Para cambiar el ancho de una columna:**

- Coloca el puntero del ratón sobre el borde derecho del encabezado de la columna. Cuando el cursor se convierta en una flecha de cambio de tamaño, haz clic y arrastra.
- Haz clic con el botón derecho del ratón en el encabezado de la columna > Formato > Establecer ancho e introduce el ancho en píxeles.

**Visibilidad de las columnas**

Las columnas se pueden ocultar al configurar la tabla. Las columnas ocultas siguen participando en los cálculos, pero no se muestran.

**Para ocultar una columna:**

- Haz clic con el botón derecho del ratón en el nombre de la columna en el área «Valores» del panel «Configuración de componentes» y selecciona «Ocultar». El nombre de la columna aparece en gris.

**Para mostrar una columna oculta:**

- Haz clic con el botón derecho del ratón en el nombre de la columna que aparece en gris en el panel «Configuración de componentes» y selecciona «Mostrar».

**Tema principal:** [Componentes del informe: Tablas](../../../../studio/new-uc/reference/report-studio-reference/report-component-table.html)
