---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Configuración de la estructura de la tabla"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes del informe: Tablas"
source_path: "studio/new-uc/reference/report-studio-reference/table-structure-config.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configuración de la estructura de la tabla

La estructura de la tabla se configura mediante el panel «Configuración de componentes», que aparece al añadir o seleccionar una tabla en un informe.

**Áreas de configuración de componentes**

El panel «Configuración de componentes» incluye cuatro áreas principales para crear tablas:

|  |  |  |
| --- | --- | --- |
| **Área** | **Descripción** | **Restricciones** |
| Filas | Proporciona los datos de la primera columna de la tabla. Las entradas duplicadas se agrupan automáticamente. Los campos múltiples crean subgrupos. | Acepta dimensiones (campos de etiqueta). Se permiten varios campos. |
| Columnas | Proporciona los encabezados de las columnas de la tabla. Se utiliza principalmente para realizar giros basados en el tiempo. | Solo se puede añadir UN campo. Se utiliza habitualmente para las dimensiones temporales. |
| Valores | Proporciona los datos que aparecen en el cuerpo de la tabla. Estas se convierten en las columnas numéricas. | Admite métricas y campos numéricos. Se permiten varios campos. |
| Filtros | Filtra los registros que se muestran en la tabla. Limita los datos a los que cumplen los criterios. | Acepta dimensiones y métricas. Se permiten varios filtros. |

**Añadir y eliminar columnas**

**Para añadir columnas:**

1. Selecciona la tabla del informe.
2. Arrastra los campos desde el Explorador de proyectos hasta el área correspondiente (Filas o Valores) en el panel Configuración de componentes.
3. La tabla se actualizará automáticamente para mostrar la nueva columna.

**Para eliminar columnas:**

- Arrastra el campo fuera del área de configuración de componentes, O BIEN
- Haz clic con el botón derecho del ratón en el campo y selecciona «Eliminar».

**Orden de las columnas**

**Para reordenar las columnas:**

- Haz clic en el encabezado de la columna y arrástralo hasta una nueva posición en la tabla.
- Reordena los campos del área «Valores» para cambiar el orden de las columnas.

**Nota:** Al exportar a Excel, las columnas mantienen el orden configurado en el componente de informe. Las columnas que no se hayan configurado explícitamente se añaden automáticamente al final.

**Agrupación de columnas**

Puedes agrupar dos o más columnas bajo un encabezado común. Esto resulta útil para organizar métricas relacionadas, como agrupar las columnas «Coste» y «Presupuesto» bajo el encabezado «Finanzas».

**Para agrupar columnas:**

1. Mantén pulsada la tecla Ctrl (Windows) o Alt (Mac) y haz clic en cada encabezado de columna para incluirlo en el grupo.
2. Haz clic con el botón derecho del ratón y selecciona «Agrupar columnas».
3. Introduce el texto del encabezado del grupo y haz clic en Aceptar.

**Consejo:** Puedes utilizar texto dinámico en los encabezados de grupo. Por ejemplo, <%=CurrentDate( )%> muestra el período actual.

Para desagrupar columnas, haz clic con el botón derecho del ratón en el encabezado de la columna y selecciona «Desagrupar columnas».

**Agrupación de filas**

Las tablas se agrupan automáticamente en función de al menos un campo del área «Filas». La agrupación adicional consolida los datos y muestra valores agregados.

**Para configurar la agrupación de filas:**

1. Selecciona la tabla y haz clic en «Agrupar» en la pestaña «Datos».
2. En el cuadro de diálogo «Agrupar», selecciona las columnas que deseas utilizar para agrupar.
3. Haz clic en «Grupo» para enviar tu solicitud.

Cuando se agrupan, las columnas con varios valores diferentes muestran tres puntos verticales (varios), y se añade una columna «Recuento» que indica el número de entradas agrupadas.

**Subtotales y totales generales**

Cuando hay varios campos en el área «Filas», TBM Studio agrupa automáticamente los valores y puede mostrar subtotales. Configure los subtotales mediante el cuadro de diálogo «Subtotales» de la pestaña «Datos».

|  |  |  |
| --- | --- | --- |
| **Opción** | **Descripción** | **Valor predeterminado** |
| Mostrar fila completa | Muestra una fila «Total» en la parte inferior de la tabla con los valores agregados. | Habilitada |
| Mostrar columna «Total» | Muestra una columna «Totales» con los totales de cada fila. | Inhabilitado |
| Mostrar otra fila | Cuando el número de filas es limitado, se muestra una fila «Otros» con los totales restantes. | Inhabilitado |
| Inserta etiquetas de subtotal en | Determina en qué columna se muestran las etiquetas de subtotal. | Primera columna agrupada |
| Niveles de subtotal (1-4) | Número de niveles de agrupación para los que se mostrarán subtotales. | 1 |

**Consejo:** La fila «Total» gestiona de forma inteligente los distintos tipos de columnas: suma las columnas numéricas y, en el caso de las columnas calculadas (como «Coste por servidor»), vuelve a calcular el valor utilizando los totales en lugar de sumar los valores individuales.

**Estructura de árbol de subtotales**

En el caso de datos jerárquicos, crea tablas en forma de árbol que se puedan desplegar y que permitan a los usuarios profundizar en los distintos niveles.

**Para crear un árbol de subtotales:**

1. Arrastra dos o más campos al área «Filas».
2. Añade uno o varios campos al área «Valores».
3. En la pestaña Datos, en el grupo Estructura, haz clic en «Como árbol».
4. Si lo deseas, configura «Número máximo de elementos secundarios» para limitar el número de filas que se muestran y añadir un enlace «Otros» para los elementos restantes.

**Tema principal:** [Componentes del informe: Tablas](../../../../studio/new-uc/reference/report-studio-reference/report-component-table.html)
