---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Añadir varias fuentes de datos"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Trabajar con datos"
  - "Transformar y enriquecer los datos"
source_path: "studio/new-uc/howtoguides/work-with-data/append-multiple.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Añadir varias fuentes de datos

## Objetivo

Combina las filas de una o varias tablas de origen en una tabla de destino, creando así un conjunto de datos unificado a partir de múltiples fuentes.

## Cuándo utilizar esto

Utiliza «Append» cuando necesites:

- Combinar datos de varias fuentes similares (por ejemplo, inventarios de servidores virtuales y físicos)
- Consolidar los datos regionales en una única tabla maestra
- Añadir filas de datos adicionales a una tabla existente
- Agrupar conjuntos de datos con estructuras similares, pero no idénticas

Nota: La función «Append» añade filas a la tabla. Si, por el contrario, quieres añadir columnas a filas ya existentes, utiliza la función «Unir» (consulta «Unir datos de varias fuentes&»).

## Requisitos previos

- La tabla de destino es una tabla de transformación (no una tabla cargada)
- Existen tablas de origen con datos que se deben añadir
- Comprensión de la correspondencia entre columnas del origen y el destino

## Estimación de tiempo

Entre 15 y 20 minutos para la configuración inicial; 5 minutos para añadir fuentes adicionales

## Pasos

1. Echa un vistazo a la tabla de destino en **el Explorador de proyectos**.
2. Añade un paso **«Añadir»** al proceso de transformación.
3. Haz clic en «**Añadir fuente de datos** ».
4. Seleccione la tabla de origen a la que desea añadir datos y haga clic en «**Siguiente** ».
5. Asignar columnas de origen a columnas de destino:
   - **Columnas emparejadas automáticamente:** las columnas con nombres coincidentes (sin distinción entre mayúsculas y minúsculas) se asignan automáticamente y se muestran con marcas de verificación verdes
   - **Asignación manual:** para las columnas sin asignar, utiliza el menú desplegable para seleccionar la columna de origen correspondiente
   - **Valores fijos:** para utilizar el mismo valor en todas las filas añadidas, seleccione «Introducir un valor fijo para todas las filas» e introduzca el valor
   - **Fórmulas:** Introduce una fórmula que comience por = para transformar los datos de origen (por ejemplo, ="pm-&"& {Asset Tag} )
6. (Opcional) Haz clic en **«Seleccionar columna de origen adicional»** para añadir nuevas columnas de la tabla de origen a la tabla de destino.
7. Consulte las tablas de vista previa que aparecen al final para comprobar la asignación.
8. Pulse **Guardar**.
9. Para añadir tablas de origen adicionales, haz clic de nuevo en **«Añadir origen de datos»** y repite los pasos 4 a 8.

## Resultados previstos

Las filas de todas las tablas de origen se añaden a la tabla de destino. La vista previa muestra datos combinados de todas las fuentes. Cada fuente aparece en el panel «Adicionar» junto con el número de columnas asignadas que se requieren.

## Gestión de fuentes adjuntas

En el panel «Añadir», puedes:

- **Edición** : Modificar las asignaciones de columnas para una fuente añadida
- **Eliminar** : Eliminar una fuente añadida de la tabla de destino
- **Añadir fuente de datos** : Añadir otra tabla de origen para añadir datos

## Errores habituales

- **Discrepancias en los tipos de columna:** si una columna de origen no aparece en el menú desplegable, comprueba que tenga el mismo tipo que la columna de destino. Si es necesario, utiliza fórmulas para convertir los tipos.
- **Fórmulas frente a valores fijos:** los valores fijos no evalúan las fórmulas. Para utilizar una fórmula, añade un paso «Fórmulas» antes del paso «Añadir», y luego asigna la columna resultante.
- **Bloqueo de adiciones para periodos fuera del intervalo:** en las tablas versionadas, las adiciones solo se aplican a la versión actual. Si se selecciona un periodo fuera del intervalo de fechas de la versión, la entrada se bloquea y no se puede editar.

## Tareas relacionadas

- [Combinar datos de varias fuentes](join-data.html)
- [Aplicar fórmulas para transformar datos](apply-formula.html)
- Uso de las funciones de búsqueda (Referencia: Fórmulas y funciones)

**Tema principal:** [Transformar y enriquecer datos](../../../../studio/new-uc/howtoguides/work-with-data/transform-enrich-data.html)
