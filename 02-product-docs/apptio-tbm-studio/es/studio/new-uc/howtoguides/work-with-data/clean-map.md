---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Limpiar y mapear datos utilizando las columnas del mapa"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Trabajar con datos"
  - "Transformar y enriquecer los datos"
source_path: "studio/new-uc/howtoguides/work-with-data/clean-map.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Limpiar y mapear datos utilizando las columnas del mapa

## Objetivo

Asigne las columnas de los datos de origen a esquemas de conjuntos de datos maestros estandarizados, garantizando que los datos se ajusten a la estructura prevista para la modelización de costes y la elaboración de informes.

## Cuándo utilizar esto

Utiliza las columnas de asignación cuando necesites:

- Alinear los datos externos (contabilidad general, presupuesto, previsiones) con las tablas maestras canónicas
- Estandarizar datos de diversas fuentes en estructuras unificadas
- Preparar los datos para su uso por parte de los objetos del modelo
- Asegúrese de que los campos obligatorios estén rellenados para los procesos posteriores

## Requisitos previos

- Tabla de origen cargada e importada
- Comprensión del esquema del conjunto de datos maestro de destino
- Los tipos de columna están configurados correctamente en la tabla de origen

## Estimación de tiempo

Entre 15 y 20 minutos para la configuración inicial; entre 5 y 10 minutos para las actualizaciones rutinarias

## Pasos

1. Busca en el Explorador de proyectos la tabla de origen que deseas asignar.
2. Haz clic en **«Añadir paso»** en el flujo de transformación y selecciona «**Asignar columnas** ».
3. Seleccione el conjunto de datos maestro de destino (por ejemplo, el maestro de fuentes de costes o el maestro de proveedores).
4. Asignar las columnas de origen a las columnas de destino:
   - El sistema empareja automáticamente las columnas con nombres idénticos (sin distinguir entre mayúsculas y minúsculas)
   - Revisa las columnas asignadas automáticamente (indicadas con marcas de verificación verdes)
   - Para las columnas obligatorias no asignadas (marcadas con un asterisco), seleccione la columna de origen correspondiente en el menú desplegable
   - Para vincular columnas de diferentes tipos, introduce una fórmula que comience por = (por ejemplo, =Value( {Column} ) para convertir texto en un valor numérico)
5. (Opcional) Añade columnas personalizadas al conjunto de datos principal haciendo clic en «**Añadir columna personalizada** ». Estas adiciones se mantienen tras las actualizaciones.
6. (Opcional) Para extraer datos adicionales de tablas relacionadas, haz clic en **«Unir»**, añade enlaces a otras tablas y asigna las columnas unidas.
7. Revisa la vista previa que aparece en la parte inferior del cuadro de diálogo para comprobar las asignaciones.
8. Haz clic en **«Guardar»** para aplicar el paso «Asignar columnas».

## Resultados previstos

Los datos de origen ahora se ajustan al esquema del conjunto de datos maestro y aparecen en la vista previa con todas las columnas asignadas. La tabla ya está lista para utilizarse en objetos de modelo e informes. Se añade automáticamente una columna a ***la tabla de origen*** para realizar un seguimiento del linaje de los datos.

## Errores habituales

- **La columna no aparece en el menú desplegable:** comprueba que el tipo de la columna de origen coincida con el tipo de la columna de destino. Las columnas numéricas no aparecerán al asignarlas a campos de etiqueta. Soluciona el problema yendo al paso «Importar» y modificando el tipo de columna.
- **Columnas obligatorias sin asignar:** aunque se puede guardar sin asignar todas las columnas obligatorias, los objetos del modelo posteriores pueden generar errores. Asegúrate siempre de asignar los campos obligatorios (marcados con \*) antes de utilizar la tabla en los modelos.
- **Errores de incompatibilidad de tipos:** si se asigna un código numérico a un campo de etiqueta, utilice una fórmula como « =NumberFormat({Account }*,"#,###.##»;* ») para convertir el tipo.

## Tareas relacionadas

- [Aplicar fórmulas para transformar datos](apply-formula.html)
- [Combinar datos de varias fuentes](join-data.html)
- <../../reference/data-studio-ref.html>

**Tema principal:** [Transformar y enriquecer datos](../../../../studio/new-uc/howtoguides/work-with-data/transform-enrich-data.html)
