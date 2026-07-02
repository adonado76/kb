---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Añadir tablas a los informes"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Crear informes"
  - "Conceptos básicos sobre los informes"
source_path: "studio/new-uc/howtoguides/create-reports/add-tables-report.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Añadir tablas a los informes

**Objetivo:** Añadir una tabla de datos para mostrar los datos del modelo en un formato estructurado de filas y columnas

**Cuándo utilizarlo:** cuando necesites mostrar datos detallados, permitir un análisis en profundidad o presentar información que los usuarios quieran ordenar, filtrar o exportar

**Duración estimada:** 10-15 minutos

## Cómo entender el panel de configuración de componentes

Al añadir una tabla, aparece el panel «Configuración de componentes». Este panel cuenta con cuatro áreas a las que puedes arrastrar campos para crear tu tabla:

|  |  |  |
| --- | --- | --- |
| **Área** | **Finalidad** | **Qué arrastrar aquí** |
| **Filas** | Define los datos de la primera columna | Campos de dimensión (etiquetas, categorías) |
| **Columnas** | Muestra los encabezados de las columnas | Periodos de tiempo o una sola dimensión |
| **Valores** | Muestra los datos en las celdas de la tabla | Métricas (coste, presupuesto, recuento) |
| **Filtros** | Limita qué datos se muestran | Cualquier campo para filtrar los resultados |

**Pasos**

1. Abre tu informe y **échale un vistazo,** si aún no lo has hecho.
2. Haz clic en la pestaña **«Informe»** y, a continuación, haz clic en «**Tabla** ». En el informe aparece una tabla provisional y se abre el panel «Configuración de componentes ad hoc».
3. En la parte superior del panel de configuración, selecciona un **objeto de modelo** en la lista desplegable. Esto determina qué tablas y métricas están disponibles.
4. En el **Explorador de proyectos** (panel izquierdo), expande la sección **«Tablas»** para encontrar los campos de dimensión.
5. Arrastra un campo de dimensión al área «**Filas** ». Por ejemplo, arrastra «Centro de datos» para crear una tabla que muestre una fila por cada centro de datos.
6. Despliega la sección **«Métricas»** en el Explorador de proyectos.
7. Arrastra una o varias métricas al área «**Valores** ». Por ejemplo, arrastra «Coste» y «Presupuesto» para mostrar ambos valores en cada fila.
8. (Opcional) Añade columnas basadas en el tiempo desplegando la sección **«Tiempo»** y arrastrando un campo de tiempo al área «**Columnas** ».
9. (Opcional) Aplica filtros arrastrando cualquier campo al área **de filtros** y haciendo clic con el botón derecho del ratón para seleccionar «**Editar filtro** ».

## Ejemplo: Creación de una tabla de costes sencilla

Para crear una tabla que muestre el coste y el coste acumulado en lo que va de año por centro de datos:

- Selecciona **«Centros de datos»** como objeto modelo
- En «Tablas > Información de centros de datos», arrastra **«Centro de datos»** a **«Filas»**
- En «Métricas», arrastra **«Coste»** a **«Valores»**
- En «Métricas», arrastra **«Coste acumulado»** a **«Valores»**

## Resultados previstos

- La tabla se rellena con los datos de tu modelo
- Aparecen columnas para cada métrica que hayas añadido
- Aparecen filas para cada valor único del campo «Filas»
- Por defecto, aparece una fila «Total» en la parte inferior

## Errores habituales

- **Demasiados datos:** las tablas con miles de filas se vuelven lentas y difíciles de manejar. Aplica filtros o considera la posibilidad de utilizar gráficos para obtener una visión general.
- **Objeto de modelo incorrecto:** si no ves los campos que necesitas, comprueba que hayas seleccionado el objeto de modelo correcto en la parte superior del panel de configuración.
- **Olvidarse de actualizar:** si desmarcas la opción «Actualizar resultados inmediatamente», haz clic en «Actualizar» después de realizar los cambios para ver los datos.

**Tema principal:** [Conceptos básicos de los informes](../../../../studio/new-uc/howtoguides/create-reports/report-basic.html)
