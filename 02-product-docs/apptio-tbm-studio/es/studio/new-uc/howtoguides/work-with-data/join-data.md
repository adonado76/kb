---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Combinar datos de varias fuentes"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Trabajar con datos"
  - "Transformar y enriquecer los datos"
source_path: "studio/new-uc/howtoguides/work-with-data/join-data.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Combinar datos de varias fuentes

## Objetivo

Combina datos de dos o más tablas en las mismas filas basándote en valores coincidentes de las columnas clave, enriqueciendo así tu tabla principal con información complementaria.

## Cuándo utilizar esto

Utiliza «Join» cuando necesites:

- Añadir columnas de una tabla de referencia (por ejemplo, datos de centros de coste a partir de datos de RR. HH.)
- Enriquecer los datos de costes con información sobre activos o la jerarquía organizativa
- Combinar conjuntos de datos relacionados para elaborar informes exhaustivos
- Crea una tabla única con todos los datos necesarios para los controladores de las unidades del modelo

Nota: La unión combina los datos en las mismas filas. Si prefieres añadir filas, utiliza la función «Añadir» (consulta la sección C: «Añadir varias fuentes de datos»).

## Requisitos previos

- Tabla principal revisada
- Existen tablas relacionadas con columnas clave coincidentes
- Comprensión de las claves de unión (columnas con valores coincidentes)

## Estimación de tiempo

15-20 minutos

## Pasos

1. Abre la tabla principal en el **Explorador de proyectos**.
2. Añade un paso **«Join»** al proceso de transformación (aparecerá después del paso «Table»).
3. En el diagrama de unión, la tabla principal aparece a la izquierda. A la derecha aparecen las tablas correspondientes con los porcentajes de coincidencia.
4. Haz clic en **«Añadir enlace»** para crear una unión.
5. En el cuadro de diálogo «**Añadir enlace** »:
   - **De la tabla** : Selecciona la tabla relacionada para realizar la unión
   - **En «Columna** »: Selecciona la columna clave de la tabla relacionada
   - **En «Columna** »: Selecciona la columna clave correspondiente en tu tabla principal
6. Haz clic en **Aceptar** para crear el enlace.
7. Revisa el diagrama de uniones:
   - Haz clic en el signo **«+»** de las tablas para ver los porcentajes de coincidencia por columna
   - Haz clic en un enlace para ver los detalles de los resultados coincidentes, no coincidentes y de referencia
8. Si es necesario, añade más uniones repitiendo los pasos 4 a 6.
9. Haz clic en **«Guardar»** para aplicar el paso «Unir».
10. Comprueba que las columnas unidas aparezcan en el **Explorador de proyectos** debajo de tu tabla principal (se muestran con una notación del tipo « *TableName.ColumnName* »).

## Resultados previstos

Las columnas de la tabla unida ya están disponibles en tu tabla principal. Puedes utilizar estas columnas en fórmulas, informes y configuraciones de modelos. La vista previa del paso **«Tabla»** no muestra las columnas unidas, pero estas están disponibles en los pasos posteriores y en **el Explorador de proyectos**.

## Errores habituales

- **Porcentaje de coincidencia bajo:** si el porcentaje de coincidencia es bajo, comprueba que las columnas de la clave de unión contengan los mismos valores y tipos de datos. Los espacios al principio o al final, o las diferencias en mayúsculas y minúsculas, pueden impedir que se encuentren coincidencias.
- **Las columnas unidas no se ven en el paso «Tabla»:** se trata de un comportamiento esperado. Las columnas unidas aparecen en el Explorador de proyectos y en los pasos posteriores del proceso, pero no en la vista previa del paso «Tabla».
- **Uso de datos unidos en fórmulas:** si necesitas aplicar una lógica condicional basada tanto en las columnas principales como en las columnas unidas, utiliza fórmulas Lookup() en un paso de Fórmulas en lugar de basarte únicamente en la función Join.

**Tareas relacionadas**

- [Aplicar fórmulas para transformar datos](apply-formula.html)
- [Datos limpios y cartográficos](apply-formula.html)
- [Uso de las funciones de búsqueda](../../reference/formula-function.html)

**Tema principal:** [Transformar y enriquecer datos](../../../../studio/new-uc/howtoguides/work-with-data/transform-enrich-data.html)
